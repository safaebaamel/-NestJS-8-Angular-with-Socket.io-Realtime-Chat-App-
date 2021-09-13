# specify Node version nd image
# Image name (development -- can be changed)
FROM node:14 AS development

# Specify working directory inside a container
WORKDIR /sophie/src/app

# Copy package-lock.json & package.json from host to inside container working directory
COPY package*.json ./

# Install dependencies 
RUN npm install

#Bundle App Sources
COPY . .

RUN npm run build

EXPOSE 3000

## PROD ##
# Build another image named production

FROM node:14 AS production

ARG NODE_ENV=production
ENV NODE_ENV=${NODE_ENV}

# Set Work directory

WORKDIR /sophie/src/app

COPY --from=development /sophie/src/app .

EXPOSE 3000

# Run app

CMD ["node", "dist/main"]