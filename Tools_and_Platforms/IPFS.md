# IPFS : InterPlanetary FileSystem

our problem in web :

    - the information on it is centralized.
    - is cencorship.
    because content is hosted on just a few servers and the government easily can access to them.

but is good too:

    - fast deliver.
    - always is in access.

### location base addressing

we tell the computer where to get the information but if that location isn't accessible,
when the server is down we can't get that file.

when we want to download a file like photo from the internet we tell the computer
exactly where to find the photo.

location of the photo : is the ip address or domain name.

### content base addressing

for solve the location base addressing ipfs move to content based addressing.

so we don't want the location and we don't say where is the file.
instead we say what we want???

### content base work

every file has a unique hash, witch can be compared to a fingerprint.
so when we want the file we call the network who has the file with this hash?
so the someone on ipfs network can provide it to us.

how do we know that, that person hasn't tampered
with the file?

with the hash of the file we have, we can verify what we have received.
it's a built-in security.

## IPFS Stores Files and makes them accessible to others

files are stored inside ipfs objects and these objects can store up to 256kb
worth of data and can contain links to other IPFS objects.

### what about objects more than 256kb?

those are splite up into multiple IPFS objects that are all 256kb in size and afterwards
and the system will create an empty IPFS object that links to all the other pieces of the
file.

### how do we change stuff on it?

IPFS supports versioning of our files.

this object tells IPFS witch commit went before it and it links to the IPFS object of our files.
when we want to update our file we add the updated file in the IPFS network and the software
will create a new commit object for our file.
this commit object now links to the previous commit and this process
can be repeated endlessly.

IPFS will make sure that our file, plus it's entire history is accessible to the other nodes
on the network.

## IPFS Problems

the biggest problem that IPFS faces is keeping files available.

every node on the network keeps a cache of the files that it has downloaded and helps
to share them if other people need them.

but if a specific file is hosted by like we can say 4 nodes and those nodes go offline,
then that file becomes unavailble and no one can grab a copy of it.

## Problem solution

    -Incentivize nodes:
        incentivize people to store files and make them available

    -Proactively distribute files:
        we can proactively distribute files and make sure that there are
        always a certain number of copies available on the network.
        like FileCoins.

## Filecoin

it's basically a blockchain built on top of IPFS that wants to create a decentralized market
for storage.

if we have some free space on our harddrive, we can rent it out to others and make money of it
in the process.

Filecoin creates a strong incentive for nodes to keep the files online for as long as possible
because otherwise they won't be rewarded.

the system makes sure that files are replicated on many nodes so they cannot become unavailable.
