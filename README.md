## The Spec
Each job listing begins with the following pipe delimited metadata, followed by any number of paragraphs for further info. The unique string "metafriendly" is added to let parsers know that it conforms to the spec
```
[Company name] | [Job title] | [location(s), semi-colon delimited] ["(Remote OK)", if applicable] | [Full-Time/Part-Time/Intern/Visa/Remote | [Optional list of semi-colon delimited skills]

[Additional Freeform Information] metafriendly
```

## Example
```
Acme Products | Test Engineer | Las Vegas, NV; (Remote OK) | Full-Time | Data Science

Engineer needed to test prototype products. Must be able to lift and carry anvils. metafriendly
```
