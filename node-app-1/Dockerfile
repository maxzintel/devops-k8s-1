FROM node:alpine
WORKDIR '/app'
COPY ./package.json ./
RUN npm install
COPY . .
CMD ["npm", "run", "start"]

# To run, use: docker run -p 3000:3000 -t <image-id>
# To verify it works, use: curl localhost:3000

# To tag, use: docker tag <image-id> <username>/hello-world
# To push to Docker Hub, use: docker push <username>/hello-world
