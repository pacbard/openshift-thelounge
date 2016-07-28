The lounge on OpenShift
=========================

[The lounge](https://github.com/thelounge/lounge) is a free, open, always connected web IRC client.

Running lounge on OpenShift
--------------------

The easiest way to deploy lounge on OpenShift is with the [Client Tools](https://developers.openshift.com/en/managing-client-tools.html).

Start by creating a Node.js application:

    rhc app create <appname> https://raw.githubusercontent.com/icflorescu/openshift-cartridge-nodejs/master/metadata/manifest.yml --from-code=https://github.com/pacbard/openshift-thelounge.git

Connect to your application remotely using SSH:

    rhc ssh <appname>

This setup assumes you want to run lounge in its private mode. You will need to create your lounge login:
    
    cd $OPENSHIFT_REPO_DIR
    ./lounge add <username>

Additionally, remove the default user (optional):

    ./lounge remove default
