# Timesheet Githook
Asks how long you worked on a commit then logs that amount of time to the corresponding JIRA ticket. Feel free to log issues or send PRs. Here is the [blog post](http://mike-solomon.com/timesheet-githook) if you'd like a walkthrough of the code or if you would like to leave comments, suggestions or share experiences.

## Example
![example](http://i.imgur.com/s4v8eKS.gif)

## Setup
### Clone the Post Commit Hook
- Steps
  1. Open your terminal and change directory to your github repository `` cd my-github-repository ``
  2. Run this command to change your directory to your git hooks folder (you need the back ticks) `` cd `git rev-parse --git-dir`/hooks ``
  3. Clone the timesheet git hook and install dependencies with this command: `` git clone https://github.com/msolomonTMG/timesheet-githook.git && ln -s timesheet-githook/post-commit post-commit && chmod +x post-commit && chmod +x timesheet-githook/sum_time.rb && sudo gem install bundler && bundle install ``
  - Be sure to change the JIRA url if you are not from my organization :)

## Usage
- When you commit on a branch that has a JIRA ticket in the name and you do not log time through a [smart commit](https://confluence.atlassian.com/display/FISHEYE/Using+smart+commits#Usingsmartcommits-TransitionyourJIRAissues), a message will pop up asking how long that commit took to code.
- Answer the question in this format:
  - 1d (for one day)
  - 2h (for two hours)
  - 30m (for thirty minutes)
  - 1h 10m (for one hour and ten minutes)

## Notes
- I welcome pull requests to make this better!
- I want an update to not show the message if the commit is a merge
  - [This stack overflow article](http://stackoverflow.com/questions/3824050/telling-if-a-git-commit-is-a-merge-revert-commit) seems like a good place to start for this
