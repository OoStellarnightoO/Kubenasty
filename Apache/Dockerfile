FROM httpd:2.4.49

# Copy custom httpd.conf from ubuntu host to apache container
COPY httpd.conf /usr/local/apache2/conf/httpd.conf

# git clone to tmp folder first because it will run into issues trying to clone to /usr/local/apache2/htdocs as it already exists
RUN apt-get update && apt-get install -y git && \
    git clone https://github.com/picocms/Pico.git /tmp/pico && \
    cp -r /tmp/pico/* /usr/local/apache2/htdocs/ && \
    rm -rf /tmp/pico && \
    chmod -R 755 /usr/local/apache2/htdocs/ && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# Expose the default HTTP port
EXPOSE 80

