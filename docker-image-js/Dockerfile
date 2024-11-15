#Use the official Node.js image from the Docker Hub 
FROM node:14 

# Create and set the working directory 
WORKDIR /app 

# Copy package.json and install dependencies 
COPY package*.json ./ 
RUN npm install 

# Copy the project files 
COPY . . 

# Expose the port 
EXPOSE 3000 

# Command to run the application 
CMD ["node", "my-app.js"]