# Logging

## Logging Best Practices for APIs

For all APIs, the logging should use the abstract implementation through the SLF4j API/Interface (JAVA).

### Log keys

| Key       | Source                   | Description                                                          |
| --------- | ------------------------ | -------------------------------------------------------------------- |
| Service   |                          | Application/Service Name                                             |
| timestamp | System Time              | Format in epoch including milliseconds                               |
| Level     | Log Level                | Current log level                                                    |
| Trace Id  | Sleuth Generated         | Tracks single request, could be passed across services for tracking. |
| Span Id   | Sleuth Generated         | Represent basic unit of work                                         |
| message   | Log Message with context | Actual Log message                                                   |

### Log Level

| Log Level | Description                                                                                   |
| --------- | --------------------------------------------------------------------------------------------- |
| TRACE     | Finer-grained informational events than the DEBUG                                             |
| DEBUG     | Fine-grained informational events that are most useful to debug an application                |
| INFO      | Informational messages that highlight the progress of the application at coarse-grained level |
| WARN      | Potentially harmful situations                                                                |
| ERROR     | Error events that might still allow the application to continue running                       |
| FATAL     | Very severe error events that will presumably lead the application to abort                   |

_For all API's the logging should use the abstract implementation through SLF4J API/Interface (JAVA)_

### Best Practices

#### Write meaningful log message and add context to the messages

Messages are most valuable with added context:

- Transaction 2346432 failed: cc number checksum incorrect
- User 54543 successfully registered e-mail user@domain.com
- IndexOutOfBoundsException: index 12 is greater than collection size 10

:::danger[Following are examples for incorrect logging]
- "Transaction failed"
- "User operation succeeds"
- "java.lang.IndexOutOfBoundsException"
:::

Without proper context, those messages are only noise; they don’t add value and consume space that could have been useful during troubleshooting.

#### Don't log sensitive information.

Following are a few examples of sensitive/PII/SPII information which should be avoided:

- SSN
- Passwords
- Bank Account Numbers

#### Don't log for troubleshooting purposes only

Just as log messages can be written for different audiences, log messages can be used for different reasons. Even though troubleshooting is the most evident target of log messages, you can also use log messages very efficiently for:

- **Auditing:** This is sometimes a business requirement. The idea is to capture significant events that matter to the management or legal people.
- **Profiling:** As logs are timestamped (sometimes to the millisecond level), they can become a good tool to profile sections of a program.
- **Statistics:** If you log each time a certain event happens (like a certain kind of error or event), you can compute interesting statistics about the running program (or user behaviors). It’s also possible to hook this to an alert system that can detect too many errors in a row.

#### Don't Log Too Much or Too Little

Too much log and it will really become hard to get any value from it. When manually browsing such logs, there is too much clutter, which when trying to troubleshoot a production issue at 3 AM is not a good thing.

Too little log and you risk not being able to troubleshoot problems: troubleshooting is like solving a difficult puzzle; you need to have enough material for this.

Unfortunately, there is no magic rule when coding to know what to log. Make a proper judgement to remove all the noise from the logs and keep the remaining.

#### Employ log levels correctly.

It is important to use correct logging levels at the right place/environment. It might make sense to have more logging in a pre-production environment as compared to production. One of the strategies used is to use DEBUG in Pre-Prod and have INFO in Prod. There are many other strategies which could fit your needs; feel free to explore and incorporate those.
