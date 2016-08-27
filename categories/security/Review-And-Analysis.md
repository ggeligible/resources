### Security Code Review

### Static Analysis
Analyze programs source code without executing it with high coverage. Static analysis can thoroughly check limited but useful properties and helps in eliminating category of errors. It lets developer focus on deeper reasoning. Perfect static analysis is not possible but useful static analysis is possible despite:
* Non termination
* False alarms
* Missed alerts

[Soundness & Completeness](https://github.com/1989gaurav/resources/blob/master/categories/security/soundness-vs-completeness.png)


#### Analysis Design Tradeoffs
* Precision -  Minimize the false alarm
* Scaability
* Understandability - Alarms are easy to understand and action

#### Code Style
* Code style is important for static analysis
* If a code is easy to understand for human and follows conventions, then it should be easy for machine
* Always aim for good code, makes it easier to analyse

#### Flow Analysis
* Root cause of many attacks is trusting unvalidated input. No tainted data flow can catch missing input validations. For all possible inputs, prove that tainted data will never be used where untainted data is expected.


### Symbolic Execution
