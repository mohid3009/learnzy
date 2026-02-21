FROM node:18-alpine

# Create app directory
WORKDIR /usr/src/app

# Install app dependencies
# We use a wildcard to ensure both package.json AND package-lock.json are copied
# We copy from the backend/ directory because the context is the repository root
COPY backend/package*.json ./

# Use --omit=dev instead of --production to avoid warnings in npm 8+
RUN npm install --omit=dev

# Bundle app source
COPY backend/ .

# Bind to the standard port
EXPOSE 5000

# Start the application
CMD [ "npm", "start" ]
