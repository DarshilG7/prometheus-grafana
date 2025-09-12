# Prometheus & Grafana Setup

This repository contains my Grafana dashboard JSON and instructions for setting up Prometheus and Grafana.

## Steps I Followed

1. **Install Prometheus**  
   - Installed Prometheus locally on Windows.
   - Exract the folder and you will be able to see multiple folders and a YAML file.
   - now run YAML file.
   - As i am on windows i willl use powershell as run as admin an you need to switch to your preometheus folder where your all files for prometheus are kept.
   - Configured `prometheus.yml` as needed.
   - prometheus.exe --config.file=prometheus.yml 
   - By default it will be running on port 9090 so you can access it by `http://localhost:9090`


2. **Run Grafana via Docker**  

   - I have installed docker desktop on my windows and i'm using gitbash. 
   - now when i chceck for #docker --version it will show the version which i am using.
   - Now pull Grafana Docker image:
     ```
     docker pull grafana/grafana
     ```
   - Started Grafana container:
     ```
     docker run -d -p 3000:3000 grafana/grafana

     ```
   - now you can access grafana using `http://localhost:3000`


3. **Add Prometheus as a Data Source**  
   - Open Grafana in browser: `http://localhost:3000`
   - Log in (default: admin/admin)
   - Add Prometheus as a data source in Grafana settings.
   - note = as you are using grafana via docker you wont be able to add datasource by `http://localhost:9090`
   - Instead you need to write `http://host.docker.internal:9090` as commonly used in Docker environments to access a service running on the host machine from inside a Docker container 

4. **Export Dashboard JSON**  
   - Created a dashboard in Grafana.
   - you can add queries like `process_resident_memory_bytes`
   - Exported dashboard JSON file and saved it.

