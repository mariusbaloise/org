[![peribolos-sync-status](https://img.shields.io/travis/com/baloise/org/master?label=peribolos%20sync "periblos sync status")](https://travis-ci.com/github/baloise/org)

# org

We are using [Peribolos](https://github.com/kubernetes/test-infra/tree/master/prow/cmd/peribolos) to manage our GitHub org settings, teams and memberships in a [yaml file](config.yaml).

## Automation

Travis runs *peribolos* on every push to master.

### Full Config Dump

```bash
docker run --rm -v ~/peribolos-github-token:/etc/github/token gcr.io/k8s-prow/peribolos:latest \
  --dump baloise \
  --dump-full \
  --github-token-path /etc/github/token \
  > config.yaml
```

### Peribolos Help

```bash
docker run --rm gcr.io/k8s-prow/peribolos:latest --help
```
