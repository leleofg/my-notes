Como matar um processo no linux:

```
sudo kill -9 $(sudo lsof -t -i:4000)
```