# TryHackMeBadge
# Automate Security Achievement from TryHackMe WorkFlow
name: Update TryHackMe Badge

on:
  schedule:
    - cron: '0 0 * * *' # Runs every day at midnight
  workflow_dispatch: # Allows manual triggering

jobs:
  update-badge:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout repository
      uses: actions/checkout@v2

    - name: Fetch TryHackMe Badge
      uses: DhanushNehru/tryhackme-badge-action-workflow@v1.0
      with:
        image_path: './assets/tryhackme-badge.png'
        username: 'vinciaclaire'
        user_id: 'vinciaclaire'
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
