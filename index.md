---
layout: default
---

# Creating a Security Information and Event Manager (SIEM)

We are going to create our SIEM with Microsoft Azure

#Step 1 Creating our VM 

First, we want to create our Windows 10 pro Virtual Machine and name our resource group. (Naming a group now will create one automatically.) 
![Branching](VM creation.png)

The most important part of our simulation is allowing all RDP ports. We are using a default username and random password for our credentials. 

![Branching](VM creation 2.png)

Now, we just click through to allow Azure to create the default settings until we reach our networking page. Here, we ensure that we enable port 3389.  

![Branching](vm creation 4.png)

This is what our final review page should look like.

![Branching](VM creation final.png)

#Step 2 Setting up Microsoft Sentinel

In our search bar, we type in Mircosoft Sentinel and create our workspace. We click our resource group and name our Log Analytics workspace.

![Branching](creating log analytics .png)

After creating the Log analytics, we click add to connect it in our workplace.

![Branching](adding sentital to our workspace.png)

Now, we need a way to send our VM's data to Microsoft Sentinel. We accomplish this goal with a data connector. We can set one up by navigating our Sentinel page. 

![Branching](sential data connector confiig.png)

There are many connector options; for my SIEM, I am using Windows Security Events. 

![Branching](selecting our data connector.png)

Next, we configure our data connector. On our configuration page, we have two options. The legacy option is discontinued so select Windows Security Events via AMA. 

![Branching](connector 2.png)

Now, that our connector is configured we can set it up properly by creating a collection rule. This will help use filter out our data.
![Branching](settingupconnector 1.png)

We need to select our VM and our resource group and the rule will be created

![Branching](settingupconnector2.png)

We can access our rule and see all of the data that is coming into our log analytics. 

![Branching](rulescreation1.png)

In our query, we type in our code to only show what activity contains a successful connection via RDP. 

![Branching](rulecreation2.png)

These are our settings. We are going to name our rule successful local sign ins. 

![Branching](rulecreation3.png)

Our overview page should look like this. We see our rule created here and a default rule created by Azure.

![Branching](rulecreation4.png)

Finally, I am going to use RDP to sign in remotely to the VM with another device. Here, we can see that our login triggered our rule and gave us a notification. 

![Branching](incident response successful.png)

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```
