Shout on OpenShift
=========================

Shout is a free, open, always connected web IRC client.

Running Shout on OpenShift
--------------------

The easiest way to deploy Shout on OpenShift is with the [Client Tools](https://developers.openshift.com/en/managing-client-tools.html).

Start by creating a Node.js application:

    rhc app create <appname> nodejs-0.10 --from-code=https://github.com/Kornagan/openshift-shoutirc.git

Connect to your application remotely using SSH:

    rhc ssh <appname>

This setup assumes you want to run Shout in its private mode. You will need to create your Shout login:
    
    cd $OPENSHIFT_REPO_DIR
    ./shout add <username>

Additionally, remove the default user (optional):

    ./shout remove default