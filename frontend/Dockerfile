FROM node:18-alpine
WORKDIR /app
COPY package.json package-lock.json ./
RUN npm install --omit=dev=false
COPY . .
ARG NEXT_PUBLIC_BACKEND_URL
ARG NEXT_PUBLIC_MODEL_URL
ENV NEXT_PUBLIC_BACKEND_URL=$NEXT_PUBLIC_BACKEND_URL
ENV NEXT_PUBLIC_MODEL_URL=$NEXT_PUBLIC_MODEL_URL
RUN echo "NEXT_PUBLIC_BACKEND_URL=$NEXT_PUBLIC_BACKEND_URL"
RUN echo "NEXT_PUBLIC_MODEL_URL=$NEXT_PUBLIC_MODEL_URL"
RUN npm run build
EXPOSE 3000
CMD ["npm", "run", "start"]
