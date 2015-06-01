## The Spec
Each job listing begins with the following ordered, pipe-delimited metadata, followed by any number of paragraphs for further info. The unique string "metafriendly" is added to the post to let parsers know that it conforms to the spec
```
[Company name] | [Job title] | [location(s), semi-colon delimited] | [Remote/Onsite, semi-colon delimited] | [Full-Time/Part-Time/Intern] | [Citizen/Visa (optional type, semi-colon delimited)] | [Optional list of semi-colon delimited keywords]

[Additional Freeform Information] metafriendly
```

## Example
```
Acme Products | Test Engineer | Las Vegas, NV; Austin, TX | Onsite; Remote | Full-Time; Part-Time | Visa (H1B) | Tunnel Theory; Kinematics

Engineer needed to test prototype products. Must be able to lift and carry anvils. metafriendly
```

## Attribute Notes

* **Location:** Must be geocodable; Any string must give one unambiguous set of LatLng coordinates.
* **Onsite/Remote:** The word `Remote` should only be used in the positive sense; phrases such as `No Remote` are not allowed.
* **Citizen/Visa:** It can be assumed that by stating `Visa`, the job posting also accepts applicants that are `Citizen`, and `Citizen` can be omitted. Please note that this is not true for other attributes; it is possible for companies to look for Remote only applicants, or only Part-Time applicants.

## FAQ

**Why have a spec at all?**

To be better able to filter out irrelevant job listings. There are a number of third party sites that parse whoishiring information, but are unable to accurately do so because of inconsistent formatting. Most notably, false positives on `remote` work, being unable to accurately determine job location, and mistaking the keyword `intern` with international in job descriptions.

**Why not a more machine friendly format, like YAML?**

A line break after each attribute would balloon the vertical size of posts quite a bit, making the original page of posts not as useful.

**What if I don't want to share the company name?**

Put `Stealth Company` or something in the beginning.

## Acknowledgements

This pipe-delimited spec is mostly stolen from [this comment by danso](https://news.ycombinator.com/item?id=9635683)
