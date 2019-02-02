# MoKee contributors cloud generator

To build the jar, run the following:

    cd source/
    mvn package
    cp target/contributors-cloud-generator-1.0.jar ../lib/

If you make changes in `source/`, this will need to be re-built

If you have a local mirror of all the MoKee code repositories,
then you can reduce the processing time and additional storage space
required to build the cloud by telling the tool where your repository
exists; otherwise, it will download hundreds of GB of data. Reference
your local mirror by doing the following:

    export MIRROR_ROOT=/path/to/mirror

To generate the code, open a linux console and type:

    ./generate_wordcloud.sh

This will parse the commit logs in all the MoKee repos,
downloading as required, mix the data and generate a cloud.zip in the
output folder. This will take look long time the first time.

The file resources/well-known-accounts.txt allows merging multiple
Gerrit accounts into a single cloud entry. The format of this file
should match the name of the account and the list of known emails for
the account

    Name on Gerrit|nick|email1|email2|...

This project is based in a modified version of the
[kumo](https://github.com/kennycason/kumo) library.

Copyright © 2017-2019 The MoKee Open Source Project
