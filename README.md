lounge on OpenShift
=========================

lounge is a free, open, always connected web IRC client.

Running lounge on OpenShift
--------------------

The easiest way to deploy lounge on OpenShift is with the [Client Tools](https://developers.openshift.com/en/managing-client-tools.html).

Start by creating a Node.js application:

    rhc app create <appname> nodejs-0.10 --from-code=https://github.com/tomnx/openshift-loungeirc.git

Connect to your application remotely using SSH:

    rhc ssh <appname>

This setup assumes you want to run lounge in its private mode. You will need to create your lounge login:
    
    cd $OPENSHIFT_REPO_DIR
    ./lounge add <username>

Additionally, remove the default user (optional):

    ./lounge remove default
