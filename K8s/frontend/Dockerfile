From nginx
COPY . /opt
WORKDIR /opt/angular-frontend
RUN apt update
RUN apt install nodejs npm -y
RUN npm install -g @angular/cli
# Replace the localhost with the public IP and the port 8080 with 8085 in WorkerService
COPY worker.service.ts /opt/angular-frontend/src/app/services/worker.service.ts
RUN npm install
RUN ng build 
EXPOSE 30080
CMD ["ng", "serve", "--host", "0.0.0.0", "--port", "30080"]
