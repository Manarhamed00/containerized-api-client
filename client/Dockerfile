FROM node:18

# Set working directory
WORKDIR /usr/src/app

# Copy application files
COPY . .

# Install dependencies
RUN npm install

# Expose port for Nuxt.js
EXPOSE 3000

CMD ["npm", "run", "dev"]
