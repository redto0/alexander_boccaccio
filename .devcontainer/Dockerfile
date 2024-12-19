# Use an official Node runtime as a parent image for Vue.js
FROM node:14 as vue-build

# Set the working directory in the container
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Install Vue CLI and project dependencies
RUN npm install -g @vue/cli && npm install

# Build the Vue.js app
RUN npm run build

# Use an official Python runtime as a parent image for Flask
FROM python:3.9-slim

# Set the working directory in the container
WORKDIR /app

# Copy the Vue.js build output to the Flask container
COPY --from=vue-build /app/dist /app/static

# Copy the current directory contents into the container at /app
COPY . /app

# Install Flask
RUN pip install Flask

# Make port 5000 available to the world outside this container
EXPOSE 5000

# Run the Flask app
CMD ["python", "app.py"]
