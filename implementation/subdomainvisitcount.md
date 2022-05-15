# Sub-domain Visit Count

## Problem

> Medium

A website domain `"discuss.leetcode.com"` consists of various subdomains. At the top level, we have `"com"`, at the next level, we have `"leetcode.com"` and at the lowest level, `"discuss.leetcode.com"`. When we visit a domain like "discuss.leetcode.com", we will also visit the parent domains `"leetcode.com"` and `"com"` implicitly.

A count-paired domain is a domain that has one of the two formats `"rep d1.d2.d3"` or `"rep d1.d2"` where rep is the number of visits to the domain and `d1.d2.d3` is the domain itself.

- For example, `"9001 discuss.leetcode.com"` is a count-paired domain that indicates that `discuss.leetcode.com` was visited `9001` times.

Given an array of count-paired domains cpdomains, return an array of the count-paired domains of each subdomain in the input. You may return the answer in any order.

### Example 1

```
Input: cpdomains = ["9001 discuss.leetcode.com"]
Output: ["9001 leetcode.com","9001 discuss.leetcode.com","9001 com"]
Explanation: We only have one website domain: "discuss.leetcode.com".
As discussed above, the subdomain "leetcode.com" and "com" will also be visited. So they will all be visited 9001 times.
```

### Example 2

```
Input: cpdomains = ["900 google.mail.com", "50 yahoo.com", "1 intel.mail.com", "5 wiki.org"]
Output: ["901 mail.com","50 yahoo.com","900 google.mail.com","5 wiki.org","5 org","1 intel.mail.com","951 com"]
Explanation: We will visit "google.mail.com" 900 times, "yahoo.com" 50 times, "intel.mail.com" once and "wiki.org" 5 times.
For the subdomains, we will visit "mail.com" 900 + 1 = 901 times, "com" 900 + 50 + 1 = 951 times, and "org" 5 times.
```

---

## Solution

```JavaScript
var subdomainVisits = function (cpdomains) {
  const domainObj = {}; // Initiate an empty object
  for (let i = 0; i < cpdomains.length; i++) {
    let [visitCount, domain] = cpdomains[i].split(" "); // split contents of array into count of visits and domains;
    let domains = []; // Initiate empty array to push all the domains that was split
    let dot = domain.indexOf("."); // Find the first index of the "." in the domain name
    while (dot > -1) {
      domains.push(domain); // Add domains into the empty array
      domain = domain.slice(dot + 1, domain.length); // After adding slice the domain after the first "." to get the next substring
      dot = domain.indexOf("."); // Get the next index of "." from the sliced subdomain and while "." is not null, it keeps running the while loop and adding the sliced domain to the array
    }
    domains.push(domain); // Adds the last substring after the "." becomes null
    domains.forEach((domain) => {
      if (!domainObj[domain]) {
        // Loop through the domain add domain as a key to the empty object domainMap and intiate it with value 0;
        domainobj[domain] = 0;
      }
      domainObj[domain] += parseInt(visitCount); // Add the sum of visitCount as the value
    });
  }
  const result = []; // initiate an empty array for final result

  for (let key in domainObj) {
    result.push(`${domainObj[key]} ${key}`); // loop through the object and push value and key as a string into the array
  }

  return result;
};
```

---
