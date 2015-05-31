## The Spec
Each job listing begins with the following ordered pipe delimited metadata, followed by any number of paragraphs for further info. The unique string "metafriendly" is added to let parsers know that it conforms to the spec
```
[Company name] | [Job title] | [location(s), semi-colon delimited, "(Remote OK)", if applicable] | [Full-Time/Part-Time/Intern] | [Citizen/Visa (optional type, semi-colon delimited)] | [Optional list of semi-colon delimited keywords]

[Additional Freeform Information] metafriendly
```

## Example
```
Acme Products | Test Engineer | Las Vegas, NV; (Remote OK) | Full-Time; Part-Time | Visa (H1B) | Tunnel Theory; Kinematics

Engineer needed to test prototype products. Must be able to lift and carry anvils. metafriendly
```

## Attribute Notes

* **Location:** Must be geocodable; Any string (with the exception of `(Remote OK)`) must give one unambiguous set of LatLng coordinates. The words `(Remote OK)` should only be used in the positive sense; phrases such as `(Remote Not OK)` or `(No Remote)` are not allowed.

## FAQ

**Why have a spec at all?**

To be better able to filter our irrelevant job listings. There are a number of third party sites that parse whoishiring information, but are unable to accurately do so because of inconsistent information. Most notably, false positives on `remote` work, being unable to accurately determine job location, and mistaking the keybord `intern` with international in job descriptions.

**Why not a more machine friendly format, like YAML?**

A line break after each attribute would balloon the vertical size of posts quite a bit, making the original page of posts not as useful.

## Acknowledgements

This pipe-delimited spec is mostly stolen from [this comment by danso](https://news.ycombinator.com/item?id=9635683)
