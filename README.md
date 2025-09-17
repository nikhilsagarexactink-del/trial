# Turbo Charged Athletics
# Php require 8.0.25 or greater than 
# Mysql verion 10.4.27-MariaDB

# Queue Worker command on server for send email (Jobs and Queue)

# This cron is stop when queue is restart
# command for server: nohup php artisan queue:work --daemon > /dev/null 2>&1 &
# command for local: php artisan queue:work

# This runs every minute, ensuring the queue is continuously processed.

# * * * * * php /home/558415.cloudwaysapps.com/vfcukddksd/public_html/artisan queue:work --tries=3 --timeout=90 >> /dev/null 2>&1

# Here
# --tries=3 retries failed jobs up to 3 times.
# --timeout=90 prevents long-running jobs from hanging.

# Cron(Schudule:command) run on the server so please add on the cron tab
# artisan schedule:run >> /dev/null 2>&1

# Couldways support team suggestion for jobs queue

# Here are several things you can do to reduce RAM/CPU usage:
# 1. Use --sleep and --memory flags
# They prevent the worker from eating up memory and CPU when no jobs are available
# Queue via queue:listen during development
# If it’s a dev/staging site, use queue:listen instead of queue:work. It’s less efficient but better for debugging.
# Use Job Batching/Chunking
# If jobs are processing large datasets, break them into smaller chunks.
# Check DB or external service calls in Jobs
# If jobs call APIs or run DB queries, slow responses can keep the worker busy longer.


# For run schedule (Cron)
# * * * * * php /home/558415.cloudwaysapps.com/rafjmwdqnw/public_html/artisan schedule:run >> /dev/null 2>&1


# Text Message(Twilio) and Email (Postmark) working only production side its disabled for local and staging.If want to test so please set APP_ENV=production in .env file.