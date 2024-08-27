FROM node:16

# The working directory where interface is placed is /usr/src/app/daphne-at-interface
WORKDIR /usr/src/app/daphne-at-interface

# Copy everything in the daphne_brain directory to /usr/src/app/daphne-at-interface
COPY ./package.json ./package-lock.json /usr/src/app/daphne-at-interface/

RUN npm ci
RUN npm install

# Copy Interface
COPY ./. /usr/src/app/daphne-at-interface/

EXPOSE 8080

#CMD npm run dev
#CMD [ "npm", "run", "dev"]
CMD npm run dev --host 0.0.0.0
#
#RUN curl -sL https://deb.nodesource.com/setup_lts.x | bash - && \
#    apt-get install -y nodejs
#
## --> 1. Install dependencies
#WORKDIR /usr/src/app/daphne-at-interface
#COPY package.json package-lock.json* ./
#RUN npm install
#
## --> 2. Copy Interface
#WORKDIR /usr/src/app
#COPY ./. /usr/src/app/daphne-at-interface/
#
## --> 3. Run container
##CMD npm run dev
#EXPOSE 8080
#CMD [ "npm", "start"]
#CMD npm run dev