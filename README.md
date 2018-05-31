# Dockerizing Swirlds' Hashgraph SDK
Prerequisites: `docker` and `docker-compose`

1. Clone this repo
``` 
git clone git@github.com:dappcoder/swirlds-dockerized-sdk.git 
```
2. Go to `./swirlds-sdk/config.txt` and update the external IPs of the participants. Replace `192.168.1.123` with your local IP address. 
3. Download Hashgraph Swirlds SDK. 
``` https://www.swirlds.com/download/ ```
4. Unzip to desired location.
5. Copy the sdk directory from extracted archive to `./swirlds-sdk` under the root directory of this repository. Check that you now have `./swirlds-sdk/sdk/config.txt` as a valid path.
6. Run it
``` docker-compose up ```

Wait until the 4 containers log `This computer has an internal IP address`. 

You should now have 4 instances (Alice, Bob, Carol, Dave) of Hashgraph demo app 'StatsDemo' running in separate containers, being connected through a docker network.

To see statistics results of the running Hashgraph network do the following:

1. List the running docker containers
``` 
docker ps
```
2. Pick one of the hashgraph containers' ID
3. exec into that container
``` 
docker exec -it YOUR_CHOSEN_CONTAINER_ID 
```
4. check the StatsDemo logs
```
tail -f /usr/local/swirlds/sdk/StatsDemo* 
```

If you know how to read the CSV file, you should be able to see the real-time throughput statistics of your Hashgraph network. I got 180k TPS on a modest laptop (with TLS off).
