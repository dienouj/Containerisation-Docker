FROM nginx
LABEL "Project"="Vprofile"
LABEL "Maintainer"="Jouneid"
# Remove default configuration files
RUN rm -rf /etc/nginx/conf.d/default.conf  
# Copy custom Nginx configuration
COPY nginvproapp.conf /etc/nginx/conf.d/vproapp.conf  
