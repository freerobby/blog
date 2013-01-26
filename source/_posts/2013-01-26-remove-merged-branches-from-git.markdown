---
layout: post
title: "Remove Merged Branches from Git"
date: 2013-01-26 16:28
comments: true
categories: [Technology, Git, Bash, Shell]
---

I wrote a bash function that prunes a git repository's ancestral branches, helping you keep your local and remote repos tidy.

This function removes all branches, local and remote, that have been merged into your current branch. Simply run "rmb" from the command line. Don’t worry - prompt safeguards are in place to show you what you'll be removing before it delets anything. And it won't let you delete "master." :-)

Add this to your ~/.profile, run "source ~/.profile" and you’re good to go.

{% codeblock rmb.sh %}
function rmb {
  current_branch=$(git branch --no-color 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/\1/')
  if [ "$current_branch" != "master" ]; then
    echo "WARNING: You are on branch $current_branch, NOT master."
  fi
    echo "Fetching merged branches..."
  git remote prune origin
  remote_branches=$(git branch -r --merged | grep -v '/master$' | grep -v "/$current_branch$")
  local_branches=$(git branch --merged | grep -v 'master$' | grep -v "$current_branch$")
  if [ -z "$remote_branches" ] && [ -z "$local_branches" ]; then
    echo "No existing branches have been merged into $current_branch."
  else
    echo "This will remove the following branches:"
    if [ -n "$remote_branches" ]; then
      echo "$remote_branches"
    fi
    if [ -n "$local_branches" ]; then
      echo "$local_branches"
    fi
    read -p "Continue? (y/n): " -n 1 choice
    echo
    if [ "$choice" == "y" ] || [ "$choice" == "Y" ]; then
      # Remove remote branches
      git push origin `git branch -r --merged | grep -v '/master$' | grep -v "/$current_branch$" | sed 's/origin\//:/g' | tr -d '\n'`
      # Remove local branches
      git branch -d `git branch --merged | grep -v 'master$' | grep -v "$current_branch$" | sed 's/origin\///g' | tr -d '\n'`
    else
      echo "No branches removed."
    fi
  fi
}
{% endcodeblock %}

