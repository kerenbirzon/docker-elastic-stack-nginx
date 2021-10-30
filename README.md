To run this stack, run the following command:

docker-compose up
go to http://localhost:5601 to see your data in Kibana

Default Kibana user information

Username: elastic
Password: changeme

By default, the stack exposes the following ports:

5044: Logstash Beats input
5000: Logstash TCP input
9600: Logstash monitoring API
9200: Elasticsearch HTTP
9300: Elasticsearch TCP transport
5601: Kibana

80 or 443: nginx HTTPS 
need to create localhost.key and localhost.crt in /nginx/certs in order to enable ssl.
so create HTTPS certificate run the following commands:
openssl req -x509 -nodes -new -sha256 -days 1024 -newkey rsa:2048 -keyout localhost.key -out RootCA.pem -subj "/C=US/CN=Example-localhost"
openssl x509 -outform pem -in RootCA.pem -out localhost.crt
