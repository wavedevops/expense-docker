#FROM nginx
#RUN rm -rf /usr/share/nginx/html/index.html
#RUN rm -rf /etc/nginx/nginx.conf
#RUN rm -rf /etc/nginx/conf.d/default.conf
#RUN mkdir -p /var/cache/nginx/client_temp && \
#        mkdir -p /var/cache/nginx/proxy_temp && \
#        mkdir -p /var/cache/nginx/fastcgi_temp && \
#        mkdir -p /var/cache/nginx/uwsgi_temp && \
#        mkdir -p /var/cache/nginx/scgi_temp && \
#        chown -R nginx:nginx /var/cache/nginx && \
#        chown -R nginx:nginx /etc/nginx/ && \
#        chmod -R 755 /etc/nginx/ && \
#        chown -R nginx:nginx /var/log/nginx
#RUN touch /var/run/nginx.pid && \
#    chown -R nginx:nginx /var/run/nginx.pid /run/nginx.pid
#COPY expense.conf /etc/nginx/nginx.conf
#COPY code /usr/share/nginx/html/
#USER nginx
# Use an ARM-compatible Nginx image
FROM nginx:alpine

# Remove unnecessary default files
RUN rm -rf /usr/share/nginx/html/index.html && \
    rm -rf /etc/nginx/nginx.conf && \
    rm -rf /etc/nginx/conf.d/default.conf

# Create required directories and set permissions
RUN mkdir -p /var/cache/nginx/client_temp && \
    mkdir -p /var/cache/nginx/proxy_temp && \
    mkdir -p /var/cache/nginx/fastcgi_temp && \
    mkdir -p /var/cache/nginx/uwsgi_temp && \
    mkdir -p /var/cache/nginx/scgi_temp && \
    chown -R nginx:nginx /var/cache/nginx && \
    chown -R nginx:nginx /etc/nginx/ && \
    chmod -R 755 /etc/nginx/ && \
    chown -R nginx:nginx /var/log/nginx

# Ensure the nginx PID file exists and set ownership
RUN touch /var/run/nginx.pid && \
    chown -R nginx:nginx /var/run/nginx.pid /run/nginx.pid

# Copy your custom Nginx configuration and application code
COPY expense.conf /etc/nginx/nginx.conf
COPY code /usr/share/nginx/html/

# Switch to non-root user (nginx)
USER nginx

# Expose default Nginx port
EXPOSE 80
