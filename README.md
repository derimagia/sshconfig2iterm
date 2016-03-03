#sshconfig2iterm

This will convert ssh config files (located at ~/.ssh/config) to [iTerm2 Dynamic Profiles](https://www.iterm2.com/dynamic-profiles.html).

Because this is for iTerm, this will only work on Mac.
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
