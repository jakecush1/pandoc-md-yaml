# Community Profiles Pandoc demo

-> meta data in location.yaml file
-> indicator is markdown file

- navigate to a directory with files demographics_population.md and castlegar.yaml inside

- run command:
```
pandoc demographics_population.md --template demographics_population.md --metadata-file=castlegar.yaml
```

## will need to integrate pandoc-node api
- could use [node-pandoc](https://www.npmjs.com/package/node-pandoc)
