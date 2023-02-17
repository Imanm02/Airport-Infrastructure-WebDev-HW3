FROM python:3.9-buster
WORKDIR /bank
COPY package*.json ./
RUN npm install
COPY . .
CMD ["express", "express.js"]