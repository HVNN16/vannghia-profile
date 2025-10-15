FROM node:20-alpine

WORKDIR /app

# Cài dependencies
COPY package*.json ./
RUN npm install

# Copy toàn bộ source code
COPY . .

# Sửa quyền cho react-scripts và build
RUN chmod +x node_modules/.bin/react-scripts && CI=false npm run build

# Serve build folder bằng 'serve'
RUN npm install -g serve

EXPOSE 3000
CMD ["serve", "-s", "build", "-l", "3000"]
