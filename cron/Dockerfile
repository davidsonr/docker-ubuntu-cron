FROM ubuntu:18.10

RUN apt-get update
RUN apt-get update && apt-get install -y cron

ADD hello-cron /etc/cron.d/hello-cron

# Give execution rights on the cron job
RUN chmod 0644 /etc/cron.d/hello-cron

# Create the log file to be able to run tail
RUN touch /var/log/cron.log

# Symlink the cron to stdout
RUN ln -sf /dev/stdout /var/log/cron.log

# Run the command on container startup
CMD cron && tail -F /var/log/cron.log 2>&1


