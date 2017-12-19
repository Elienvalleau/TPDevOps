FROM scratch
ARG app_env
ENV APP_ENV $app_env

RUN apk update && \
   apk add \
      npm \
      node:8 \
      mongodb && \

CMD if [ ${APP_ENV} = production ]; \
        then \
        npm install --production && \
        NODE_ENV=production MONGO_HOST=localhost MONGO_USER=root MONGO_DATABASE=test MONGO_PASSWORD=123456 node app.js; \
        else \
        npm install && \
        NODE_ENV=development MONGO_HOST=localhost MONGO_USER=root MONGO_DATABASE=test MONGO_PASSWORD=123456 node app.js; \
        fi
