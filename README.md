# org

We are using [Peribolos](https://github.com/kubernetes/test-infra/tree/master/prow/cmd/peribolos) to manage our GitHub org settings, teams and memberships in a [yaml file](config.yaml).

## Automation

*peribolos* runs on every push to main and every PR to main (dry-run).

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
