### Evaluation of free container scanners

|                          | [trivy][1]                                                                   | [semgrep][2] [^7] |
| :----------------------: | :--------------------------------------------------------------------------: | :---------------: |
| usability [^1]           | great [^2][^3]                                                               | great             |
| cve-2023-37466 [^4][^5]  | false negatives: no :sparkles: <br> false positives: many [^6] :grimacing:   | false negatives: yes [^8][^9] :grimacing: <br> false positives: no :sparkles: |

[^1]: how easy it is to scan a *local* image
[^2]: on windows with distributed sealed binary
[^3]: not so great on linux (built from source) - posted problems to trivy issues
[^4]: image contains a *single* reachable vulnerability
[^5]: image built with `Dockerfile` from [here][3]
[^6]: critical: 4, high: 109 - all of them irrelevant
[^7]: not a container scanner per se, but for dynamic languages it is very applicable
[^8]: posted to Semgrep issues [here][4]
[^9]: the vulnerable code was written *before* inspecting the Semgrep rule, *not* aiming to fail it

[1]: https://github.com/aquasecurity/trivy
[2]: https://semgrep.dev/
[3]: https://github.com/OrenGitHub/dhscanner.examples/tree/main/cve_2023_37466/example_00
[4]: https://github.com/semgrep/semgrep-rules/issues/3350
