# 🏪 Amazon S3

## What Is It?

Amazon S3 is the most popular file storage service available. It provides a relatively simple way to create buckets of files to serve your files from.

{% embed url="https://www.youtube.com/watch?v=e6w9LwZJFIA" %}

## What Are The Benefits?

* **Uptime** - Data is accessible 99.99999% of the time. Outages are exceedingly rare.
* **All-In-One** - Amazon web services have a lot of power user options outside of just S3
* **Common** - Using S3 for file storage is the default option used by most developers

## Data Ownership

Most companies will either have or need to have their own Amazon organization account setup. From that organization, external developer accounts can be provided specific permissions as needed to access Amazon S3 services.

Gaining upload and edit rights to Amazon S3 for an organization is one of the starting requirements of most contracts.

## Usage Guide

Check out [Amazon's official S3 documentation](https://aws.amazon.com/pm/serv-s3/?trk=fecf68c9-3874-4ae2-a7ed-72b6d19c8034\&sc\_channel=ps\&s\_kwcid=AL!4422!3!536324446683!p!!g!!amazon%20s3\&ef\_id=CjwKCAjwsMGYBhAEEiwAGUXJaWLSPfmlAWvUjjnawVLre8muPzwfOQMT3fZ6P2dtDaeRJ1\_pqPCk4BoCX6oQAvD\_BwE:G:s\&s\_kwcid=AL!4422!3!536324446683!p!!g!!amazon%20s3) as well as the video below.

{% embed url="https://www.youtube.com/watch?v=R17izV8kCzE" %}

## Security

It's generally recommended that buckets in S3 default to being private, with permissions to read and write files being given to specific users and for only certain files and folders.

For public assets, such as website files, create a specific bucket for those files that will be separate from all others.

{% embed url="https://www.youtube.com/watch?v=weBOwG9cuZ0" %}

