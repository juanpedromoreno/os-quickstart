ERQX Play Framework QuickStart for OpenShift
--------------------

This is an Open Shift QuickStart that helps you get quickly up and running with an ERQX git based blog on OpenShift

* Create an account at https://www.openshift.com

* Install the RHC client tools if you have not already done so:

```bash
sudo gem install rhc
rhc setup
```

* Create an ERQX application providing a Git repo containing your static git based blog.
For a sample ERQX repo take a look at `https://github.com/jroper/allthatjazz.git` or any other jekyll based blog.

```bash
rhc app create myERQXBlog http://cartreflect-claytondev.rhcloud.com/reflect?github=tyrcho/openshift-cartridge-play2 GIT_REPO_BLOG={your-git-repo-blog-backend}
```

* Add the QuickStart repo as a remote and merge it into your app

```bash
cd myERQXBlog
git remote add upstream -m master https://github.com/47deg/ERQX-OpenShift-QuickStart.git
git pull -s recursive -X theirs upstream master
```

* Push your local changes

```
git push origin master
```

That's it. You have now an ERQX based blog running on top of Play Framework (v.2.3.3) on RedHat's OpenShift PAAS

http://myERQXBlog-`$yournamespace`.rhcloud.com
