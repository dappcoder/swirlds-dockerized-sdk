1. Download Hashgraph Swirlds SDK.
2. Unzip to desired location.
3. Copy the sdk directory from extracted archive to ./swirlds-sdk under the root directory of this repository. Check that you now have ./swirlds-sdk/sdk/config.txt
4. Run docker-compose up

You should now have 4 instances of Hashgraph demo app 'StatsDemo' running in separate containers, being connected through a docker network.
To see statistics results of the running Hashgraph network do the following:

1. List the running docker containers
2. Pick one of the hashgraph containers' ID
3. exec into that container
docker exec -it YOUR_CHOSEN_CONTAINER_ID
4. check the StatsDemo logs
tail -f /usr/local/swirlds/sdk/StatsDemo*

If you know how to read the CSV file, you should be able to see the the throughput statistics of your Hashgraph network. I got 180k TPS on a modest laptop.
