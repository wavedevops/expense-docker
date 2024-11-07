FROM node:20
EXPOSE 8080
RUN useradd expense
USER expense
RUN mkdir /opt/server
RUN chown expense:expenses -R /opt/server
COPY code/* .
RUN npm install
CMD [ "node","index.js" ]