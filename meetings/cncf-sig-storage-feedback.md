# CNCF Sig-Storage Review Feedback

CNCF sig storage has done the Dragonfly incubation review. The meeting was recorded in https://www.youtube.com/watch?v=Sl7ZDt7rx4M .

Here lists sig storage team's questions and suggestions:

Q: Can Dragonfly be used for all kinds of general files and image's distribution?
A: Yes, basically anything

Q: docker daemon could be configured to use a proxy to pull images via Dragonfly, but just Docker? You mentioned containerd, is it supported as well?
A: Yes, containerd is supported. It is quite to support containerd. We just need to configure a parameter of containerd, make it to pull images from the proxy dfdaemon, dfdaemon would send pull requests to dfget. We support docker, containerd, and other container engines.

Q: In your architecture, you take Harbor as an example. But if it is not Harbor, could it be any image registries?
A: Yes, It could be other registries.

Q: How does the p2p node ensure that the downloaded block is consistent with the source file. For example, if a peer node crashes, how can other nodes ensure that the downloaded data is correct.
A: The supernode will slice the file and calculate the md5 value of each slice and the md5 value of the entire file. When the supernode schedules a node to download a fragment from another node, it also tells the node the md5 value of the fragmentation data. If the node downloads the fragmentation data, the checked md5 does not match, or from another. If the peer download fails, it will be reported to the supernode. The supernode will add too many nodes to the blacklist. The next time the scheduling is performed, the problem node will be ignored. When the client downloads the complete file, it also verifies the md5 value of the entire file, so that the data downloaded by each peer is consistent and correct through double-layer verification.

Q: Dragonfly uses the p2p network, but it sounds like everything is downloaded via supernode? If the client downloads the image, will all the data flow through the supernode?
A: No. The supernode will preferentially schedule the peers of the existing data for use by other peers that need to download. If there is no fragmentation data in the entire p2p network, the supernode will dispatch itself to the peer for download, but will set the threshold to only allow the number of nodes in the threshold range to be downloaded at the same time.

Q: Is the client eventually pulling data from the p2p network, not from the supernode?
A: Yes, you are right.

Q: How to manage the version of the slice code
A: The slice header reserves 3 bits, which can be used in the future when the version changes.

Q: 24-bit indicates the size of the fragmented data, but only 4 bits indicate the fragment size. It seems that the 24-bit can represent more than 15MB.
A: The slice includes 4 bytes of block header, block data, and 1 block of block tail. The size of the whole slice is represented by 4 bits, and the size ranges from [1, 15 ] MB; fragment data size is represented by 24 bit bits, unit byte, range [0, 15 * 1024 * 1024-5] bytes; the current fragment size will not exceed 15MB.