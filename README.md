#sshconfig2iterm

This will convert ssh config files (locationed at ~/.ssh/config) to [iTerm2 Dynamic Profiles](https://www.iterm2.com/dynamic-profiles.html).

### Example Config Mapping

##### ~/.ssh/config
```
Host sample # Example Server
  #Tags server, example
  User testuser
  HostName example.com
```

Will convert to:

#####profile.json
```
{
  "Profiles": [
    {
      "Guid": "sample",
      "Name": "Example Server",
      "ShortCut": "",
      "Custom Command": "Yes",
      "Command": "ssh sample",
      "Tags": [
        "server",
        "example"
      ]
    }
  ]
}
```

The Name is first taken from the '#Label' paramter. If this isn't found it'll grab it from the Comment on the same line of the host. It falls back to the Host parameter.
