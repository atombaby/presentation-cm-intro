---

# Now Make it Work

 - currently does nothing- `include_recipe` merely makes resources available
 - add a recipe to install the forwarder:

```
chef generate recipe forwarder
```

 - reading cookbook docs, we see we have a recipe called `install_forwarder`

```
cat recipes/forwarder.rb
# Cookbook Name:: 
# Recipe:: install_forwarder

include_recipe 'chef-splunk::client'
```

This will run the recipe from the wrapped cookbook.  Now we need to fiddle with
the install

---

# Attributes

Good recipes use attributes- in this case we need to set:

 - `node['splunk']['accept_license']`
 - `node['splunk']['server']['url']`
 - `node['splunk']['forwarder']['url']`
 - `node['splunk']['outputs_conf']`
 - ?

---
