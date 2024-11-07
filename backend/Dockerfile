FROM node:20
EXPOSE 8080
RUN useradd expense
USER expense
RUN mkdir /app
RUN chown expense:expenses -R /app
COPY code/* .
RUN npm install
CMD [ "node","index.js" ]