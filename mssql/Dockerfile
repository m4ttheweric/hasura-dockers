FROM mcr.microsoft.com/azure-sql-edge
COPY ./bikes.sql .

# USER root
# #Install curl since it is needed to get repo config
# # Get official Microsoft repository configuration
# RUN export DEBIAN_FRONTEND=noninteractive && \
#     apt-get update && \
#     apt-get install -y gnupg2 && \
#     apt-get install -y curl  && \
#     curl https://packages.microsoft.com/keys/microsoft.asc |  apt-key add - && \
#     curl https://packages.microsoft.com/config/ubuntu/20.04/mssql-server-2019.list | tee /etc/apt/sources.list.d/mssql-server.list && \
#     apt-get update

# # Install optional packages.  Comment out the ones you don't need
# #RUN apt-get install -y mssql-server-agent
# # RUN apt-get install -y mssql-server-ha
# # RUN apt-get install -y mssql-server-fts

# RUN apt-get install -y mssql-tools

# RUN ( /opt/mssql/bin/sqlservr --accept-eula & ) | grep -q "Service Broker manager has started" \
#     && /opt/mssql-tools/bin/sqlcmd -S localhost -U SA -P '12345' -d master -i bikes.sql \
#     && pkill sqlservr 
