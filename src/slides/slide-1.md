class: center, middle

# Tour of Cookbook Development

---

# Design

 - does a cookbook already exist?  Laziness > Hubris
 - do we wrap the cookbook?
 - can we include directly in an existing role?
 - do we expect a new role?

???

No firm rules here, though do try to use well written and supported cookbooks
when available.  Wrapping is sometimes necessary if we wish to override
cookbook elements like templates though other methods exist.  Do consider the
interaction with the base roles already in common use

---

# Selecting a Community Cookbook

Lots of... not... good... cookbooks available.  How do we choose?

 - community behind cookbook- number of contributors and followers
 - documentation
 - plenty of attributes
 - does it have tests?
   - run through test-kitchen
 - look at the code itself
   - run through linters rubocop and foodcritic

---

# Check these out:

<img src="img/chef-splunk-cookbook.png"/>

---

# Check these out:

<img src="img/agent462-splunk-cookbook.png"/>

???

Presenter: now divert to a browser and compare the two

<a href="https://supermarket.chef.io/cookbooks/splunk">agent462's cookbook</a>

<a href="https://supermarket.chef.io/cookbooks/chef-splunk">Chef's cookbook</a>

Note that Chef's version has significantly more options and attributes.  May be more flexible than agent462's.  However, the Chef cookbook will likely be more complicated to implement.


---
