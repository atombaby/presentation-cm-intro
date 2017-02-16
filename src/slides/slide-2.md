# What needs to happen?

 - install Splunk distribution
 - configure
 - start services

---

# Wrapping the Cookbook

Wrapping a cookbook:

 - create a new cookbook
 - include the cookbook to be wrapped
 - customize as necessary

## Create the cookbook from boilerplate:

```
chef generate cookbook splunk-forwarder
cd splunk-forwarder
git checkout -b prod
git checkout -b dev
git branch -d master
```

---

## Add to GitHub

```
git remote add origin <url>
git push -u origin
```

## Add Automation:

 - Create project in [Jenkins](http://whidby.fhcrc.org/job/scicomp-cookbooks)
   (copy an existing one like scicomp-desktop)
 - Install the
   [automatic-garbanzo](https://github.com/FredHutch/automatic-garbanzo) at the
   top level of the wrapper

```
curl -L https://github.com/FredHutch/automatic-garbanzo/archive/2.1.0.tar.gz | tar -xzv --strip-components=1 -f -
```

## Add cookbook to metadata.rb:

```
grep depends metadata.rb
depends 'chef-splunk', '~> '1.6.0'
```

---

## Linting

```
rake test
```

## Converging

```
kitchen converge
```

---

## Build and Publish

```
git checkout prod
git merge --ff-only dev
# edit metadata.rb, update version as necessary
git push
git checkout dev
git merge --ff-only dev
```

Pushing on the branch `prod` will trigger jenkins to tag and upload artifacts
to Chef and Supermarket servers

