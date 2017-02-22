# D4a5

1. Explain what is checksum and the importance of checksum and how hadoop performs checksum.

A checksum is a small-sized datum from a block of digital data.
The checksum algorithm is used to calculate the checksum given data as input.A good checksum algorithm will usually output 
a significantly different value, even for small changes made to the input.

Importance of checksum:

The purpose of checksum is detecting errors which may have been introduced during its transmission or storage.
Instead of comparing large blocks of data we can compare respective checksums to check if the data is tampered.
Checksum plays an important role to verify data integrity.
 if the computed checksum for the current data input matches the stored value of a previously computed checksum, then there is
 high probability that the data is not altered.
 Checksum reduces the time and processing required to check the integrity of the data.
 
 Hadoop checksums:
 
 As hadoop stores big data ,it is a challenge to ensure the integrity of such huge bulk of data.
 Users of Hadoop expect that no data will not be corrupted during storage or processing.However, when the volumes of data flowing through the system are as large,there are chances of data corruption.
 The checksum is a way to find out if data blocks are tampered in order to ensure the integrity of the data stored in hadoop.
The HDFS transparently checksums all data written to it and by default verifies checksums when reading data. A separate checksum is created for every io.bytes.per.checksum bytes of data.
When data node recieves the data from the client and also during data replication,data nodes verify the data before they store the data and corresponding checksum.The client data is verified again when client wants to read the data from data node.If checksum is changed i means the data is altered.
But as HDFS stores replicas of the data this problem can be overcomed by copying the good replica of the data.
