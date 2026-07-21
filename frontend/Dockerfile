#Frontend UI
#  Created by Prakash Mahajan
# step 1 bring the base image
FROM node:24

# step 2 create a folder where code can stay
WORKDIR /app

# step 3 copy the code from host machine to the container
COPY . .

# step 4 install the required dependencies
RUN npm install --legacy-peer-deps

# step 5 expose the port number for documentation purposes
EXPOSE 51
# step 6 run the application
CMD ["npm", "run", "dev", "--", "--host", "0.0.0.0", "--port", "5173"]
