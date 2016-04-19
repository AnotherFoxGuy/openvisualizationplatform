**Note that the directions on this page are likely to change many times in the future as the development status of Banshee and OpenVP change.**

# Building Banshee #

  1. Clone my Banshee git repository.  (`git clone git://gitorious.org/banshee/cdhowie-clone.git`)
  1. Check out the now-playing-hijack branch.  (`git checkout -b now-playing-hijack origin/now-playing-hijack`)
  1. Build and install Banshee.  Remember to run `./autogen.sh` first, and also to `rm -fr /usr/local/lib/banshee-1` if you have installed Banshee from source before.
  1. Note the lib directory where Banshee was installed (usually /usr/local/lib/banshee-1).  We will call this `$BANSHEE_LIBDIR` in the directions below.

# Building OpenVP #

  1. Check out the 0.0.1 branch of OpenVP.  (`git clone git://gitorious.org/openvp/openvp-mainline.git && cd openvp-mainline && git checkout -b 0.0.1 origin/0.0.1`)
  1. Build.  (`./autogen.sh && make`)
  1. Install.  (`make install` as root)
  1. Note the lib directory where OpenVP was installed (usually /usr/local/lib/openvp).  We will call this `$OPENVP_LIBDIR` in the directions below.

# Building Banshee.OpenVP #

  1. Check out Banshee.OpenVP.  (`git clone git://gitorious.org/openvp/banshee-openvp.git && cd banshee-openvp`)
  1. Build.  (`./autogen.sh && make`)
  1. Install.  (`make install` as root.)
  1. Note the lib directory where Banshee.OpenVP was installed (usually /usr/local/lib/banshee-openvp).  We will call this `$BANSHEE_OPENVP_LIBDIR` in the directions below.

# Telling Banshee to use Banshee.OpenVP #

Now everything is built and installed, but Banshee doesn't know that the Banshee.OpenVP addin exists.  The simplest way to fix this is to symlink Banshee.OpenVP and all of its dependencies into `$BANSHEE_LIBDIR` by running the command `ln -s $OPENVP_LIBDIR/*.dll $BANSHEE_OPENVP_LIBDIR/*.dll $BANSHEE_LIBDIR` using the information recorded from the above steps.  Usually you can just run `ln -s /usr/local/lib/openvp/*.dll /usr/local/lib/banshee-openvp/*.dll /usr/local/lib/banshee-1/` if you have installed everything at the default locations.

# Run Banshee #

At this point you should be all set.  Run `banshee-1` from a console and enjoy!