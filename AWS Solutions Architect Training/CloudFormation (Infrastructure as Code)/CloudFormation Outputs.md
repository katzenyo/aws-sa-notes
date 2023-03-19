>[!Warning] On the Exam
> - Outputs section is accessible from a parent stack when using nesting
> - Outputs can be exported, allowing cross-stack referencing

- Outputs section is optional in templates
- Values are declared that are visible as outputs when using the CLI, console UI

## Examples

```YAML
Outputs:
  WordPressURL:
    Description: "Instance Web URL"
    Value: !Join ['', [ 'https://', !GetAtt Instance.DNSName ] ]
```