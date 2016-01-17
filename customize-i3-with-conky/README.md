Customizing i3's status bar with conky
=====

**Prerequisites**

Before starting with this,

1. you need to have the basic i3 configuration done, as described in the i3's documentation [here](https://i3wm.org/docs/userguide.html#configuring).

2. you need to have "conky" installed. Installation instructions can be found in the [project's website](https://github.com/brndnmtthws/conky/wiki/Installation).

3. be forewarned that this is my personal setup, which works in Ubuntu. I have never tried this in any other Linux distributions. So, I disown any responsibilities for the damages caused by this, and I shall not be held responsible.

---

**Steps**

Now, first copy the `conky-wrapper` and `.conkyrc` files in this directory, to your home directory, with these Steps

```
$ cd ~
$ wget https://raw.githubusercontent.com/thefourtheye/ubuntu-setups/master/customize-i3-with-conky/conky-wrapper
...
...
$ wget https://raw.githubusercontent.com/thefourtheye/ubuntu-setups/master/customize-i3-with-conky/.conkyrc
$ chmod 755 conky-wrapper
```

Open the i3 configuration file you set up from the first step in Prerequisites, and you will find the `bar` section like this

```
bar {
  status_command i3status
}
```

you need to change that to point to the location of the `conky-wrapper` file, like this

```
bar {
  # status_command i3status
  status_command <Home Directory path>/conky-wrapper
}
```

If you want to further configure the statusbar, you can use the variables listed in the [conky's page](http://conky.sourceforge.net/variables.html) in the `.conkyrc` file.
