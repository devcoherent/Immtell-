# Immtell — Schema Markup QA Report

Site: Immtell (immtell.webflow.io) · Canonical domain: https://immtell.com · Locale: English only · Custom domain: নেই

Data source: Webflow MCP (page schema settings, page/site custom code, registered scripts, CMS items) + published HTML (Ahrefs crawl, 23 Oct 17:07 UTC) visible content match এর জন্য।


## Site-wide সমস্যা (batch fix)

| সমস্যা | Severity | কোথায় | সংখ্যা |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | 214 |
| Organization logo unified (PNG) | Warning | একই Organization entity তে দুই রকম logo (SVG/PNG) — site-wide inconsistency | 54 |
| NewsArticle: added image from CMS featured-image | Warning | Article এ image নেই (Google recommended); CMS featured-image আছে | 21 |
| Organization identifier unified | Improvement | identifier এর format অন্য page থেকে আলাদা | 16 |
| Organization url normalised | Improvement | Organization url অন্য page থেকে আলাদা (trailing slash) | 16 |
| Organization: added logo | Improvement | এই page এর Organization node এ logo/sameAs ছিল না, বাকি site এ আছে | 16 |
| Organization: added sameAs | Improvement | এই page এর Organization node এ logo/sameAs ছিল না, বাকি site এ আছে | 16 |
| WebSite url normalised | Improvement | WebSite url অন্য page থেকে আলাদা | 16 |
| Gavin url -> profile page | Warning | jobTitle/url অন্য page ও profile page থেকে আলাদা | 14 |
| Gavin jobTitle unified | Warning | jobTitle/url অন্য page ও profile page থেকে আলাদা | 13 |
| breadcrumb: removed non-existent /business/sectors level | Critical | /business/sectors নামে কোনো page নেই (404) | 13 |
| Article: added image from CMS featured-image | Warning | Article এ image নেই (Google recommended); CMS featured-image আছে | 5 |
| Ewen jobTitle = visible "Head of Sponsor Compliance" | Warning | Page এ দেখানো title "Head of Sponsor Compliance", schema তে আলাদা | 3 |
| removed consultation offers (prices not shown on page) | Critical | Consultation এর দাম (£55/£150/£280) page এ দেখানো নেই — content mismatch | 2 |
| Ewen: added sameAs | Warning | Page এ দেখানো title "Head of Sponsor Compliance", schema তে আলাদা | 2 |
| removed 4 self-serving Review nodes | Critical | নিজের ব্যবসার নিজের site এ review markup — Google self-serving review policy | 1 |
| FAQ answer matched to page (£135) | Critical | Schema তে "135 pounds", page এ "£135" | 1 |
| apply-for-a-sponsor-licence page এ পুরনো registered script `schemaApplySponsorLicence` load হচ্ছে (duplicate/পুরনো schema inject করতে পারে) | Critical | Page → Custom code → registered scripts | 1 |
| 16টা Resources BlogPosting এ datePublished নেই এবং CMS `published-date` ফাঁকা | Warning | CMS Resources → published-date | 16 (manual: আসল তারিখ লাগবে) |

## Static pages

### /individuals/uk-immigration-consultation
- **URL:** https://immtell.com/individuals/uk-immigration-consultation · **Type:** Service · **Webflow page:**  (`6abeb1799a92e8d05f2b3260`)
- **বর্তমান অবস্থা:** JSON valid, schema types: Answer, Audience, BreadcrumbList, ContactPoint, Country, FAQPage, ImageObject, ListItem, Offer, Organization, Person, PostalAddress, PriceSpecification, ProfessionalService, PropertyValue, Question, Service, ServiceChannel, WebPage, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb; ❌ FAQ rich result (Aug 2023 থেকে শুধু govt/health site) — schema valid, AI/semantic এর জন্য রাখা হয়েছে

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/individuals/uk-immigration-consultation#webpage",
      "@type": "WebPage",
      "about": {
        "@id": "https://immtell.com/individuals/uk-immigration-consultation#service-page"
      },
      "breadcrumb": {
        "@id": "https://immtell.com/individuals/uk-immigration-consultation#breadcrumb"
      },
      "description": "Book a paid UK immigration consultation with a former Home Office officer. Clear, fixed fees: 15 minutes £55, 30 minutes £150, 60 minutes £280, all plus VAT.",
      "inLanguage": "en-GB",
      "isPartOf": {
        "@id": "https://immtell.com/#website"
      },
      "mainEntity": {
        "@id": "https://immtell.com/individuals/uk-immigration-consultation#service-page"
      },
      "mentions": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "name": "UK Immigration Consultation Fees | Immtell",
      "url": "https://immtell.com/individuals/uk-immigration-consultation"
    },
    {
      "@id": "https://immtell.com/individuals/uk-immigration-consultation#service-page",
      "@type": "Service",
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "audience": {
        "@type": "Audience",
        "audienceType": "Individuals seeking UK visa, settlement or citizenship advice"
      },
      "availableChannel": {
        "@type": "ServiceChannel",
        "name": "Zoom video consultation"
      },
      "description": "A paid one-to-one UK immigration advice session on Zoom with Gavin Webster, a former Home Office officer, covering visa, settlement and citizenship options before you apply.",
      "name": "UK Immigration Consultation",
      "offers": [
        {
          "@type": "Offer",
          "description": "Best for quick, specific questions: clarification on a single visa rule or eligibility point.",
          "name": "15-Minute Consultation",
          "price": "55",
          "priceCurrency": "GBP",
          "priceSpecification": {
            "@type": "PriceSpecification",
            "price": "55",
            "priceCurrency": "GBP",
            "valueAddedTaxIncluded": false
          },
          "seller": {
            "@id": "https://immtell.com/#organization"
          },
          "url": "https://immtell.com/individuals/uk-immigration-consultation"
        },
        {
          "@type": "Offer",
          "description": "Best for moderate complexity, with time to talk through options and next steps without feeling rushed.",
          "name": "30-Minute Consultation",
          "price": "150",
          "priceCurrency": "GBP",
          "priceSpecification": {
            "@type": "PriceSpecification",
            "price": "150",
            "priceCurrency": "GBP",
            "valueAddedTaxIncluded": false
          },
          "seller": {
            "@id": "https://immtell.com/#organization"
          },
          "url": "https://immtell.com/individuals/uk-immigration-consultation"
        },
        {
          "@type": "Offer",
          "description": "Best for complex matters needing a detailed review of your circumstances and a clear plan.",
          "name": "60-Minute Consultation",
          "price": "280",
          "priceCurrency": "GBP",
          "priceSpecification": {
            "@type": "PriceSpecification",
            "price": "280",
            "priceCurrency": "GBP",
            "valueAddedTaxIncluded": false
          },
          "seller": {
            "@id": "https://immtell.com/#organization"
          },
          "url": "https://immtell.com/individuals/uk-immigration-consultation"
        }
      ],
      "provider": {
        "@id": "https://immtell.com/#organization"
      },
      "serviceType": "Paid UK immigration consultation",
      "url": "https://immtell.com/individuals/uk-immigration-consultation"
    },
    {
      "@id": "https://immtell.com/individuals/uk-immigration-consultation#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/home-individual",
          "name": "Individuals",
          "position": 2
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/individuals/uk-immigration-consultation",
          "name": "UK Immigration Consultation",
          "position": 3
        }
      ]
    },
    {
      "@id": "https://immtell.com/individuals/uk-immigration-consultation#faq",
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. All consultations with Immtell are strictly confidential. Your personal information and immigration circumstances are not shared with third parties."
          },
          "name": "Are UK immigration consultations confidential?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. Immtell is regulated by the Immigration Advice Authority (IAA, formerly OISC), Registration No. F202200109, and is on the IAA register. In the UK, immigration advice can only be given legally by an IAA or SRA registered firm."
          },
          "name": "Are you regulated to provide UK immigration advice?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "No. Because of the volume of enquiries, Immtell does not provide free immigration advice. A paid consultation gives you personalised guidance from a former Home Office officer."
          },
          "name": "Do you offer free UK immigration advice?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "£55 plus VAT for 15 minutes, £150 plus VAT for 30 minutes, or £280 plus VAT for 60 minutes. Payment confirms your appointment."
          },
          "name": "How much does a consultation cost?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "15 minutes for a single, specific question, 30 minutes (most popular) for a situation with a few moving parts, and 60 minutes for complex matters needing a full discussion."
          },
          "name": "Which session length should I choose?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes, with at least 24 hours’ notice. Late cancellations or missed appointments may incur a fee."
          },
          "name": "Can I cancel or reschedule my consultation?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The consultation focuses on guidance on your options and eligibility. Detailed document reviews are carried out as part of full application support if you later instruct Immtell."
          },
          "name": "Can you review my documents during the consultation?"
        }
      ]
    }
  ]
}
```
</details>

### /resources/glossary
- **URL:** https://immtell.com/resources/glossary · **Type:** Glossary · **Webflow page:**  (`6a9d78cef0c4f20f0449ec6b`)
- **বর্তমান অবস্থা:** JSON valid, schema types: BreadcrumbList, ContactPoint, Country, DefinedTerm, DefinedTermSet, ImageObject, ListItem, Organization, Person, PostalAddress, ProfessionalService, PropertyValue, WebPage, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/resources/glossary#webpage",
      "@type": "WebPage",
      "about": {
        "@id": "https://immtell.com/#organization"
      },
      "breadcrumb": {
        "@id": "https://immtell.com/resources/glossary#breadcrumb"
      },
      "description": "UK immigration is full of acronyms and technical terms. This glossary explains the ones you are most likely to come across, in plain English.",
      "inLanguage": "en-GB",
      "isPartOf": {
        "@id": "https://immtell.com/#website"
      },
      "mainEntity": {
        "@id": "https://immtell.com/resources/glossary#glossary"
      },
      "name": "Immigration Glossary",
      "url": "https://immtell.com/resources/glossary"
    },
    {
      "@id": "https://immtell.com/resources/glossary#glossary",
      "@type": "DefinedTermSet",
      "description": "UK immigration is full of acronyms and technical terms. This glossary explains the ones you are most likely to come across, in plain English.",
      "hasDefinedTerm": [
        {
          "@type": "DefinedTerm",
          "description": "An electronic record, not a physical certificate, that a licensed sponsor assigns to a worker they wish to employ. The worker uses its reference number to apply for their visa.",
          "inDefinedTermSet": {
            "@id": "https://immtell.com/resources/glossary#glossary"
          },
          "name": "Certificate of Sponsorship (CoS)"
        },
        {
          "@type": "DefinedTerm",
          "description": "A fine issued to an employer who is found to have employed someone without the right to work in the UK. Penalties are set per worker and increase for repeat breaches.",
          "inDefinedTermSet": {
            "@id": "https://immtell.com/resources/glossary#glossary"
          },
          "name": "Civil Penalty"
        },
        {
          "@type": "DefinedTerm",
          "description": "A check carried out by the Home Office to confirm a sponsor is meeting its duties. It can be announced or unannounced, and may happen before or after a licence is granted.",
          "inDefinedTermSet": {
            "@id": "https://immtell.com/resources/glossary#glossary"
          },
          "name": "Compliance Visit"
        },
        {
          "@type": "DefinedTerm",
          "description": "The regulator for immigration advisers in the UK, formerly known as the OISC. Only advisers registered with the IAA, or regulated by the SRA, can legally give UK immigration advice.",
          "inDefinedTermSet": {
            "@id": "https://immtell.com/resources/glossary#glossary"
          },
          "name": "Immigration Advice Authority (IAA)"
        },
        {
          "@type": "DefinedTerm",
          "description": "Also called settlement. It allows a person to live and work in the UK without time restrictions, and is usually a step towards British citizenship.",
          "inDefinedTermSet": {
            "@id": "https://immtell.com/resources/glossary#glossary"
          },
          "name": "Indefinite Leave to Remain (ILR)"
        },
        {
          "@type": "DefinedTerm",
          "description": "The main UK work visa for people sponsored by a licensed employer to fill an eligible role that meets the required skill and salary thresholds.",
          "inDefinedTermSet": {
            "@id": "https://immtell.com/resources/glossary#glossary"
          },
          "name": "Skilled Worker Visa"
        },
        {
          "@type": "DefinedTerm",
          "description": "A code that classifies a job role. It is used to check whether a role is eligible for sponsorship and what the going rate for the role is.",
          "inDefinedTermSet": {
            "@id": "https://immtell.com/resources/glossary#glossary"
          },
          "name": "SOC Code"
        },
        {
          "@type": "DefinedTerm",
          "description": "The permission a UK business needs from the Home Office before it can employ most non-UK workers. It comes with ongoing compliance duties.",
          "inDefinedTermSet": {
            "@id": "https://immtell.com/resources/glossary#glossary"
          },
          "name": "Sponsor Licence"
        },
        {
          "@type": "DefinedTerm",
          "description": "The record-keeping and reporting responsibilities a business takes on when it holds a sponsor licence, such as reporting changes to a sponsored worker's employment.",
          "inDefinedTermSet": {
            "@id": "https://immtell.com/resources/glossary#glossary"
          },
          "name": "Sponsor Duties"
        }
      ],
      "inLanguage": "en-GB",
      "name": "Immtell UK Immigration Glossary",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com/resources/glossary"
    },
    {
      "@id": "https://immtell.com/resources/glossary#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/resources",
          "name": "Resources",
          "position": 2
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/resources/glossary",
          "name": "Glossary",
          "position": 3
        }
      ]
    }
  ]
}
```
</details>

### /resources/tool/visa-route-finder
- **URL:** https://immtell.com/resources/tool/visa-route-finder · **Type:** Tool (WebApplication) · **Webflow page:**  (`6a99b969a85749c44c89cd55`)
- **বর্তমান অবস্থা:** JSON valid, schema types: BreadcrumbList, ContactPoint, Country, ImageObject, ListItem, Offer, Organization, PeopleAudience, Person, PostalAddress, ProfessionalService, PropertyValue, WebApplication, WebPage, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb; ❌ Software app (rating/review নেই)

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/resources/tool/visa-route-finder#webpage",
      "@type": "WebPage",
      "about": {
        "@id": "https://immtell.com/#organization"
      },
      "breadcrumb": {
        "@id": "https://immtell.com/resources/tool/visa-route-finder#breadcrumb"
      },
      "description": "Answer a few questions to see which UK visa routes you may be eligible for, whether you are coming to work, join family, study, or settle.",
      "inLanguage": "en-GB",
      "isPartOf": {
        "@id": "https://immtell.com/#website"
      },
      "mainEntity": {
        "@id": "https://immtell.com/resources/tool/visa-route-finder#app"
      },
      "mentions": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "name": "Visa Route Finder",
      "url": "https://immtell.com/resources/tool/visa-route-finder"
    },
    {
      "@id": "https://immtell.com/resources/tool/visa-route-finder#app",
      "@type": "WebApplication",
      "applicationCategory": "UtilitiesApplication",
      "audience": {
        "@type": "PeopleAudience",
        "audienceType": "Individuals planning to come to or stay in the UK"
      },
      "browserRequirements": "Requires JavaScript",
      "description": "Answer a few questions to see which UK visa routes you may be eligible for, whether you are coming to work, join family, study, or settle.",
      "featureList": [
        "Your purpose: whether you are coming to work, join family, study, or settle shapes the route.",
        "Sponsorship: many work routes require a job offer from a licensed UK sponsor.",
        "Your current status: whether you are inside or outside the UK affects how and when you apply.",
        "Family connections: a partner or family member in the UK may open a family route."
      ],
      "inLanguage": "en-GB",
      "isAccessibleForFree": true,
      "name": "Visa Route Finder",
      "offers": {
        "@type": "Offer",
        "price": "0",
        "priceCurrency": "GBP"
      },
      "operatingSystem": "All",
      "provider": {
        "@id": "https://immtell.com/#organization"
      },
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "timeRequired": "PT4M",
      "url": "https://immtell.com/resources/tool/visa-route-finder"
    },
    {
      "@id": "https://immtell.com/resources/tool/visa-route-finder#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/resources",
          "name": "Resources",
          "position": 2
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/resources/tools",
          "name": "Tools",
          "position": 3
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/resources/tool/visa-route-finder",
          "name": "Visa Route Finder",
          "position": 4
        }
      ]
    }
  ]
}
```
</details>

### /resources/tool/soc-code-lookup
- **URL:** https://immtell.com/resources/tool/soc-code-lookup · **Type:** Tool (WebApplication) · **Webflow page:**  (`6a99b849011eeee33e4513d8`)
- **বর্তমান অবস্থা:** JSON valid, schema types: BreadcrumbList, BusinessAudience, ContactPoint, Country, ImageObject, ListItem, Offer, Organization, Person, PostalAddress, ProfessionalService, PropertyValue, WebApplication, WebPage, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb; ❌ Software app (rating/review নেই)

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/resources/tool/soc-code-lookup#webpage",
      "@type": "WebPage",
      "about": {
        "@id": "https://immtell.com/#organization"
      },
      "breadcrumb": {
        "@id": "https://immtell.com/resources/tool/soc-code-lookup#breadcrumb"
      },
      "description": "Find the right Standard Occupational Classification (SOC) code for the role you want to sponsor, and see the going rate and skill level that apply.",
      "inLanguage": "en-GB",
      "isPartOf": {
        "@id": "https://immtell.com/#website"
      },
      "mainEntity": {
        "@id": "https://immtell.com/resources/tool/soc-code-lookup#app"
      },
      "name": "SOC Code Lookup",
      "url": "https://immtell.com/resources/tool/soc-code-lookup"
    },
    {
      "@id": "https://immtell.com/resources/tool/soc-code-lookup#app",
      "@type": "WebApplication",
      "applicationCategory": "BusinessApplication",
      "audience": {
        "@type": "BusinessAudience",
        "audienceType": "UK employers"
      },
      "browserRequirements": "Requires JavaScript",
      "description": "Find the right Standard Occupational Classification (SOC) code for the role you want to sponsor, and see the going rate and skill level that apply.",
      "featureList": [
        "Going rate: each SOC code sets the minimum salary, and paying below it can lead to refusal or a reportable event.",
        "Skill level: the code determines whether the role meets the required threshold for sponsorship.",
        "Salary list status: some occupations sit on the Immigration Salary List with reduced rates.",
        "Visa route eligibility: the code affects which visa routes, such as Health and Care, the role qualifies for."
      ],
      "inLanguage": "en-GB",
      "isAccessibleForFree": true,
      "name": "SOC Code Lookup",
      "offers": {
        "@type": "Offer",
        "price": "0",
        "priceCurrency": "GBP"
      },
      "operatingSystem": "All",
      "provider": {
        "@id": "https://immtell.com/#organization"
      },
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "timeRequired": "PT2M",
      "url": "https://immtell.com/resources/tool/soc-code-lookup"
    },
    {
      "@id": "https://immtell.com/resources/tool/soc-code-lookup#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/resources",
          "name": "Resources",
          "position": 2
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/resources/tools",
          "name": "Tools",
          "position": 3
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/resources/tool/soc-code-lookup",
          "name": "SOC Code Lookup",
          "position": 4
        }
      ]
    }
  ]
}
```
</details>

### /resources/tool/licence-eligibility-checker
- **URL:** https://immtell.com/resources/tool/licence-eligibility-checker · **Type:** Tool (WebApplication) · **Webflow page:**  (`6a99b49551e84fe61fba936a`)
- **বর্তমান অবস্থা:** JSON valid, schema types: BreadcrumbList, BusinessAudience, ContactPoint, Country, ImageObject, ListItem, Offer, Organization, Person, PostalAddress, ProfessionalService, PropertyValue, WebApplication, WebPage, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb; ❌ Software app (rating/review নেই)

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/resources/tool/licence-eligibility-checker#webpage",
      "@type": "WebPage",
      "about": {
        "@id": "https://immtell.com/#organization"
      },
      "breadcrumb": {
        "@id": "https://immtell.com/resources/tool/licence-eligibility-checker#breadcrumb"
      },
      "description": "Answer a few questions to see whether your business is likely to qualify for a UK sponsor licence, and what the Home Office will want to see.",
      "inLanguage": "en-GB",
      "isPartOf": {
        "@id": "https://immtell.com/#website"
      },
      "mainEntity": {
        "@id": "https://immtell.com/resources/tool/licence-eligibility-checker#app"
      },
      "mentions": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "name": "Licence Eligibility Checker",
      "url": "https://immtell.com/resources/tool/licence-eligibility-checker"
    },
    {
      "@id": "https://immtell.com/resources/tool/licence-eligibility-checker#app",
      "@type": "WebApplication",
      "applicationCategory": "BusinessApplication",
      "audience": {
        "@type": "BusinessAudience",
        "audienceType": "UK employers"
      },
      "browserRequirements": "Requires JavaScript",
      "description": "Answer a few questions to see whether your business is likely to qualify for a UK sponsor licence, and what the Home Office will want to see.",
      "featureList": [
        "A genuine, trading business: the Home Office must be satisfied the organisation is real and lawfully operating.",
        "A genuine vacancy: the role must be at the required skill level and genuinely exist.",
        "Suitable Key Personnel: the Authorising Officer and Level 1 User must be eligible and UK-based.",
        "No serious history: unspent offences or prior compliance failures can affect suitability."
      ],
      "inLanguage": "en-GB",
      "isAccessibleForFree": true,
      "name": "Licence Eligibility Checker",
      "offers": {
        "@type": "Offer",
        "price": "0",
        "priceCurrency": "GBP"
      },
      "operatingSystem": "All",
      "provider": {
        "@id": "https://immtell.com/#organization"
      },
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "timeRequired": "PT3M",
      "url": "https://immtell.com/resources/tool/licence-eligibility-checker"
    },
    {
      "@id": "https://immtell.com/resources/tool/licence-eligibility-checker#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/resources",
          "name": "Resources",
          "position": 2
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/resources/tools",
          "name": "Tools",
          "position": 3
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/resources/tool/licence-eligibility-checker",
          "name": "Licence Eligibility Checker",
          "position": 4
        }
      ]
    }
  ]
}
```
</details>

### /resources/tool/compliance-health-check
- **URL:** https://immtell.com/resources/tool/compliance-health-check · **Type:** Tool (WebApplication) · **Webflow page:**  (`6a99b24aa39dde865aea7d69`)
- **বর্তমান অবস্থা:** JSON valid, schema types: BreadcrumbList, BusinessAudience, ContactPoint, Country, ImageObject, ListItem, Offer, Organization, Person, PostalAddress, ProfessionalService, PropertyValue, WebApplication, WebPage, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb; ❌ Software app (rating/review নেই)

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/resources/tool/compliance-health-check#webpage",
      "@type": "WebPage",
      "about": {
        "@id": "https://immtell.com/#organization"
      },
      "breadcrumb": {
        "@id": "https://immtell.com/resources/tool/compliance-health-check#breadcrumb"
      },
      "description": "A quick self-assessment of how audit-ready your business is as a sponsor, with pointers on where to focus before a Home Office visit.",
      "inLanguage": "en-GB",
      "isPartOf": {
        "@id": "https://immtell.com/#website"
      },
      "mainEntity": {
        "@id": "https://immtell.com/resources/tool/compliance-health-check#app"
      },
      "name": "Compliance Health Check",
      "url": "https://immtell.com/resources/tool/compliance-health-check"
    },
    {
      "@id": "https://immtell.com/resources/tool/compliance-health-check#app",
      "@type": "WebApplication",
      "applicationCategory": "BusinessApplication",
      "audience": {
        "@type": "BusinessAudience",
        "audienceType": "UK employers"
      },
      "browserRequirements": "Requires JavaScript",
      "description": "A quick self-assessment of how audit-ready your business is as a sponsor, with pointers on where to focus before a Home Office visit.",
      "featureList": [
        "Right to work checks: whether valid checks are held for every sponsored worker, and were done at the right time.",
        "Record-keeping: whether files are complete, centralised, and match what the Home Office expects to see.",
        "Reporting processes: whether changes affecting sponsored workers are reported within the required deadlines.",
        "Key Personnel and systems: whether the right people and processes are in place to manage the licence day to day."
      ],
      "inLanguage": "en-GB",
      "isAccessibleForFree": true,
      "name": "Compliance Health Check",
      "offers": {
        "@type": "Offer",
        "price": "0",
        "priceCurrency": "GBP"
      },
      "operatingSystem": "All",
      "provider": {
        "@id": "https://immtell.com/#organization"
      },
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "timeRequired": "PT4M",
      "url": "https://immtell.com/resources/tool/compliance-health-check"
    },
    {
      "@id": "https://immtell.com/resources/tool/compliance-health-check#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/resources",
          "name": "Resources",
          "position": 2
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/resources/tools",
          "name": "Tools",
          "position": 3
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/resources/tool/compliance-health-check",
          "name": "Compliance Health Check",
          "position": 4
        }
      ]
    }
  ]
}
```
</details>

### /resources/tool/civil-penalty-calculator
- **URL:** https://immtell.com/resources/tool/civil-penalty-calculator · **Type:** Tool (WebApplication) · **Webflow page:**  (`6a97586ab63fdaaeac662b69`)
- **বর্তমান অবস্থা:** JSON valid, schema types: BreadcrumbList, BusinessAudience, ContactPoint, Country, ImageObject, ListItem, Offer, Organization, Person, PostalAddress, ProfessionalService, PropertyValue, WebApplication, WebPage, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb; ❌ Software app (rating/review নেই)

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/resources/tool/civil-penalty-calculator#webpage",
      "@type": "WebPage",
      "about": {
        "@id": "https://immtell.com/#organization"
      },
      "breadcrumb": {
        "@id": "https://immtell.com/resources/tool/civil-penalty-calculator#breadcrumb"
      },
      "description": "Estimate your potential exposure for illegal working civil penalties, based on your circumstances and check history. Get an immediate figure and a sense of what drives it.",
      "inLanguage": "en-GB",
      "isPartOf": {
        "@id": "https://immtell.com/#website"
      },
      "mainEntity": {
        "@id": "https://immtell.com/resources/tool/civil-penalty-calculator#app"
      },
      "name": "Civil Penalty Calculator",
      "url": "https://immtell.com/resources/tool/civil-penalty-calculator"
    },
    {
      "@id": "https://immtell.com/resources/tool/civil-penalty-calculator#app",
      "@type": "WebApplication",
      "applicationCategory": "BusinessApplication",
      "audience": {
        "@type": "BusinessAudience",
        "audienceType": "UK employers"
      },
      "browserRequirements": "Requires JavaScript",
      "description": "Estimate your potential exposure for illegal working civil penalties, based on your circumstances and check history. Get an immediate figure and a sense of what drives it.",
      "featureList": [
        "Number of workers found without a valid check, as penalties are issued per worker.",
        "First or repeat breach within the last three years, which significantly changes the amount.",
        "Mitigating factors, such as reporting the suspected illegal worker and cooperating with the Home Office.",
        "Whether a valid check was attempted, which can provide a statutory excuse in some cases."
      ],
      "inLanguage": "en-GB",
      "isAccessibleForFree": true,
      "name": "Civil Penalty Calculator",
      "offers": {
        "@type": "Offer",
        "price": "0",
        "priceCurrency": "GBP"
      },
      "operatingSystem": "All",
      "provider": {
        "@id": "https://immtell.com/#organization"
      },
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "timeRequired": "PT3M",
      "url": "https://immtell.com/resources/tool/civil-penalty-calculator"
    },
    {
      "@id": "https://immtell.com/resources/tool/civil-penalty-calculator#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/resources",
          "name": "Resources",
          "position": 2
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/resources/tools",
          "name": "Tools",
          "position": 3
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/resources/tool/civil-penalty-calculator",
          "name": "Civil Penalty Calculator",
          "position": 4
        }
      ]
    }
  ]
}
```
</details>

### /testimonials
- **URL:** https://immtell.com/testimonials · **Type:** Testimonials · **Webflow page:**  (`6a96d5336ef1aedfbdd36bce`)
- **বর্তমান অবস্থা:** JSON valid, schema types: BreadcrumbList, CollectionPage, ContactPoint, Country, ImageObject, ListItem, Organization, Person, PostalAddress, ProfessionalService, PropertyValue, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |
| removed 4 self-serving Review nodes | Critical | নিজের ব্যবসার নিজের site এ review markup — Google self-serving review policy | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/testimonials#collectionpage",
      "@type": "CollectionPage",
      "about": {
        "@id": "https://immtell.com/#organization"
      },
      "description": "Client reviews and testimonials for Immtell, an IAA-regulated UK immigration consultancy.",
      "isPartOf": {
        "@id": "https://immtell.com/#website"
      },
      "name": "Immtell Client Reviews and Testimonials",
      "url": "https://immtell.com/testimonials"
    },
    {
      "@id": "https://immtell.com/testimonials#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/testimonials",
          "name": "Testimonials",
          "position": 2
        }
      ]
    }
  ]
}
```
</details>

### /fees/cos-skilled-worker-visa-fees
- **URL:** https://immtell.com/fees/cos-skilled-worker-visa-fees · **Type:** Pricing · **Webflow page:**  (`6a9471065840de8890cda836`)
- **বর্তমান অবস্থা:** JSON valid, schema types: Answer, BreadcrumbList, ContactPoint, Country, FAQPage, ImageObject, ListItem, Offer, Organization, Person, PostalAddress, PriceSpecification, ProfessionalService, PropertyValue, Question, Service, WebPage, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb; ❌ FAQ rich result (Aug 2023 থেকে শুধু govt/health site) — schema valid, AI/semantic এর জন্য রাখা হয়েছে

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/fees/cos-skilled-worker-visa-fees#webpage",
      "@type": "WebPage",
      "about": {
        "@id": "https://immtell.com/fees/cos-skilled-worker-visa-fees#service-page"
      },
      "breadcrumb": {
        "@id": "https://immtell.com/fees/cos-skilled-worker-visa-fees#breadcrumb"
      },
      "description": "Professional fees for CoS eligibility assessments, assigning a Certificate of Sponsorship (CoS), Skilled Worker visa support, allocation increase requests, and priority processing.",
      "inLanguage": "en-GB",
      "isPartOf": {
        "@id": "https://immtell.com/#website"
      },
      "mainEntity": {
        "@id": "https://immtell.com/fees/cos-skilled-worker-visa-fees#service-page"
      },
      "mentions": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "name": "CoS & Skilled Worker Visa Fees",
      "url": "https://immtell.com/fees/cos-skilled-worker-visa-fees"
    },
    {
      "@id": "https://immtell.com/fees/cos-skilled-worker-visa-fees#service-page",
      "@type": "Service",
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Fixed professional fees for Certificate of Sponsorship allocation requests, CoS eligibility assessment and drafting, combined CoS and Skilled Worker visa support, and the priority slot service. Home Office fees are separate.",
      "name": "Certificate of Sponsorship and Skilled Worker Visa Support",
      "offers": [
        {
          "@type": "Offer",
          "name": "CoS Allocation Increase Request",
          "price": "1000",
          "priceCurrency": "GBP",
          "priceSpecification": {
            "@type": "PriceSpecification",
            "price": "1000",
            "priceCurrency": "GBP",
            "valueAddedTaxIncluded": false
          },
          "seller": {
            "@id": "https://immtell.com/#organization"
          },
          "url": "https://immtell.com/fees/cos-skilled-worker-visa-fees"
        },
        {
          "@type": "Offer",
          "name": "CoS Eligibility Assessment and Drafting",
          "price": "1500",
          "priceCurrency": "GBP",
          "priceSpecification": {
            "@type": "PriceSpecification",
            "price": "1500",
            "priceCurrency": "GBP",
            "valueAddedTaxIncluded": false
          },
          "seller": {
            "@id": "https://immtell.com/#organization"
          },
          "url": "https://immtell.com/fees/cos-skilled-worker-visa-fees"
        },
        {
          "@type": "Offer",
          "name": "Full CoS Assignment and Skilled Worker Visa Support (Combined)",
          "price": "2200",
          "priceCurrency": "GBP",
          "priceSpecification": {
            "@type": "PriceSpecification",
            "price": "2200",
            "priceCurrency": "GBP",
            "valueAddedTaxIncluded": false
          },
          "seller": {
            "@id": "https://immtell.com/#organization"
          },
          "url": "https://immtell.com/fees/cos-skilled-worker-visa-fees"
        },
        {
          "@type": "Offer",
          "description": "Charged only on successful slot acquisition. The £350 Home Office Priority Service Fee is paid separately.",
          "name": "Priority Slot Service",
          "price": "495",
          "priceCurrency": "GBP",
          "priceSpecification": {
            "@type": "PriceSpecification",
            "price": "495",
            "priceCurrency": "GBP",
            "valueAddedTaxIncluded": false
          },
          "seller": {
            "@id": "https://immtell.com/#organization"
          },
          "url": "https://immtell.com/fees/cos-skilled-worker-visa-fees"
        },
        {
          "@type": "Offer",
          "name": "Response to a Live Home Office Query on an Allocation Request",
          "price": "1000",
          "priceCurrency": "GBP",
          "priceSpecification": {
            "@type": "PriceSpecification",
            "price": "1000",
            "priceCurrency": "GBP",
            "valueAddedTaxIncluded": false
          },
          "seller": {
            "@id": "https://immtell.com/#organization"
          },
          "url": "https://immtell.com/fees/cos-skilled-worker-visa-fees"
        }
      ],
      "provider": {
        "@id": "https://immtell.com/#organization"
      },
      "serviceType": "CoS assignment and Skilled Worker visa support",
      "url": "https://immtell.com/fees/cos-skilled-worker-visa-fees"
    },
    {
      "@id": "https://immtell.com/fees/cos-skilled-worker-visa-fees#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/fees/sponsor-licence-application-fees",
          "name": "Fees",
          "position": 2
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/fees/cos-skilled-worker-visa-fees",
          "name": "CoS & Skilled Worker Visa Fees",
          "position": 3
        }
      ]
    },
    {
      "@id": "https://immtell.com/fees/cos-skilled-worker-visa-fees#faq",
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "No. Home Office visa fees and the Immigration Health Surcharge are payable directly to the Home Office. We confirm which government fees apply before you instruct, and we direct you to GOV.UK for the current rates, because the government can update them at any time."
          },
          "name": "Are Home Office visa fees included in your professional fee?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. CoS eligibility assessment and drafting is available at £1,500 + VAT as a standalone instruction. Visa application support is also available as a standalone instruction where the CoS has already been assigned by someone else; the fee is confirmed at instruction. The combined CoS and visa service at £2,200 + VAT is more cost-effective than two separate retentions and eliminates the mismatch risk that arises when CoS and visa are managed by different parties."
          },
          "name": "Can I instruct CoS support without the visa support, or the other way around?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Priority slots are released by the Home Office in restricted daily windows and are frequently oversubscribed within minutes. Immtell monitors the release windows and secures a slot on your behalf. The £495 + VAT Immtell fee is charged only if a slot is successfully acquired. If a slot is not secured, you do not pay the Immtell fee. The £350 Home Office Priority Service Fee is separate and paid directly by you to the Home Office once a slot is confirmed. Most clients secure a slot within 2 to 5 working days."
          },
          "name": "How does the priority slot service work?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Where Immtell has confirmed that a visa application is ready for submission and a refusal arises due to deficiencies in our preparation, we will correct the submission and support resubmission at no additional professional fee. This covers submission quality, narrative construction, SOC code and salary analysis, and document alignment within our scope. It does not cover outcomes driven by factors outside our control, including Immigration Rule changes after instruction, changes in the worker's personal circumstances, or material information not disclosed before submission."
          },
          "name": "What if the visa application is refused?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "No. Every service is scoped and priced as a fixed engagement. You know what you are paying before you instruct. There are no hourly rates, no time-recording surprises, and no invoices that grow while the matter is open. If a complex matter comes to light after instruction that falls outside the agreed scope, an out-of-scope fee may apply. This will be either a fixed amount or our standard hourly rate, and will be agreed with you before any additional work continues."
          },
          "name": "Do you charge by the hour?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. Employers with recurring sponsorship needs across multiple workers or departments typically benefit from reduced per-matter fees. These arrangements are agreed individually based on the volume of instructions expected within a 12-month period. Contact us directly to discuss."
          },
          "name": "Is there a discount for multiple sponsorships?"
        }
      ]
    }
  ]
}
```
</details>

### /about
- **URL:** https://immtell.com/about · **Type:** About · **Webflow page:**  (`6a945e7aecca377464b9eb80`)
- **বর্তমান অবস্থা:** JSON valid, schema types: AboutPage, Answer, BreadcrumbList, ContactPoint, FAQPage, ImageObject, ListItem, Organization, Person, PostalAddress, PropertyValue, Question, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| Ewen jobTitle = visible "Head of Sponsor Compliance" | Warning | Page এ দেখানো title "Head of Sponsor Compliance", schema তে আলাদা | fixed code এ সংশোধিত |
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb; ❌ FAQ rich result (Aug 2023 থেকে শুধু govt/health site) — schema valid, AI/semantic এর জন্য রাখা হয়েছে

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": [
        {
          "@type": "PostalAddress",
          "addressCountry": "GB",
          "addressLocality": "London",
          "postalCode": "E14 5NR",
          "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
        },
        {
          "@type": "PostalAddress",
          "addressCountry": "GB",
          "addressLocality": "Brighton",
          "postalCode": "BN1 3XE",
          "streetAddress": "83 Queens Road"
        }
      ],
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, sponsor overseas workers, and supporting individuals with visas, settlement and British citizenship.",
      "employee": [
        {
          "@id": "https://immtell.com/#gavin-webster"
        },
        {
          "@id": "https://immtell.com/#ewen-mckenzie"
        }
      ],
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/about#webpage",
      "@type": "AboutPage",
      "about": {
        "@id": "https://immtell.com/#organization"
      },
      "dateModified": "2026-09-22",
      "inLanguage": "en-GB",
      "isPartOf": {
        "@id": "https://immtell.com/#website"
      },
      "mainEntity": {
        "@id": "https://immtell.com/#organization"
      },
      "name": "About Immtell",
      "url": "https://immtell.com/about"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "alumniOf": [
        {
          "@type": "Organization",
          "name": "Ernst & Young"
        },
        {
          "@type": "Organization",
          "name": "PwC"
        },
        {
          "@type": "Organization",
          "name": "Vialto Partners"
        }
      ],
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including over 6 years as a Visa Officer at British diplomatic missions, followed by senior immigration advisory roles at EY and PwC (later Vialto Partners).",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licences",
        "UK work visas",
        "UK immigration compliance",
        "settlement and British citizenship"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/#ewen-mckenzie",
      "@type": "Person",
      "description": "Head of Compliance at Immtell. Former Home Office sponsorship compliance specialist with around 20 years of government compliance experience. Leads Immtell's mock sponsor licence audits and desktop salary compliance reviews.",
      "jobTitle": "Head of Sponsor Compliance",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Home Office compliance visits",
        "sponsor management system reporting",
        "sponsored worker records"
      ],
      "name": "Ewen McKenzie",
      "sameAs": [
        "https://www.linkedin.com/in/ewen-mckenzie-020289200/"
      ],
      "url": "https://immtell.com/about/ewen-mckenzie",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/about#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/about",
          "name": "About",
          "position": 2
        }
      ]
    },
    {
      "@id": "https://immtell.com/about#faq",
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. Immtell is regulated by the Immigration Advice Authority (IAA, formerly OISC), Registration No. F202200109. This means we are authorised to legally provide UK immigration advice. You can verify our registration at the IAA public register."
          },
          "name": "Is Immtell regulated?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. On the business side, we handle sponsor licence applications, Certificates of Sponsorship, immigration compliance, and overseas worker visa support. For individuals, we handle UK work visas, family visas, settlement applications, and British citizenship. We do not handle immigration outside the UK."
          },
          "name": "Does Immtell handle both business and individual immigration?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Every engagement is handled personally by Gavin Webster or under his direct supervision. You will not be passed to a junior adviser or a large processing team. This is a deliberate choice. It is how we maintain the quality and accuracy that protects our clients."
          },
          "name": "Who will I work with at Immtell?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Immtell is an IAA-regulated immigration consultancy, not a law firm. Our focus is narrow (UK immigration only), which means every engagement benefits from deep specialist knowledge rather than general practice. Unlike large firms, every case is handled at senior level and not delegated to junior staff. Unlike unregulated online platforms, our advice is legally authorised under IAA regulation."
          },
          "name": "How is Immtell different from a solicitor or a large immigration firm?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Immtell has offices in London (Level 18, 40 Bank Street, Canary Wharf, London, E14 5NR) and Brighton (83 Queens Road, Brighton, East Sussex, BN1 3XE). Consultations can be conducted in person (by appointment) or by video call."
          },
          "name": "Where is Immtell based?"
        }
      ]
    }
  ]
}
```
</details>

### /fees/compliance-audit-fees
- **URL:** https://immtell.com/fees/compliance-audit-fees · **Type:** Pricing · **Webflow page:**  (`6a9455acc6dd4f0824ba0d5c`)
- **বর্তমান অবস্থা:** JSON valid, schema types: Answer, BreadcrumbList, ContactPoint, Country, FAQPage, ImageObject, ListItem, Offer, Organization, Person, PostalAddress, PriceSpecification, ProfessionalService, PropertyValue, Question, Service, UnitPriceSpecification, WebPage, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb; ❌ FAQ rich result (Aug 2023 থেকে শুধু govt/health site) — schema valid, AI/semantic এর জন্য রাখা হয়েছে

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "employee": [
        {
          "@id": "https://immtell.com/#gavin-webster"
        },
        {
          "@id": "https://immtell.com/#ewen-mckenzie"
        }
      ],
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/#ewen-mckenzie",
      "@type": "Person",
      "description": "Head of Sponsor Compliance at Immtell and a former Home Office sponsorship compliance specialist. Former Home Office Regional Compliance Manager who led teams of Home Office Compliance Officers carrying out sponsor licence audits, and former National Training Lead for sponsor compliance operations. 20 years with the Home Office, including 16 years specialising in sponsor compliance and sponsor management.",
      "jobTitle": "Head of Sponsor Compliance",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Sponsor Management System reporting",
        "Sponsor duties",
        "Right to Work checks",
        "Home Office compliance visits"
      ],
      "name": "Ewen McKenzie",
      "sameAs": [
        "https://www.linkedin.com/in/ewen-mckenzie-020289200/"
      ],
      "url": "https://immtell.com/about/ewen-mckenzie",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/fees/compliance-audit-fees#webpage",
      "@type": "WebPage",
      "about": {
        "@id": "https://immtell.com/fees/compliance-audit-fees#service-page"
      },
      "breadcrumb": {
        "@id": "https://immtell.com/fees/compliance-audit-fees#breadcrumb"
      },
      "description": "Professional fees for independent UK immigration compliance audits and ongoing sponsor licence support, from a one-off review to a 12-month advisory arrangement.",
      "inLanguage": "en-GB",
      "isPartOf": {
        "@id": "https://immtell.com/#website"
      },
      "mainEntity": {
        "@id": "https://immtell.com/fees/compliance-audit-fees#service-page"
      },
      "mentions": [
        {
          "@id": "https://immtell.com/#gavin-webster"
        },
        {
          "@id": "https://immtell.com/#ewen-mckenzie"
        }
      ],
      "name": "Compliance Audit Fees",
      "url": "https://immtell.com/fees/compliance-audit-fees"
    },
    {
      "@id": "https://immtell.com/fees/compliance-audit-fees#service-page",
      "@type": "Service",
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Fixed professional fees for independent UK sponsor licence compliance audits with a RAG-rated report, either as the entry point to a 12-month support arrangement or as a standalone one-off audit.",
      "name": "Sponsor Licence Compliance Audits and Ongoing Support",
      "offers": [
        {
          "@type": "Offer",
          "name": "Independent Compliance Review (entering 12-month arrangement)",
          "priceCurrency": "GBP",
          "priceSpecification": {
            "@type": "PriceSpecification",
            "maxPrice": "2000",
            "minPrice": "1500",
            "priceCurrency": "GBP",
            "valueAddedTaxIncluded": false
          },
          "seller": {
            "@id": "https://immtell.com/#organization"
          },
          "url": "https://immtell.com/fees/compliance-audit-fees"
        },
        {
          "@type": "Offer",
          "description": "Monthly compliance guidance for the 12-month term following the entry audit.",
          "name": "Ongoing Compliance Support (12-month arrangement)",
          "priceCurrency": "GBP",
          "priceSpecification": {
            "@type": "UnitPriceSpecification",
            "billingDuration": "P12M",
            "maxPrice": "1500",
            "minPrice": "750",
            "priceCurrency": "GBP",
            "unitText": "MONTH",
            "valueAddedTaxIncluded": false
          },
          "seller": {
            "@id": "https://immtell.com/#organization"
          },
          "url": "https://immtell.com/fees/compliance-audit-fees"
        },
        {
          "@type": "Offer",
          "name": "Standalone One-Off Immigration Compliance Audit",
          "priceCurrency": "GBP",
          "priceSpecification": {
            "@type": "PriceSpecification",
            "minPrice": "3500",
            "priceCurrency": "GBP",
            "valueAddedTaxIncluded": false
          },
          "seller": {
            "@id": "https://immtell.com/#organization"
          },
          "url": "https://immtell.com/fees/compliance-audit-fees"
        },
        {
          "@type": "Offer",
          "name": "Sponsored Worker Interviews (up to 3 workers)",
          "price": "500",
          "priceCurrency": "GBP",
          "priceSpecification": {
            "@type": "PriceSpecification",
            "price": "500",
            "priceCurrency": "GBP",
            "valueAddedTaxIncluded": false
          },
          "seller": {
            "@id": "https://immtell.com/#organization"
          },
          "url": "https://immtell.com/fees/compliance-audit-fees"
        },
        {
          "@type": "Offer",
          "description": "Available separately if you do not enter the 12-month ongoing support arrangement.",
          "name": "Ad-hoc Queries and Support After a Standalone Audit",
          "price": "350",
          "priceCurrency": "GBP",
          "priceSpecification": {
            "@type": "UnitPriceSpecification",
            "price": "350",
            "priceCurrency": "GBP",
            "unitText": "HOUR",
            "valueAddedTaxIncluded": false
          },
          "seller": {
            "@id": "https://immtell.com/#organization"
          },
          "url": "https://immtell.com/fees/compliance-audit-fees"
        }
      ],
      "provider": {
        "@id": "https://immtell.com/#organization"
      },
      "serviceType": "UK immigration compliance audit",
      "url": "https://immtell.com/fees/compliance-audit-fees"
    },
    {
      "@id": "https://immtell.com/fees/compliance-audit-fees#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/fees/sponsor-licence-application-fees",
          "name": "Fees",
          "position": 2
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/fees/compliance-audit-fees",
          "name": "Compliance Audit Fees",
          "position": 3
        }
      ]
    },
    {
      "@id": "https://immtell.com/fees/compliance-audit-fees#faq",
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The retainer-entry price of £1,500–£2,000 + VAT reflects the ongoing commitment that follows the audit. The 12-month arrangement means Immtell is engaged throughout the year, providing continuous compliance guidance, not a one-time review with no follow-through. The standalone audit from £3,500 + VAT reflects the absence of that ongoing relationship. The audit itself is identical in scope either way. What differs is what comes after it."
          },
          "name": "Why is the audit cheaper when I enter a 12-month arrangement?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes, you can. The Home Office does not require you to use an external auditor. The question to ask yourself is whether an internal review would find the same things a Home Office compliance officer would find. Internal reviews are often conducted by the same team responsible for the compliance processes being reviewed, which limits how objective the findings can be. An external audit conducted by someone who spent 13+ years inside the Home Office and later guided major employers through compliance at EY and PwC provides a closer approximation of what a Home Office compliance visit would uncover."
          },
          "name": "Can I run a compliance review myself rather than instructing Immtell?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The Compliance Review Report rates every finding Red, Amber, or Green. A Red rating means non-compliance or an issue requiring immediate attention. Left unaddressed, Red findings carry the risk of Home Office enforcement action, civil penalties, or suspension of your sponsor licence. An Amber rating means the position is not fully compliant but is addressable through specific improvements or adjustments within a defined timeframe. A Green rating means full compliance with Home Office requirements and current best practice. Each finding is accompanied by the specific Home Office requirement it relates to, the gap identified, and a recommended action. The written Compliance Improvement Plan then sets out the remedial steps in priority order, so you leave the process with a clear action list, not just a list of problems."
          },
          "name": "What does the RAG report contain?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Direct access to Gavin is included in the ongoing arrangement. If a Home Office query, an SMS audit request, or a notice of a compliance visit arrives during the 12-month term, you contact Gavin directly. There are no ticketing systems, no junior handovers, and no delays while a team works out who is handling it."
          },
          "name": "What happens if the Home Office contacts us during the ongoing arrangement?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Depending on the agreed scope of the monthly support package, training can be included. The monthly rate reflects the scope of your ongoing needs, and for organisations where sponsor duties training or right to work training is part of the agreed arrangement, that is built into the monthly fee rather than charged separately."
          },
          "name": "Is training included in the ongoing monthly arrangement?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "For the audit and the 12-month support arrangement, no. The audit is a fixed-fee engagement and the ongoing support arrangement is a fixed monthly rate. You know what you are paying before you instruct, and the figures do not change while the work is open. If you do not enter into the ongoing support arrangement, any queries or support needed after the audit are billed at £350 + VAT per hour. Where a discrete piece of fixed work arises, such as supporting a visa application or assigning a Certificate of Sponsorship, a fixed fee is agreed before that work begins rather than an hourly rate."
          },
          "name": "Do you charge by the hour?"
        }
      ]
    }
  ]
}
```
</details>

### /resources/events
- **URL:** https://immtell.com/resources/events · **Type:** Events listing · **Webflow page:**  (`6a9442137b904b23efae0e20`)
- **বর্তমান অবস্থা:** JSON valid, schema types: BreadcrumbList, CollectionPage, ContactPoint, Country, ImageObject, ListItem, Organization, Person, PostalAddress, ProfessionalService, PropertyValue, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/resources/events#webpage",
      "@type": "CollectionPage",
      "about": {
        "@id": "https://immtell.com/#organization"
      },
      "breadcrumb": {
        "@id": "https://immtell.com/resources/events#breadcrumb"
      },
      "description": "Live sessions and recorded webinars on sponsor compliance, visa routes, and the changes that affect your business. Hosted by our team, including an ex-Home Office officer.",
      "inLanguage": "en-GB",
      "isPartOf": {
        "@id": "https://immtell.com/#website"
      },
      "name": "Events & Webinars",
      "url": "https://immtell.com/resources/events"
    },
    {
      "@id": "https://immtell.com/resources/events#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/resources",
          "name": "Resources",
          "position": 2
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/resources/events",
          "name": "Events",
          "position": 3
        }
      ]
    }
  ]
}
```
</details>

### /fees/sponsor-licence-application-fees
- **URL:** https://immtell.com/fees/sponsor-licence-application-fees · **Type:** Pricing · **Webflow page:**  (`6a934441890706d073c7b581`)
- **বর্তমান অবস্থা:** JSON valid, schema types: Answer, BreadcrumbList, ContactPoint, Country, FAQPage, ImageObject, ListItem, Offer, Organization, Person, PostalAddress, PriceSpecification, ProfessionalService, PropertyValue, Question, Service, WebPage, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb; ❌ FAQ rich result (Aug 2023 থেকে শুধু govt/health site) — schema valid, AI/semantic এর জন্য রাখা হয়েছে

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/fees/sponsor-licence-application-fees#webpage",
      "@type": "WebPage",
      "about": {
        "@id": "https://immtell.com/fees/sponsor-licence-application-fees#service-page"
      },
      "breadcrumb": {
        "@id": "https://immtell.com/fees/sponsor-licence-application-fees#breadcrumb"
      },
      "description": "Professional fees for every tier of Home Office sponsor licence application support, from initial application through to strategy, application, and compliance training. Set out in full, before you enquire.",
      "inLanguage": "en-GB",
      "isPartOf": {
        "@id": "https://immtell.com/#website"
      },
      "mainEntity": {
        "@id": "https://immtell.com/fees/sponsor-licence-application-fees#service-page"
      },
      "mentions": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "name": "Sponsor Licence Application Fees",
      "url": "https://immtell.com/fees/sponsor-licence-application-fees"
    },
    {
      "@id": "https://immtell.com/fees/sponsor-licence-application-fees#service-page",
      "@type": "Service",
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Fixed professional fees for UK sponsor licence application support, from application support through strategy, application and compliance training, plus UK Expansion Worker licences. Home Office fees are separate.",
      "name": "UK Sponsor Licence Application Support",
      "offers": [
        {
          "@type": "Offer",
          "description": "Route and eligibility assessment, Key Personnel review and preparation and submission of the sponsor licence application.",
          "name": "Application Support",
          "priceCurrency": "GBP",
          "priceSpecification": {
            "@type": "PriceSpecification",
            "minPrice": "4500",
            "priceCurrency": "GBP",
            "valueAddedTaxIncluded": false
          },
          "seller": {
            "@id": "https://immtell.com/#organization"
          },
          "url": "https://immtell.com/fees/sponsor-licence-application-fees"
        },
        {
          "@type": "Offer",
          "description": "Adds route strategy, deeper Key Personnel risk analysis and a pre-submission risk assessment.",
          "name": "Strategy and Application",
          "priceCurrency": "GBP",
          "priceSpecification": {
            "@type": "PriceSpecification",
            "maxPrice": "6000",
            "minPrice": "5750",
            "priceCurrency": "GBP",
            "valueAddedTaxIncluded": false
          },
          "seller": {
            "@id": "https://immtell.com/#organization"
          },
          "url": "https://immtell.com/fees/sponsor-licence-application-fees"
        },
        {
          "@type": "Offer",
          "description": "Everything in Strategy and Application plus HR, right to work and SMS reporting training.",
          "name": "Strategy, Application and Compliance Training",
          "priceCurrency": "GBP",
          "priceSpecification": {
            "@type": "PriceSpecification",
            "maxPrice": "10000",
            "minPrice": "8750",
            "priceCurrency": "GBP",
            "valueAddedTaxIncluded": false
          },
          "seller": {
            "@id": "https://immtell.com/#organization"
          },
          "url": "https://immtell.com/fees/sponsor-licence-application-fees"
        },
        {
          "@type": "Offer",
          "description": "For overseas businesses establishing a UK presence for the first time.",
          "name": "UK Expansion Worker Licence",
          "priceCurrency": "GBP",
          "priceSpecification": {
            "@type": "PriceSpecification",
            "maxPrice": "12000",
            "minPrice": "8000",
            "priceCurrency": "GBP",
            "valueAddedTaxIncluded": false
          },
          "seller": {
            "@id": "https://immtell.com/#organization"
          },
          "url": "https://immtell.com/fees/sponsor-licence-application-fees"
        }
      ],
      "provider": {
        "@id": "https://immtell.com/#organization"
      },
      "serviceType": "Sponsor licence application",
      "url": "https://immtell.com/fees/sponsor-licence-application-fees"
    },
    {
      "@id": "https://immtell.com/fees/sponsor-licence-application-fees#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/fees/sponsor-licence-application-fees",
          "name": "Fees",
          "position": 2
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/fees/sponsor-licence-application-fees",
          "name": "Sponsor Licence Application Fees",
          "position": 3
        }
      ]
    },
    {
      "@id": "https://immtell.com/fees/sponsor-licence-application-fees#faq",
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "No. The Home Office application fee is payable directly to the Home Office and is never included in Immtell's invoice. We confirm which government fee applies to your application before you instruct, and we direct you to GOV.UK for the current rate."
          },
          "name": "Is the Home Office application fee included in your professional fee?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Tier 1 covers established businesses where the application does not require route strategy analysis, the company structure is clear, and all Key Personnel are eligible. Tier 2 is the right choice where route strategy is needed, the corporate structure is more complex, or Key Personnel eligibility requires analysis before submission. Tier 3 includes everything in Tier 2 plus HR and compliance training. If you are unsure which tier applies to your situation, a conversation with Gavin before instruction will clarify it."
          },
          "name": "How do I know which tier is right for me?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "No. Every engagement is scoped and priced as a fixed instruction. You know what you are paying before you instruct. There are no hourly rates, no time-recording surprises, and no invoices that grow while the matter is open."
          },
          "name": "Do you charge by the hour?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The fee ranges above cover the majority of standard applications. Where a situation falls outside the standard scope, for example, a layered group structure with overseas parent entities, we confirm a revised fee before you instruct. We do not proceed on an open-ended basis."
          },
          "name": "What if my situation is more complex than the standard scope?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "If your application is refused because of an error in our preparation, we correct it and resubmit at no additional professional fee. It covers deficiencies within our control: the preparation, documentation, narrative, and Key Personnel review that form our scope. It does not cover outcomes driven by Immigration Rule changes after instruction, third-party evidence errors, or information not disclosed to us before submission. We cannot guarantee approval. We can guarantee that everything within our control is prepared to the standard required."
          },
          "name": "What does the Submission Integrity Commitment cover?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes, you can. The Home Office does not require you to use a professional adviser. The question to ask yourself is whether your business is confident it can identify every eligibility requirement, prepare the supporting documentation correctly, and manage the application without guidance. A refused application can result in a 6-month cooling-off period before a further application can be made. Many businesses that attempt the sponsorship application themselves instruct a professional adviser after a refusal, at which point the cost is higher and the timeline is longer. Getting it right the first time is almost always the lower-cost route. There is also a regulatory point: UK immigration advice can only be provided legally by a firm registered with the Immigration Advice Authority or by a practising solicitor."
          },
          "name": "Can I apply for a sponsor licence without using a professional adviser?"
        }
      ]
    }
  ]
}
```
</details>

### /individuals/settle-in-the-uk/indefinite-leave-to-remain
- **URL:** https://immtell.com/individuals/settle-in-the-uk/indefinite-leave-to-remain · **Type:** Service · **Webflow page:**  (`6a9336c291bf868baf43b4ad`)
- **বর্তমান অবস্থা:** JSON valid, schema types: Answer, BreadcrumbList, ContactPoint, Country, FAQPage, ImageObject, ListItem, Organization, Person, PostalAddress, ProfessionalService, PropertyValue, Question, Service, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |
| removed consultation offers (prices not shown on page) | Critical | Consultation এর দাম (£55/£150/£280) page এ দেখানো নেই — content mismatch | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb; ❌ FAQ rich result (Aug 2023 থেকে শুধু govt/health site) — schema valid, AI/semantic এর জন্য রাখা হয়েছে

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/individuals/settle-in-the-uk/indefinite-leave-to-remain#service-page",
      "@type": "Service",
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Support with Indefinite Leave to Remain: eligibility, the qualifying route, evidence and application, prepared by an IAA-regulated firm.",
      "name": "Indefinite Leave to Remain (ILR) Application Support",
      "provider": {
        "@id": "https://immtell.com/#organization"
      },
      "serviceType": "ILR application support",
      "url": "https://immtell.com/individuals/settle-in-the-uk/indefinite-leave-to-remain"
    },
    {
      "@id": "https://immtell.com/individuals/settle-in-the-uk/indefinite-leave-to-remain#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/individuals/settle-in-the-uk/indefinite-leave-to-remain",
          "name": "Indefinite Leave to Remain",
          "position": 2
        }
      ]
    },
    {
      "@id": "https://immtell.com/individuals/settle-in-the-uk/indefinite-leave-to-remain#faq",
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Currently five years on most work and family routes, and ten years on the Long Residence route. Settlement rules are under review and may change in future, but the current rules apply until any change is confirmed."
          },
          "name": "How many years until I can apply for ILR?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The Home Office application fee is £3,226 per person from 8 April 2026, separate from any professional fee. Check the current figure on GOV.UK."
          },
          "name": "How much does ILR cost in 2026?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "On most routes, no more than 180 days outside the UK in any rolling 12-month period across your qualifying years."
          },
          "name": "How many days can I spend outside the UK before ILR?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes, you must pass the Life in the UK test, and meet English at level B1 unless you are exempt by age or nationality."
          },
          "name": "Do I need the Life in the UK test and an English test for ILR?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "They are expected to, as the reform is intended to apply to people already here. The transitional detail is still being finalised, so confirm your route and timing before you rely on the five-year period."
          },
          "name": "Will the 2026 settlement changes affect me if I am already in the UK?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "No. ILR is permanent settlement; citizenship is the next step and normally requires you to hold ILR or settled status first."
          },
          "name": "Is ILR the same as British citizenship?"
        }
      ]
    }
  ]
}
```
</details>

### /business/uk-immigration/uk-immigration-business-plans
- **URL:** https://immtell.com/business/uk-immigration/uk-immigration-business-plans · **Type:** Service · **Webflow page:**  (`6a92eb3e0f3eabab047bfe89`)
- **বর্তমান অবস্থা:** JSON valid, schema types: Answer, BreadcrumbList, ContactPoint, Country, FAQPage, ImageObject, ListItem, Organization, Person, PostalAddress, ProfessionalService, PropertyValue, Question, Service, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb; ❌ FAQ rich result (Aug 2023 থেকে শুধু govt/health site) — schema valid, AI/semantic এর জন্য রাখা হয়েছে

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/business/uk-immigration/uk-immigration-business-plans#service-page",
      "@type": "Service",
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Professionally written business plans for UK immigration applications, including Self-Sponsorship, Innovator Founder, Global Talent, Expansion Worker, and Sponsor Licence routes, drafted by a specialist immigration business plan writer and reviewed by Immtell's IAA-registered immigration team.",
      "name": "UK Immigration Business Plans",
      "provider": {
        "@id": "https://immtell.com/#organization"
      },
      "serviceType": "Immigration business plan preparation",
      "url": "https://immtell.com/business/uk-immigration/uk-immigration-business-plans"
    },
    {
      "@id": "https://immtell.com/business/uk-immigration/uk-immigration-business-plans#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Business Services",
          "position": 2
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/business/uk-immigration/uk-immigration-business-plans",
          "name": "UK Immigration Business Plans",
          "position": 3
        }
      ]
    },
    {
      "@id": "https://immtell.com/business/uk-immigration/uk-immigration-business-plans#faq",
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. Two rounds of revision are included in every plan. These rounds exist to ensure the final version accurately reflects your input and is fully aligned with your immigration application before submission."
          },
          "name": "Can I request changes after the first draft?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. We regularly prepare business plans for clients pursuing the UK Self-Sponsorship route, where an individual sets up a UK company and sponsors themselves as a Skilled Worker. The plan is written to support both the genuine commercial purpose of the business and the specific requirements of the Self-Sponsorship immigration case."
          },
          "name": "Can this support a Self-Sponsorship visa application?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. If you need end-to-end support, including preparing and submitting the immigration application itself, we can provide that as a separate regulated immigration service. Immtell is registered with the Immigration Advice Authority (IAA, formerly OISC), Registration No. F202200109. Contact us to discuss scope."
          },
          "name": "Can you help with the immigration application as well?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. A structured business plan can demonstrate your UK market entry rationale, commercial intent, and the specific reasons your organisation needs to establish a UK presence. These are material to an Expansion Worker licence application."
          },
          "name": "Is this suitable for an Expansion Worker sponsor licence application?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. We can structure the plan to address the viability and scalability criteria that endorsing bodies assess under the Innovator Founder route. We do not provide endorsement services, but a professionally written plan can significantly strengthen your case to an endorsing body."
          },
          "name": "Is this suitable for the Innovator Founder visa?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "We offer an expedited service. The expedited plan costs £2,800 + VAT (an additional £350 on the standard fee) and is delivered within 6 working days of your consultation call, instead of the standard 10 working days. Select the expedited option at the point of ordering."
          },
          "name": "What if I need the plan quickly?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Your plan is drafted by a specialist immigration business plan writer, not a generic copywriter, and is reviewed by our IAA-registered immigration team before delivery. The writer works with the immigration context in mind from the opening consultation."
          },
          "name": "Who actually writes the plan?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "No. Home Office application fees are separate and are paid directly to the Home Office. They are not included in Immtell's fee. Immtell's fee covers the business plan service only: the consultation, drafting, and two rounds of revision."
          },
          "name": "Are Home Office fees included in the price?"
        }
      ]
    }
  ]
}
```
</details>

### /business/uk-immigration/business-travel-visitor-visas
- **URL:** https://immtell.com/business/uk-immigration/business-travel-visitor-visas · **Type:** Service · **Webflow page:**  (`6a92dc4381c79909745ec70b`)
- **বর্তমান অবস্থা:** JSON valid, schema types: Answer, BreadcrumbList, ContactPoint, Country, FAQPage, ImageObject, ListItem, Organization, Person, PostalAddress, ProfessionalService, PropertyValue, Question, Service, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb; ❌ FAQ rich result (Aug 2023 থেকে শুধু govt/health site) — schema valid, AI/semantic এর জন্য রাখা হয়েছে

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/business/uk-immigration/business-travel-visitor-visas#service-page",
      "@type": "Service",
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Pre-travel assessments, permitted-activity guidance, and UK visitor visa applications for employees travelling to or entering the UK.",
      "name": "UK Business Travel and Visitor Visa Support",
      "provider": {
        "@id": "https://immtell.com/#organization"
      },
      "serviceType": "Business travel and visitor visa advice",
      "url": "https://immtell.com/business/uk-immigration/business-travel-visitor-visas"
    },
    {
      "@id": "https://immtell.com/business/uk-immigration/business-travel-visitor-visas#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Business Services",
          "position": 2
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/business/uk-immigration/business-travel-visitor-visas",
          "name": "Business Travel & Visitor Visas",
          "position": 3
        }
      ]
    },
    {
      "@id": "https://immtell.com/business/uk-immigration/business-travel-visitor-visas#faq",
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Permitted activities include attending meetings and conferences, negotiating contracts, participating in internal training or workshops, and visiting UK clients or business partners. Activities that are not permitted include delivering services to UK clients, contributing to day-to-day business operations, or doing work that would otherwise require a sponsored work visa. The line between permitted and not permitted depends on the specific activities, not just the stated purpose of the visit."
          },
          "name": "What activities are permitted under the UK visitor route for business visitors?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "In most cases, no. Business visitors must remain employed and paid by their overseas employer. Direct payment from a UK source is usually restricted under the visitor rules. If a UK company is paying the employee for work carried out during the visit, that is likely to require a sponsored work visa rather than a visitor entry."
          },
          "name": "Can a business visitor be paid by a UK company during their visit?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "This depends on the employee's nationality. Nationals of some countries can enter the UK as a Standard Visitor without applying for a visa in advance. Nationals of other countries must apply for a Standard Visitor visa before travelling. Regardless of nationality, the activities carried out during the visit must comply with the visitor rules. A visa grants permission to enter the UK; it does not change what activities are permitted once inside."
          },
          "name": "Do business visitors always need a visa before travelling to the UK?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "A sponsored work visa is required when the employee will carry out activities that amount to work in the UK, for example filling an operational role, delivering services directly to a UK client, contributing to day-to-day UK business operations, or being remunerated by a UK entity. If there is any uncertainty about whether planned activities cross this line, a legal assessment before travel is the most reliable way to confirm the correct route."
          },
          "name": "When does a business visit require a work visa instead of a visitor entry?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "A Standard Visitor visa covers multiple purposes, including tourism, family visits, and certain permitted business activities. There is no separate \"Business Visitor visa\" in UK immigration law. Business visitors use the Standard Visitor route but must carry out only the activities listed as permitted under Appendix Visitor: Permitted Activities. The activities permitted for business visitors are a subset of the broader Standard Visitor permissions."
          },
          "name": "What is the difference between a Standard Visitor and a Business Visitor?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "A refusal of entry is recorded against the employee's immigration history and can trigger additional scrutiny on every subsequent visit to the UK. Travel plans and any commercial commitments dependent on the visit are immediately disrupted. In some cases, refusals can affect applications for other types of visa in future. Getting a legal assessment of the planned activities before travel is the most effective way to avoid this outcome."
          },
          "name": "What happens if an employee is refused entry to the UK at the border?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The assessment covers the purpose of the visit, the employee's role and their relationship to the UK entity, the specific activities planned day by day, the commercial context, and whether those activities fall within the permitted activities under the UK visitor rules. The output is a written assessment confirming the correct immigration route and, where the visitor route is appropriate, preparation notes for the employee covering what to bring and what to say at the border."
          },
          "name": "How does Immtell assess whether a business visit is compliant?"
        }
      ]
    }
  ]
}
```
</details>

### /business/case-studies
- **URL:** https://immtell.com/business/case-studies · **Type:** Case study listing · **Webflow page:**  (`6a91e64d57561396c97705e5`)
- **বর্তমান অবস্থা:** JSON valid, schema types: Answer, BreadcrumbList, CollectionPage, ContactPoint, Country, FAQPage, ImageObject, ListItem, Organization, Person, PostalAddress, ProfessionalService, PropertyValue, Question, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb; ❌ FAQ rich result (Aug 2023 থেকে শুধু govt/health site) — schema valid, AI/semantic এর জন্য রাখা হয়েছে

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/business/case-studies#collectionpage",
      "@type": "CollectionPage",
      "about": {
        "@id": "https://immtell.com/#organization"
      },
      "description": "Client case studies showing how Immtell resolved UK sponsor licence, compliance and visa challenges.",
      "isPartOf": {
        "@id": "https://immtell.com/#website"
      },
      "name": "Immtell UK Immigration Case Studies",
      "url": "https://immtell.com/business/case-studies"
    },
    {
      "@id": "https://immtell.com/business/case-studies#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/business/case-studies",
          "name": "Case Studies",
          "position": 2
        }
      ]
    },
    {
      "@id": "https://immtell.com/business/case-studies#faq",
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. If a case study reflects a challenge similar to yours, we can discuss how the approach might apply to your specific situation. Book a call and describe your situation briefly when you request it, and we will prepare accordingly."
          },
          "name": "Can I speak to Immtell about a situation similar to one of the case studies?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. All case studies on this page are based on real client engagements. Client names and identifying details have been anonymised or generalised where appropriate to protect confidentiality, but the challenges, approaches, and outcomes described are factually accurate."
          },
          "name": "Are the case studies based on real client engagements?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Immtell works with businesses across a range of sizes, from founder-led companies and SMEs applying for their first sponsor licence, to larger organisations managing high-volume sponsorship programmes and multi-jurisdiction compliance. The case studies include examples at both ends of that range."
          },
          "name": "Does Immtell work with businesses of all sizes, or only large organisations?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Our case study experience includes energy and nuclear projects, technology companies (including overseas businesses establishing UK operations), professional services and consultancy, healthcare and care provision, and higher education. We also work with businesses in hospitality, financial services, and defence."
          },
          "name": "What sectors does Immtell have experience with?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. Several of the case studies above involved fixed project mobilisation windows or compliance deadlines. We are experienced in working to tight timelines and will be direct about what is and is not achievable within a given timeframe."
          },
          "name": "Can Immtell handle urgent cases or tight timelines?"
        }
      ]
    }
  ]
}
```
</details>

### /individuals/settle-in-the-uk/settlement-british-citizenship
- **URL:** https://immtell.com/individuals/settle-in-the-uk/settlement-british-citizenship · **Type:** Service · **Webflow page:**  (`6a91dc0c96dfb0cda2911844`)
- **বর্তমান অবস্থা:** JSON valid, schema types: Answer, BreadcrumbList, ContactPoint, Country, FAQPage, ImageObject, ListItem, Organization, Person, PostalAddress, ProfessionalService, PropertyValue, Question, Service, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |
| removed consultation offers (prices not shown on page) | Critical | Consultation এর দাম (£55/£150/£280) page এ দেখানো নেই — content mismatch | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb; ❌ FAQ rich result (Aug 2023 থেকে শুধু govt/health site) — schema valid, AI/semantic এর জন্য রাখা হয়েছে

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/individuals/settle-in-the-uk/settlement-british-citizenship#service-page",
      "@type": "Service",
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Support with British citizenship by naturalisation: eligibility assessment, evidence and application, prepared by an IAA-regulated firm.",
      "name": "British Citizenship by Naturalisation Application Support",
      "provider": {
        "@id": "https://immtell.com/#organization"
      },
      "serviceType": "Naturalisation application support",
      "url": "https://immtell.com/individuals/settle-in-the-uk/settlement-british-citizenship"
    },
    {
      "@id": "https://immtell.com/individuals/settle-in-the-uk/settlement-british-citizenship#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/home-individual",
          "name": "Individuals",
          "position": 2
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/individuals/settle-in-the-uk/settlement-british-citizenship",
          "name": "British Citizenship",
          "position": 3
        }
      ]
    },
    {
      "@id": "https://immtell.com/individuals/settle-in-the-uk/settlement-british-citizenship#faq",
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "On the standard route, at least 12 months after getting ILR or settled status. If you are married to a British citizen, there is no 12-month wait, but you must already hold ILR or settled status when you apply."
          },
          "name": "How long must I hold ILR before applying for citizenship?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The Home Office naturalisation fee is £1,709 from 8 April 2026, which includes the citizenship ceremony, plus £50 for the Life in the UK test and around £150 for an English test if you are not exempt. Check the current figure on GOV.UK."
          },
          "name": "How much does British citizenship cost in 2026?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "On the five-year route, up to 450 days over five years and up to 90 in the final 12 months. On the three-year partner route, up to 270 days over three years. The Home Office can use discretion in some cases."
          },
          "name": "How many days can I have spent outside the UK?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "No. The UK allows dual nationality, so you can usually keep your existing citizenship, though you should check whether your own country allows it."
          },
          "name": "Do I need to give up my current citizenship?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "No. You normally need to hold ILR or settled status first, then meet the citizenship rules (including the residence and character requirements) before you can apply to naturalise."
          },
          "name": "Can I apply for citizenship at the same time as ILR?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "They can, because citizenship normally requires ILR first. If the ILR qualifying period lengthens, the date you can naturalise may move later; existing ILR holders are not affected."
          },
          "name": "Will the 2026 settlement changes delay my citizenship?"
        }
      ]
    }
  ]
}
```
</details>

### /secure-priority-cos-allocation
- **URL:** https://immtell.com/secure-priority-cos-allocation · **Type:** Service · **Webflow page:**  (`6a91d523f8d310d8a3946112`)
- **বর্তমান অবস্থা:** JSON valid, schema types: Answer, BreadcrumbList, ContactPoint, Country, FAQPage, ImageObject, ListItem, Organization, Person, PostalAddress, ProfessionalService, PropertyValue, Question, Service, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb; ❌ FAQ rich result (Aug 2023 থেকে শুধু govt/health site) — schema valid, AI/semantic এর জন্য রাখা হয়েছে

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/secure-priority-cos-allocation#service-page",
      "@type": "Service",
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "A managed service to secure a Home Office priority slot for a Certificate of Sponsorship allocation increase when an urgent hire cannot wait the standard timeline.",
      "name": "Priority CoS Allocation Service",
      "provider": {
        "@id": "https://immtell.com/#organization"
      },
      "serviceType": "Priority CoS allocation",
      "url": "https://immtell.com/secure-priority-cos-allocation"
    },
    {
      "@id": "https://immtell.com/secure-priority-cos-allocation#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/secure-priority-cos-allocation",
          "name": "Secure Priority CoS Allocation",
          "position": 2
        }
      ]
    },
    {
      "@id": "https://immtell.com/secure-priority-cos-allocation#faq",
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "A priority slot is not mandatory but significantly accelerates the timeline. Without it, the Home Office processes CoS allocation requests within its standard timeline, which can be up to 18 weeks. With a priority slot, the target is within 5 working days from the date of the Home Office Priority Service Fee payment. If your allocation need is urgent, a priority slot is the only way to expedite the Home Office's processing of the request."
          },
          "name": "Do I need a priority service slot to process my CoS allocation request?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The Home Office Priority Service Fee is £350. This fee is paid directly to the Home Office once Immtell secures a priority slot. It is required by the Home Office to activate priority processing of your allocation request. This figure should be verified against current GOV.UK guidance as government fees are subject to change."
          },
          "name": "How much does the Home Office Priority Service cost?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Immtell's fee is £495 + VAT. This fee is payable only if Immtell successfully secures a priority slot. If Immtell cannot secure a slot, no fee is charged. The Immtell fee is entirely separate from the Home Office Priority Service Fee."
          },
          "name": "How much does Immtell charge for the priority slot service?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "After placing an order, you confirm that you have submitted the allocation request via the SMS and completed the Home Office form. Immtell begins requesting a priority slot from Working Day 1. Once a slot is secured, Immtell forwards the Home Office payment link to you so you can pay the £350 Priority Service Fee directly. The Home Office then processes your request. Immtell continues submitting requests until the slot is confirmed and reviews progress with you at key milestones."
          },
          "name": "What happens after I place an order with Immtell?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Immtell monitors the Home Office's daily priority slot release window and submits requests on your behalf at the point of release. Priority slots are released in small numbers each day and are oversubscribed within minutes. Immtell does not need access to your SMS or to be formally appointed as your legal representative. Submissions are made via Immtell's own email address."
          },
          "name": "How does Immtell secure a priority service slot?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "An Undefined CoS is used for Skilled Workers who are already in the UK. It is required when an existing worker needs to extend their current visa, switch to a Skilled Worker visa from another immigration category, or when a new hire is already in the country. Undefined CoS allocations are issued annually by the Home Office and can be topped up via an in-year allocation increase request."
          },
          "name": "What is an Undefined Certificate of Sponsorship (CoS)?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "A Defined CoS is required for Skilled Workers applying for their visa from outside the UK. Defined CoS submissions are requested separately from Undefined CoS allocations and are not eligible for expedited processing through the Home Office priority service."
          },
          "name": "What is a Defined Certificate of Sponsorship (CoS)?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "A Level 1 User on your Sponsor Management System (SMS) submits the allocation increase request through the SMS portal and completes the Home Office allocation request form. Once this is done, Immtell can begin requesting a priority slot to expedite the Home Office's processing of the request."
          },
          "name": "How do I request an increase in my CoS allocation?"
        }
      ]
    }
  ]
}
```
</details>

### /individuals/visa-application/uk-visitor-visas
- **URL:** https://immtell.com/individuals/visa-application/uk-visitor-visas · **Type:** Service · **Webflow page:**  (`6a91d43b40a788d64878046a`)
- **বর্তমান অবস্থা:** JSON valid, schema types: Answer, BreadcrumbList, ContactPoint, Country, FAQPage, ImageObject, ListItem, Offer, Organization, Person, PostalAddress, ProfessionalService, PropertyValue, Question, Service, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb; ❌ FAQ rich result (Aug 2023 থেকে শুধু govt/health site) — schema valid, AI/semantic এর জন্য রাখা হয়েছে

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/individuals/visa-application/uk-visitor-visas#service-page",
      "@type": "Service",
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Support with UK visitor visa applications for tourism, business and family visits, prepared by an IAA-regulated firm.",
      "name": "UK Visitor Visa Support",
      "offers": [
        {
          "@type": "Offer",
          "name": "15-Minute Visitor Visa Consultation",
          "price": "55",
          "priceCurrency": "GBP"
        },
        {
          "@type": "Offer",
          "name": "30-Minute Visitor Visa Consultation",
          "price": "150",
          "priceCurrency": "GBP"
        },
        {
          "@type": "Offer",
          "name": "60-Minute Visitor Visa Consultation",
          "price": "280",
          "priceCurrency": "GBP"
        }
      ],
      "provider": {
        "@id": "https://immtell.com/#organization"
      },
      "serviceType": "Visitor visa support",
      "url": "https://immtell.com/individuals/visa-application/uk-visitor-visas"
    },
    {
      "@id": "https://immtell.com/individuals/visa-application/uk-visitor-visas#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/home-individual",
          "name": "Individuals",
          "position": 2
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/individuals/visa-application/uk-visitor-visas",
          "name": "UK Visitor Visas",
          "position": 3
        }
      ]
    },
    {
      "@id": "https://immtell.com/individuals/visa-application/uk-visitor-visas#faq",
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "It depends on your nationality. Nationals of some countries can enter the UK as a Standard Visitor without applying for a visa in advance. Nationals of other countries must apply for a Standard Visitor Visa before travelling. Some nationalities that previously did not need a visa are now required to obtain a UK Electronic Travel Authorisation (ETA) before travelling. The ETA is not a visa, but it is a mandatory pre-travel requirement for affected nationalities. To check what you need, use the [GOV.UK: Check if you need a UK visa] tool, which confirms the requirement based on your nationality and travel purpose."
          },
          "name": "Do I need a visa to visit the UK?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The UK ETA is a digital pre-travel permission introduced by the Home Office for nationalities that do not require a full visitor visa but are no longer able to travel to the UK visa-free without any prior authorisation. If your nationality is in the ETA-required category, you must apply for and receive an approved ETA before travelling. The ETA is linked to your passport and does not replace the Standard Visitor Visa. It is separate and applies to different nationalities. Check current ETA requirements at GOV.UK: Apply for a UK Electronic Travel Authorisation."
          },
          "name": "What is a UK Electronic Travel Authorisation (ETA) and do I need one?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Standard Visitor Visas normally allow stays of up to 6 months per visit. The exact period granted will be stated in your visa or entry clearance. Multiple-entry visas are available, meaning you can make more than one trip during the visa's validity period, but each individual visit is subject to the permitted stay. You cannot combine multiple visits to extend your stay beyond what is permitted on any single visit."
          },
          "name": "How long can I stay in the UK on a visitor visa?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. Visiting family members living in the UK is one of the permitted purposes under the Standard Visitor route. You will need to demonstrate the relationship with the person you are visiting, that they are lawfully resident in the UK, that you have somewhere to stay, and that you have sufficient funds and ties to your home country to show you will leave at the end of your visit."
          },
          "name": "Can I visit family in the UK on a Standard Visitor Visa?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "No. Visitor visas do not permit employment of any kind in the UK. You cannot take up a job, deliver services for payment to a UK company, or contribute to the day-to-day operations of a UK employer. Certain limited business activities are permitted under the business visitor rules, including attending meetings, conferences, and contract negotiations. If your activities would constitute work or employment, a sponsored work visa is required. Applying as a visitor for a trip that involves employment is a common cause of refusal and can have consequences for future visa applications."
          },
          "name": "Can I work in the UK on a visitor visa?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The most common reasons for refusal are: the application does not clearly demonstrate strong ties to the home country; the stated purpose of the visit is not convincing or is inconsistent with the applicant's circumstances; financial evidence is insufficient or poorly presented; the application does not address concerns raised by the applicant's travel or immigration history; or there are inconsistencies between the supporting documents and the application. Most refusals are preventable with careful preparation. A previous refusal must be disclosed on any future application and will be taken into account by the visa officer."
          },
          "name": "Why do UK visitor visa applications get refused?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. A refusal does not permanently bar you from reapplying. However, the refusal must be disclosed on any future UK immigration application, and you should address the reasons for refusal before reapplying. Reapplying with the same evidence that was refused is unlikely to produce a different outcome. Understanding specifically why the application was refused, and preparing a stronger application that addresses those reasons, is the right approach. Immtell can review refusal notices and advise on whether and how to reapply."
          },
          "name": "Can I reapply if my UK visitor visa application was refused?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "If you are travelling to the UK specifically to get married or enter a civil partnership, you must apply for a Marriage Visitor Visa rather than a Standard Visitor Visa. This applies even if you are a non-visa national who would not normally require a visa to enter the UK. The Marriage Visitor Visa does not allow you to remain in the UK after the ceremony. If your intention is to remain in the UK with your partner after the marriage, a Spouse Visa application is required. These are two separate routes on two separate applications. Immtell advises on both."
          },
          "name": "Do I need a separate visa to get married in the UK?"
        }
      ]
    }
  ]
}
```
</details>

### /individuals/visa-application/student-visas
- **URL:** https://immtell.com/individuals/visa-application/student-visas · **Type:** Service · **Webflow page:**  (`6a91ce80d77ca4b737667258`)
- **বর্তমান অবস্থা:** JSON valid, schema types: Answer, BreadcrumbList, ContactPoint, Country, FAQPage, ImageObject, ListItem, Offer, Organization, Person, PostalAddress, ProfessionalService, PropertyValue, Question, Service, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb; ❌ FAQ rich result (Aug 2023 থেকে শুধু govt/health site) — schema valid, AI/semantic এর জন্য রাখা হয়েছে

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/individuals/visa-application/student-visas#service-page",
      "@type": "Service",
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Support with UK Student visa applications, prepared by a firm with 23+ years of UK immigration experience.",
      "name": "UK Student Visa Support",
      "offers": [
        {
          "@type": "Offer",
          "name": "15-Minute Student Visa Consultation",
          "price": "55",
          "priceCurrency": "GBP"
        },
        {
          "@type": "Offer",
          "name": "30-Minute Student Visa Consultation",
          "price": "150",
          "priceCurrency": "GBP"
        },
        {
          "@type": "Offer",
          "name": "60-Minute Student Visa Consultation",
          "price": "280",
          "priceCurrency": "GBP"
        }
      ],
      "provider": {
        "@id": "https://immtell.com/#organization"
      },
      "serviceType": "Student visa support",
      "url": "https://immtell.com/individuals/visa-application/student-visas"
    },
    {
      "@id": "https://immtell.com/individuals/visa-application/student-visas#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/home-individual",
          "name": "Individuals",
          "position": 2
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/individuals/visa-application/student-visas",
          "name": "UK Student Visas",
          "position": 3
        }
      ]
    },
    {
      "@id": "https://immtell.com/individuals/visa-application/student-visas#faq",
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Whether you need a visa depends on your nationality, the length of your course, and the type of institution. Most international students from outside the UK will need either a UK Student Visa or a Short-Term Study Visa. Some nationalities may study short courses under a Standard Visitor Visa. If you are unsure, Immtell can confirm the correct route in a consultation."
          },
          "name": "Do I need a visa to study in the UK?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "A Confirmation of Acceptance for Studies (CAS) is a unique reference number issued by a licensed UK educational institution once you have accepted your course offer. It contains details about your course, tuition fees, and your institution's sponsor licence. You cannot apply for a UK Student Visa without a valid CAS number. Check that the details are accurate before you submit."
          },
          "name": "What is a CAS and why do I need one?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Most students on the UK Student Visa are permitted to work a limited number of hours per week during term time. The exact conditions depend on your visa and the level of your course. Working beyond the permitted hours is a breach of your visa conditions and can have serious consequences for future applications. Check your conditions carefully before taking up any work."
          },
          "name": "Can I work while studying in the UK on a Student Visa?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The UK Student Visa is the main route for degree-level and other longer courses. The Short-Term Study Visa is available only for English language courses lasting 6 to 11 months. The Short-Term Study Visa does not permit work, does not allow you to bring family members, and does not let you switch to a different visa route from inside the UK."
          },
          "name": "What is the difference between a Student Visa and a Short-Term Study Visa?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Eligibility to bring dependants (a partner or children) depends on the level of your course and your sponsor's track record. Not all students are eligible. Dependant applications add complexity and cost to the overall application. Immtell can advise on whether this is an option for your specific situation."
          },
          "name": "Can I bring my family to the UK on a Student Visa?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "A refusal does not necessarily mean you cannot study in the UK. The refusal notice states the specific reasons. In many cases, refusals result from avoidable documentation errors rather than fundamental eligibility issues. Immtell can review your refusal notice, identify what went wrong, and help you prepare a stronger application. Book a 60-minute consultation if you have received a refusal."
          },
          "name": "What happens if my UK Student Visa application is refused?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Processing times vary. UK Visas and Immigration publishes current estimates on GOV.UK. You should apply as early as possible, ideally as soon as your CAS has been issued. Priority and super-priority services are available in some locations for an additional fee. For current processing times, refer to the GOV.UK Student Visa page."
          },
          "name": "How long does a UK Student Visa take to process?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "No. No regulated immigration adviser can lawfully guarantee the outcome of a visa application. What Immtell provides is regulated, expert advice designed to give your application the strongest possible foundation and reduce the risk of avoidable refusal."
          },
          "name": "Can Immtell guarantee my application will be approved?"
        }
      ]
    }
  ]
}
```
</details>

### /individuals/visa-application/work-visas
- **URL:** https://immtell.com/individuals/visa-application/work-visas · **Type:** Service · **Webflow page:**  (`6a91c2efe731db9b4870eb08`)
- **বর্তমান অবস্থা:** JSON valid, schema types: Answer, BreadcrumbList, ContactPoint, Country, FAQPage, ImageObject, ListItem, Offer, Organization, Person, PostalAddress, ProfessionalService, PropertyValue, Question, Service, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb; ❌ FAQ rich result (Aug 2023 থেকে শুধু govt/health site) — schema valid, AI/semantic এর জন্য রাখা হয়েছে

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/individuals/visa-application/work-visas#service-page",
      "@type": "Service",
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Support with UK work visa applications, including the Skilled Worker route, prepared by a former UK Home Office officer.",
      "name": "UK Work Visa Support",
      "offers": {
        "@type": "Offer",
        "name": "Work Visa Consultation",
        "price": "150",
        "priceCurrency": "GBP"
      },
      "provider": {
        "@id": "https://immtell.com/#organization"
      },
      "serviceType": "Work visa support",
      "url": "https://immtell.com/individuals/visa-application/work-visas"
    },
    {
      "@id": "https://immtell.com/individuals/visa-application/work-visas#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/home-individual",
          "name": "Individuals",
          "position": 2
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/individuals/visa-application/work-visas",
          "name": "UK Work Visas",
          "position": 3
        }
      ]
    },
    {
      "@id": "https://immtell.com/individuals/visa-application/work-visas#faq",
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes, some work visas lead to Indefinite Leave to Remain (ILR), the UK's formal term for permanent residency. The most common route is the Skilled Worker Visa: after 5 years of qualifying residence, you can apply for ILR (subject to current rules, which are under government review). The UK Ancestry Visa also leads to ILR after 5 years. Some other routes, such as the Graduate Visa and the Youth Mobility Scheme Visa, do not lead directly to settlement, but they can be used as a stepping stone to apply for a sponsored work visa, which in turn can lead to ILR."
          },
          "name": "Can a UK work visa lead to permanent residency (ILR) in the UK?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Several UK work visa routes do not require employer sponsorship. The Graduate Visa, UK Ancestry Visa, and Youth Mobility Scheme Visa are all unsponsored; you can apply without a job offer from a UK employer. The India Young Professionals Scheme Visa is also unsponsored but operates via a ballot system for Indian nationals. The Skilled Worker Visa and Health and Care Worker Visa both require a Certificate of Sponsorship from a licensed UK employer."
          },
          "name": "Which UK work visas do not require employer sponsorship?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Most people who are not British or Irish citizens will need some form of leave to enter or remain in the UK that permits work. This is usually a work visa (such as the Skilled Worker Visa) or another leave category that includes the right to work (such as the Graduate Visa or a family visa with work permission). If you are a British or Irish citizen, or if you hold Settled Status (ILR) or Pre-Settled Status (EUSS), you are generally permitted to work without needing a separate visa. If you are unsure about your current immigration status and whether it permits work, a consultation will clarify your position quickly."
          },
          "name": "Do I need a visa to work legally in the UK?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The changes introduced in April 2024 and July 2025 raised salary thresholds and changed eligibility criteria for the Skilled Worker route. Critically, transitional arrangements are in place, meaning that whether the old or new rules apply to you depends on when you first received a Skilled Worker Visa and whether you are renewing, changing roles, or applying for the first time. This is one of the most common sources of confusion for Skilled Worker applicants right now, and it is an area where getting the wrong answer can result in a refusal. A consultation with Gavin will confirm which rules apply to your specific situation."
          },
          "name": "How do the April 2024 and July 2025 rule changes affect my Skilled Worker Visa?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The Skilled Worker Visa is the most common UK work visa route for people who have a confirmed job offer from a UK employer. The employer must hold a Home Office sponsor licence and issue a Certificate of Sponsorship. The Skilled Worker Visa covers a wide range of occupations and salary levels, and it can lead to Indefinite Leave to Remain after 5 years. Note that the salary thresholds and eligibility rules changed in April 2024 and again in July 2025, and transitional arrangements now apply to some applicants depending on when they first entered the route."
          },
          "name": "What is the most common UK work visa for people with a job offer?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The Graduate Visa currently lasts 2 years for bachelor's and master's degree holders, and 3 years for PhD holders. The Government has announced that the duration for bachelor's and master's level holders will be reduced to 18 months in 2027. PhD holders are not affected by this change. If you are planning to use the Graduate Visa after completing your studies, factor this timeline into your career and visa planning. You can use the Graduate Visa period to find sponsored employment and then switch to a Skilled Worker Visa if you want to remain in the UK longer term."
          },
          "name": "How long is the Graduate Visa, and is it changing?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Salary thresholds for the Skilled Worker Visa depend on your occupation code (SOC code), whether you are a new applicant or are extending an existing visa, and whether transitional arrangements apply to your situation. There is a general minimum salary threshold and occupation-specific \"going rates\", the higher of the two applies in most cases. The thresholds changed in April 2024, and there are now different rules depending on when you first obtained a Skilled Worker Visa. Because these figures change and transitional arrangements are complex, Immtell recommends verifying current rates at GOV.UK: Skilled Worker visa pay requirements and discussing your specific position in a consultation before applying."
          },
          "name": "What are the current salary thresholds for a Skilled Worker Visa?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. You can apply to switch from a Graduate Visa to a Skilled Worker Visa from inside the UK, provided you have a valid Certificate of Sponsorship from a licensed employer and meet the eligibility requirements (including the salary threshold). You do not need to leave the UK to make this switch. Timing matters, you should apply before your Graduate Visa expires. If you leave the UK and your Graduate Visa expires while you are abroad, you cannot re-enter on it."
          },
          "name": "Can I switch from a Graduate Visa to a Skilled Worker Visa while I am still in the UK?"
        }
      ]
    }
  ]
}
```
</details>

### /business/uk-immigration/hire-sponsor-overseas-workers
- **URL:** https://immtell.com/business/uk-immigration/hire-sponsor-overseas-workers · **Type:** Service · **Webflow page:**  (`6a91c2b5e944681735706ffc`)
- **বর্তমান অবস্থা:** JSON valid, schema types: Answer, BreadcrumbList, ContactPoint, Country, FAQPage, ImageObject, ListItem, Organization, Person, PostalAddress, ProfessionalService, PropertyValue, Question, Service, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb; ❌ FAQ rich result (Aug 2023 থেকে শুধু govt/health site) — schema valid, AI/semantic এর জন্য রাখা হয়েছে

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/business/uk-immigration/hire-sponsor-overseas-workers#service-page",
      "@type": "Service",
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Professional fees for assigning a Certificate of Sponsorship and preparing the Skilled Worker visa application, managed as one instruction.",
      "name": "Certificate of Sponsorship and Skilled Worker Visa Support",
      "provider": {
        "@id": "https://immtell.com/#organization"
      },
      "serviceType": "CoS and Skilled Worker visa support",
      "url": "https://immtell.com/business/uk-immigration/hire-sponsor-overseas-workers"
    },
    {
      "@id": "https://immtell.com/business/uk-immigration/hire-sponsor-overseas-workers#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Business Services",
          "position": 2
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/business/uk-immigration/hire-sponsor-overseas-workers",
          "name": "Hire & Sponsor Overseas Workers",
          "position": 3
        }
      ]
    },
    {
      "@id": "https://immtell.com/business/uk-immigration/hire-sponsor-overseas-workers#faq",
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Before assigning a Certificate of Sponsorship, confirm that: the SOC code correctly reflects the role's actual duties, the salary meets the current threshold including any applicable transitional provisions, the role represents a genuine vacancy and not a cosmetic position, the employer's reporting history on the SMS is up to date, and the worker's right to work has been checked and recorded correctly. Any one of these items being incorrect can lead to CoS refusal, visa refusal, or a compliance flag on the sponsor licence."
          },
          "name": "What checks should be carried out before assigning a Certificate of Sponsorship?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The total timeline from instruction to visa decision depends on several stages. Once we are instructed and documents are in place, CoS drafting and assignment typically takes 3 to 5 working days. For out-of-country applications, standard Skilled Worker visa processing is typically around 3 weeks. For in-country applications (extensions and switches), the standard Home Office target is around 8 weeks. Priority and super-priority visa services are sometimes available at an additional Home Office cost for in-country applications. Processing times are set by the Home Office and are subject to change; we confirm current targets when you instruct."
          },
          "name": "How long does it take to sponsor a Skilled Worker from start to finish?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "A Defined CoS is required for workers applying from outside the UK. Unlike Undefined CoS allocation increases, Defined CoS requests are not eligible for the Home Office priority processing service. Processing time for a Defined CoS depends on the Home Office's current workload and whether additional information is requested. Allow several weeks from submission as a working guide, but verify current targets with us at the time of instruction as these are subject to change."
          },
          "name": "How long does a Defined CoS decision take?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. We support both the employer (CoS drafting on the SMS, eligibility review, role documentation) and the individual worker (visa application preparation and submission, document review, coordination of timelines). Managing both from one instruction is how we eliminate the most common cause of visa refusal at this stage: a discrepancy between the CoS and the visa application."
          },
          "name": "Do you support both the employer and the visa applicant with the application?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Not always. If you need help with an Undefined CoS allocation increase, we can support you without SMS access. If you need us to prepare and assign a Defined CoS or submit one on your behalf, we will need to be added to your SMS as a Level 1 User. We will only request access when it is strictly necessary."
          },
          "name": "Does Immtell need access to our Sponsor Management System?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. If we did not prepare the original allocation increase request, we can still step in. We will review the submission, identify the specific issue the Home Office query is likely targeting, and prepare a structured response. The fee for this is £1,000 + VAT. Where the deadline is compressed, we prioritise these engagements subject to availability."
          },
          "name": "Can Immtell help if my CoS allocation increase request has already been submitted?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. As specialist immigration advisers, we support both the main applicant and their dependants, including spouses, partners, and children. Dependant visa applications can be included as part of your Skilled Worker visa service. If a sponsored worker's dependants need visa support, simply speak with us directly and we will guide you through the process."
          },
          "name": "Does Immtell support dependant visa applications for Skilled Worker visa holders?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Business visitor visa support is a separate service. The key question is not always which visa to apply for: it is whether the planned activities are permitted under the UK Visitor Rules or whether a sponsored work visa is required instead. Getting this distinction wrong can result in an employee being refused entry at the UK border. See our Business Travel and Visitor Visas page for details of how the visitor route assessment works."
          },
          "name": "Can you support business visitor visa applications?"
        }
      ]
    }
  ]
}
```
</details>

### /individuals/visa-application/family-partner-visas
- **URL:** https://immtell.com/individuals/visa-application/family-partner-visas · **Type:** Service · **Webflow page:**  (`6a919bc95f19dc2b14f587c3`)
- **বর্তমান অবস্থা:** JSON valid, schema types: Answer, BreadcrumbList, ContactPoint, Country, FAQPage, ImageObject, ListItem, Offer, Organization, Person, PostalAddress, ProfessionalService, PropertyValue, Question, Service, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb; ❌ FAQ rich result (Aug 2023 থেকে শুধু govt/health site) — schema valid, AI/semantic এর জন্য রাখা হয়েছে

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/individuals/visa-application/family-partner-visas#service-page",
      "@type": "Service",
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Support with UK spouse, unmarried partner and fiancé visa applications, prepared by a former UK Home Office Visa Officer.",
      "name": "UK Family and Partner Visa Support",
      "offers": [
        {
          "@type": "Offer",
          "name": "15-Minute Family Visa Consultation",
          "price": "55",
          "priceCurrency": "GBP"
        },
        {
          "@type": "Offer",
          "name": "30-Minute Family Visa Consultation",
          "price": "150",
          "priceCurrency": "GBP"
        },
        {
          "@type": "Offer",
          "name": "60-Minute Family Visa Consultation",
          "price": "280",
          "priceCurrency": "GBP"
        }
      ],
      "provider": {
        "@id": "https://immtell.com/#organization"
      },
      "serviceType": "Family and partner visa support",
      "url": "https://immtell.com/individuals/visa-application/family-partner-visas"
    },
    {
      "@id": "https://immtell.com/individuals/visa-application/family-partner-visas#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/home-individual",
          "name": "Individuals",
          "position": 2
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/individuals/visa-application/family-partner-visas",
          "name": "Family & Partner Visas",
          "position": 3
        }
      ]
    },
    {
      "@id": "https://immtell.com/individuals/visa-application/family-partner-visas#faq",
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. A Fiancé Visa allows you to travel to the UK to marry your British or settled partner. You must marry within 6 months of entering the UK on the Fiancé Visa. After the marriage, you apply to switch to a Spouse Visa; this is the required next step to remain in the UK long-term. You cannot extend the Fiancé Visa."
          },
          "name": "Can a UK fiancé visa lead to a spouse visa?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. A Spouse Visa application is normally submitted from outside the UK, at a UK Visa Application Centre in your country. The application is made on your circumstances at the time; you do not need to be in the UK to apply."
          },
          "name": "Can I apply for a UK spouse visa if we are living outside the UK?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "A UK Spouse Visa is initially granted for 2.5 years. Before it expires, you apply to extend for a further 2.5 years. After 5 years in total on a Spouse or Partner visa, you become eligible to apply for Indefinite Leave to Remain (ILR), permanent residency in the UK."
          },
          "name": "How long does a UK spouse visa last?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The UK partner must meet a minimum income threshold set by the Home Office. This figure was updated in April 2024 and is subject to further change; always verify the current threshold at GOV.UK. Cash savings can also be used to meet the financial requirement in certain circumstances."
          },
          "name": "What is the financial requirement for a UK spouse visa?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The Home Office assesses whether your relationship is \"genuine and subsisting.\" Evidence typically includes photographs of the couple together over time, communication records (messages, emails, call logs), evidence of joint plans (travel bookings, shared accommodation), and witness statements. A consultation helps identify the strongest evidence for your specific situation."
          },
          "name": "What evidence do I need to prove our relationship is genuine?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Dependent children of the main applicant can often be included in the application or apply separately as dependants. Eligibility depends on the child's age, nationality, and circumstances. A consultation can confirm the requirements for your specific family situation."
          },
          "name": "Can my children come to the UK on a family visa?"
        }
      ]
    }
  ]
}
```
</details>

### /terms-conditions
- **URL:** https://immtell.com/terms-conditions · **Type:** Legal · **Webflow page:**  (`6a918d79c8224d0aa76591c1`)
- **বর্তমান অবস্থা:** JSON valid, schema types: BreadcrumbList, ContactPoint, ImageObject, ListItem, Organization, Person, PostalAddress, PropertyValue, WebPage, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "Organization",
      "@id": "https://immtell.com/#organization",
      "name": "Immtell",
      "url": "https://immtell.com",
      "logo": {
        "@type": "ImageObject",
        "@id": "https://immtell.com/#logo",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "foundingDate": "2023",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "email": "info@immtell.com",
      "telephone": "+44-20-3910-6641",
      "address": [
        {
          "@type": "PostalAddress",
          "streetAddress": "Level 18, 40 Bank Street, Canary Wharf",
          "addressLocality": "London",
          "postalCode": "E14 5NR",
          "addressCountry": "GB"
        },
        {
          "@type": "PostalAddress",
          "streetAddress": "83 Queens Road",
          "addressLocality": "Brighton",
          "postalCode": "BN1 3XE",
          "addressCountry": "GB"
        }
      ],
      "contactPoint": {
        "@type": "ContactPoint",
        "contactType": "customer service",
        "telephone": "+44-20-3910-6641",
        "email": "info@immtell.com",
        "areaServed": "GB",
        "availableLanguage": "English"
      },
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ]
    },
    {
      "@type": "WebSite",
      "@id": "https://immtell.com/#website",
      "name": "Immtell",
      "url": "https://immtell.com",
      "inLanguage": "en-GB",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@type": "Person",
      "@id": "https://immtell.com/#gavin-webster",
      "name": "Gavin Webster",
      "jobTitle": "Founder and Managing Director",
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      },
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ]
    },
    {
      "@type": "WebPage",
      "@id": "https://immtell.com/terms-conditions#webpage",
      "name": "Terms and Conditions",
      "url": "https://immtell.com/terms-conditions",
      "isPartOf": {
        "@id": "https://immtell.com/#website"
      },
      "about": {
        "@id": "https://immtell.com/#organization"
      },
      "inLanguage": "en-GB",
      "dateModified": "2023-03-03",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@type": "BreadcrumbList",
      "@id": "https://immtell.com/terms-conditions#breadcrumb",
      "itemListElement": [
        {
          "@type": "ListItem",
          "position": 1,
          "name": "Home",
          "item": "https://immtell.com"
        },
        {
          "@type": "ListItem",
          "position": 2,
          "name": "Terms and Conditions",
          "item": "https://immtell.com/terms-conditions"
        }
      ]
    }
  ]
}
```
</details>

### /news
- **URL:** https://immtell.com/news · **Type:** Blog listing · **Webflow page:**  (`6a90c009845fa7ec4961a71a`)
- **বর্তমান অবস্থা:** JSON valid, schema types: Answer, BreadcrumbList, CollectionPage, ContactPoint, Country, FAQPage, ImageObject, ListItem, Organization, Person, PostalAddress, ProfessionalService, PropertyValue, Question, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb; ❌ FAQ rich result (Aug 2023 থেকে শুধু govt/health site) — schema valid, AI/semantic এর জন্য রাখা হয়েছে

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/news#collectionpage",
      "@type": "CollectionPage",
      "about": {
        "@id": "https://immtell.com/#organization"
      },
      "description": "News, policy updates and practical analysis on UK immigration for employers and visa applicants.",
      "isPartOf": {
        "@id": "https://immtell.com/#website"
      },
      "name": "Immtell UK Immigration News",
      "url": "https://immtell.com/news"
    },
    {
      "@id": "https://immtell.com/news#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/news",
          "name": "News",
          "position": 2
        }
      ]
    },
    {
      "@id": "https://immtell.com/news#faq",
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Immtell publishes UK immigration updates written or reviewed by Gavin Webster, a former UK Home Office Visa Officer, within 5 working days of any Home Office Statement of Changes. For the official source, see GOV.UK: Immigration Rules."
          },
          "name": "Where can I find reliable, up-to-date UK immigration news?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Frequently. The Home Office issues Statements of Changes to the Immigration Rules several times a year. The most significant recent changes were in April 2024 and July 2025, with a fee increase in April 2026."
          },
          "name": "How often do UK immigration rules change?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Gavin Webster, Immtell's founder, with 13+ years inside the UK Home Office and 23+ years of UK immigration experience in total. Articles are written or reviewed by him."
          },
          "name": "Who writes Immtell's immigration news?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. Immtell is on the IAA register (Registration No. F202200109). Only IAA or SRA registered firms can legally provide UK immigration advice."
          },
          "name": "Is Immtell a regulated UK immigration firm?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Book a paid consultation with Gavin Webster, who will confirm how the change applies to your specific circumstances and what you need to do."
          },
          "name": "How do I find out how a rule change affects my business or visa?"
        }
      ]
    }
  ]
}
```
</details>

### /business/uk-immigration/protect-your-sponsor-licence
- **URL:** https://immtell.com/business/uk-immigration/protect-your-sponsor-licence · **Type:** Service · **Webflow page:**  (`6a908ec7a63f0dd932b88685`)
- **বর্তমান অবস্থা:** JSON valid, schema types: Answer, BreadcrumbList, ContactPoint, Country, FAQPage, ImageObject, ListItem, Organization, Person, PostalAddress, PropertyValue, Question, Service, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb; ❌ FAQ rich result (Aug 2023 থেকে শুধু govt/health site) — schema valid, AI/semantic এর জন্য রাখা হয়েছে

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers.",
      "employee": [
        {
          "@id": "https://immtell.com/#gavin-webster"
        },
        {
          "@id": "https://immtell.com/#ewen-mckenzie"
        }
      ],
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder of Immtell and a former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later senior advisory roles at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence",
        "Skilled Worker visa",
        "Home Office visa decision-making",
        "UK immigration compliance"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/#ewen-mckenzie",
      "@type": "Person",
      "description": "Head of Sponsor Compliance at Immtell and a former Home Office sponsorship compliance specialist. Former Home Office Regional Compliance Manager who led teams of Home Office Compliance Officers carrying out sponsor licence audits, and former National Training Lead for sponsor compliance operations. 20 years with the Home Office, including 16 years specialising in sponsor compliance and sponsor management.",
      "jobTitle": "Head of Sponsor Compliance",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Sponsor Management System reporting",
        "Sponsor duties",
        "Right to Work checks",
        "Home Office compliance visits"
      ],
      "name": "Ewen McKenzie",
      "sameAs": [
        "https://www.linkedin.com/in/ewen-mckenzie-020289200/"
      ],
      "url": "https://immtell.com/about/ewen-mckenzie",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/business/uk-immigration/protect-your-sponsor-licence#service",
      "@type": "Service",
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Immigration compliance audits, mock audits, sponsor duty training and Home Office compliance-visit preparation for UK sponsor licence holders, informed by a former Home Office sponsorship compliance specialist.",
      "name": "Sponsor Licence Compliance and Mock Audits",
      "provider": {
        "@id": "https://immtell.com/#organization"
      },
      "serviceType": "UK sponsor licence compliance support",
      "url": "https://immtell.com/business/uk-immigration/protect-your-sponsor-licence"
    },
    {
      "@id": "https://immtell.com/business/uk-immigration/protect-your-sponsor-licence#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Business Services",
          "position": 2
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/business/uk-immigration/protect-your-sponsor-licence",
          "name": "Protect Your Sponsor Licence",
          "position": 3
        }
      ]
    },
    {
      "@id": "https://immtell.com/business/uk-immigration/protect-your-sponsor-licence#faq",
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "A Home Office compliance visit can occur at any time and does not always follow advance notice. Common triggers include: a new sponsor licence application, a request for additional CoS allocation, a visa application by a sponsored worker, or routine UKVI compliance activity. Visits can also be triggered by intelligence, for example, a reporting failure, an HMRC discrepancy, or a worker complaint. The safest approach is to treat compliance readiness as a permanent state, not a pre-visit exercise."
          },
          "name": "What triggers a Home Office compliance visit?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "During a Home Office compliance visit, officials will typically review: HR and immigration management systems; right to work documentation for all employees; sponsored worker files (including contracts, pay records and contact details); whether changes affecting sponsored workers (salary, role, location) have been reported via the SMS within the required timeframe; and whether key personnel, the Authorising Officer, Level 1 User and Key Contact, understand and are actively fulfilling their sponsor duties. The compliance visit assesses both documentation and practice"
          },
          "name": "What does the Home Office look for during a compliance audit?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "No. Immtell's compliance audit is a private engagement between us and your organisation, nothing is reported externally and nothing is triggered with the Home Office as a result. The purpose is to identify what a Home Office inspector would find, fix it before they do, and produce a written record of your compliance activity. It is specifically designed to replicate the Home Office compliance visit process so that if UKVI does visit, you are prepared."
          },
          "name": "Is your compliance audit the same as a Home Office audit?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The Compliance Review Report contains four components: a written findings summary of your current compliance position; a Red / Amber / Green (RAG) rating across all key areas to show where risks are high, moderate or low; a Compliance Improvement Plan with prioritised recommendations and suggested owners; and a virtual follow-up meeting to walk through the findings and answer HR and management questions. The report is yours to keep as a documented record of proactive compliance activity."
          },
          "name": "What does the RAG Compliance Review Report include?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "At minimum, annually. More frequently if: you have grown your sponsored workforce significantly in the past 12 months; your Authorising Officer, Level 1 User or Key Contact has changed; you have received any communication from the Home Office; you have undergone a corporate restructure, merger or acquisition; or you operate across multiple sites. The Home Office does not announce most compliance visits, there is no period you can use as a final preparation window."
          },
          "name": "How often should sponsor licence systems be reviewed?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Sponsors must keep, for each sponsored worker: a copy of their right to work evidence; contact details (address and telephone number); their employment contract; evidence of their current salary; their job title and work location; and records of any changes to these details. Records must be current, accessible, and available for immediate compliance visit, not archived or stored in a format the Home Office cannot access quickly during a visit. Records must also be retained for a defined period after the worker leaves. Our audit checks all of these against current Home Office guidance."
          },
          "name": "What records must sponsors keep for sponsored workers?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Both options cover the same scope, sponsor licence management, sponsored worker file review, right to work compliance review, and HR systems assessment. The difference is how we observe your systems. A remote audit is conducted via video call with secure document sharing and works well for organisations with a small sponsored population and mature HR systems. An on-site audit involves attendance at your premises, which allows us to observe how your HR processes work in practice, not just how they are documented. For first-time audits or larger populations, on-site attendance typically produces a more thorough report."
          },
          "name": "What is the difference between a remote and on-site compliance audit?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. We provide standalone training sessions covering sponsor duties, right to work compliance procedures, and the most common compliance failures. Training is available for HR teams, line managers and Authorising Officers, and can be delivered remotely or in person. It can be taken independently of an audit, as a follow-on from the Compliance Improvement Plan recommendations, or included as part of our monthly support package depending on the agreed scope."
          },
          "name": "Can compliance training be delivered to HR teams or managers?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. For organisations entering a 12-month compliance support arrangement, the initial audit is priced at £1,500–£2,000 + VAT, a reduced entry investment reflecting the ongoing commitment. The arrangement then continues at £750–£1,500 per month: direct access to experienced compliance guidance when issues arise, no ticketing systems, no delays. Training for HR teams, line managers, and Authorising Officers can also be included within the monthly arrangement depending on the agreed scope. For organisations that prefer a standalone one-off review, this is available from £4,000 + VAT. For most active sponsors, the 12-month arrangement is the more practical choice; it means your compliance position is maintained continuously, not just reviewed at a single point in time."
          },
          "name": "Can you provide ongoing compliance support after the audit?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "For organisations entering a 12-month compliance support arrangement, the initial Independent Compliance Review is priced at £1,500–£2,000 + VAT. This includes a structured audit against real Home Office requirements, identification of compliance gaps, a RAG-rated Compliance Review Report, and a virtual follow-up meeting. Ongoing oversight then continues at £750–£1,500 per month for the 12-month arrangement. Optional add-on: sponsored worker interviews (up to 3 workers) at £500 + VAT. For organisations that prefer a standalone one-off audit, this is available from £4,000 + VAT. The exact cost depends on the size and complexity of your sponsored workforce and the current state of your internal systems."
          },
          "name": "How much does a sponsor licence compliance audit cost?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. Certain compliance functions can be handled on an advisory basis, for example, guidance on SMS reporting, support responding to Home Office queries, advice on changes affecting sponsored workers, and preparation for compliance visits. Full operational management of the SMS is possible where Immtell is added as a Level 1 User after the licence is granted. What cannot be outsourced is the Authorising Officer responsibility, the AO must be a senior person within your organisation who holds personal accountability for the licence."
          },
          "name": "Can immigration compliance be outsourced?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. If you have received notice of a Home Office compliance visit, we can conduct an accelerated pre-visit review, assessing your files, records and systems against the areas the Home Office will examine, identifying the most urgent gaps, and providing a prioritised fix-list before the compliance visit date. The sooner you engage us after receiving notice, the more preparation time is available. If you have not received notice but want to prepare proactively, our standard compliance audit is the right starting point."
          },
          "name": "Can you help us prepare for a Home Office compliance visit we have already been notified of?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Right to work checks apply to all employees. British citizens, EU nationals, settled workers and overseas workers, regardless of how they were recruited. Checks must be completed before employment begins, and evidence must be retained throughout employment and for a defined period after it ends. An employer who fails to conduct a compliant check and employs someone without the right to work can face a civil penalty of up to £60,000 per worker under current Home Office penalty levels. Our compliance audit reviews a sample of all employee types, not just sponsored workers."
          },
          "name": "Do right to work checks apply to all employees or only sponsored workers?"
        }
      ]
    }
  ]
}
```
</details>

### /privacy-policy
- **URL:** https://immtell.com/privacy-policy · **Type:** Legal · **Webflow page:**  (`6a903c672679378ad028ac5d`)
- **বর্তমান অবস্থা:** JSON valid, schema types: BreadcrumbList, ContactPoint, ImageObject, ListItem, Organization, Person, PostalAddress, PropertyValue, WebPage, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "Organization",
      "@id": "https://immtell.com/#organization",
      "name": "Immtell",
      "url": "https://immtell.com",
      "logo": {
        "@type": "ImageObject",
        "@id": "https://immtell.com/#logo",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "foundingDate": "2023",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "email": "info@immtell.com",
      "telephone": "+44-20-3910-6641",
      "address": [
        {
          "@type": "PostalAddress",
          "streetAddress": "Level 18, 40 Bank Street, Canary Wharf",
          "addressLocality": "London",
          "postalCode": "E14 5NR",
          "addressCountry": "GB"
        },
        {
          "@type": "PostalAddress",
          "streetAddress": "83 Queens Road",
          "addressLocality": "Brighton",
          "postalCode": "BN1 3XE",
          "addressCountry": "GB"
        }
      ],
      "contactPoint": {
        "@type": "ContactPoint",
        "contactType": "customer service",
        "telephone": "+44-20-3910-6641",
        "email": "info@immtell.com",
        "areaServed": "GB",
        "availableLanguage": "English"
      },
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ]
    },
    {
      "@type": "WebSite",
      "@id": "https://immtell.com/#website",
      "name": "Immtell",
      "url": "https://immtell.com",
      "inLanguage": "en-GB",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@type": "Person",
      "@id": "https://immtell.com/#gavin-webster",
      "name": "Gavin Webster",
      "jobTitle": "Founder and Managing Director",
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      },
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ]
    },
    {
      "@type": "WebPage",
      "@id": "https://immtell.com/privacy-policy#webpage",
      "name": "Privacy Policy",
      "url": "https://immtell.com/privacy-policy",
      "isPartOf": {
        "@id": "https://immtell.com/#website"
      },
      "about": {
        "@id": "https://immtell.com/#organization"
      },
      "inLanguage": "en-GB",
      "dateModified": "2024-11-12",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@type": "BreadcrumbList",
      "@id": "https://immtell.com/privacy-policy#breadcrumb",
      "itemListElement": [
        {
          "@type": "ListItem",
          "position": 1,
          "name": "Home",
          "item": "https://immtell.com"
        },
        {
          "@type": "ListItem",
          "position": 2,
          "name": "Privacy Policy",
          "item": "https://immtell.com/privacy-policy"
        }
      ]
    }
  ]
}
```
</details>

### /business/uk-immigration/apply-for-a-sponsor-licence
- **URL:** https://immtell.com/business/uk-immigration/apply-for-a-sponsor-licence · **Type:** Service · **Webflow page:**  (`6a8c7ce5053fb7a2ccbdcc20`)
- **বর্তমান অবস্থা:** JSON valid, schema types: Answer, BreadcrumbList, ContactPoint, Country, FAQPage, ImageObject, ListItem, Organization, Person, PostalAddress, ProfessionalService, PropertyValue, Question, Service, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |
| registered script schemaApplySponsorLicence | Critical | page settings schema এর পাশাপাশি পুরনো script লোড হয় | page থেকে script remove |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb; ❌ FAQ rich result (Aug 2023 থেকে শুধু govt/health site) — schema valid, AI/semantic এর জন্য রাখা হয়েছে

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/business/uk-immigration/apply-for-a-sponsor-licence#service-page",
      "@type": "Service",
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Full UK sponsor licence application support: route assessment, evidence preparation, key personnel review, and submission, handled personally by a former Home Office officer.",
      "name": "UK Sponsor Licence Application",
      "provider": {
        "@id": "https://immtell.com/#organization"
      },
      "serviceType": "Sponsor licence application",
      "url": "https://immtell.com/business/uk-immigration/apply-for-a-sponsor-licence"
    },
    {
      "@id": "https://immtell.com/business/uk-immigration/apply-for-a-sponsor-licence#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Business Services",
          "position": 2
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/business/uk-immigration/apply-for-a-sponsor-licence",
          "name": "Apply for a Sponsor Licence",
          "position": 3
        }
      ]
    },
    {
      "@id": "https://immtell.com/business/uk-immigration/apply-for-a-sponsor-licence#faq",
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. In certain commercial scenarios, holding both a Skilled Worker licence and a Global Business Mobility (GBM) Senior or Specialist Worker licence simultaneously provides operational flexibility, for example where a business is both recruiting new overseas hires and transferring senior employees from an overseas entity. A Combined licence is assessed on a case-by-case basis and must align with genuine vacancy requirements. We assess whether a combined structure is appropriate before any application is submitted."
          },
          "name": "Can a business hold more than one sponsor licence type at the same time?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. The Home Office does not require prior sponsorship experience. Most businesses applying for the first time have never sponsored a worker before. What matters is whether your business is genuine, actively trading, and has the right people and processes in place to meet ongoing sponsor duties. First-time applicants receive approvals regularly; the quality of preparation determines the outcome, not sponsorship history."
          },
          "name": "Can I apply for a UK sponsor licence if my business has never sponsored anyone before?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes, you can. The Home Office application form is publicly available and there is no legal requirement to use a professional adviser. The consideration is the consequence of a refusal: a cooling-off period of up to 6 months during which you cannot sponsor any overseas workers. Most refusals are caused not by ineligibility but by documentation gaps or failure to address Home Office concerns proactively. Professional preparation exists specifically to reduce that risk. There is also a regulatory point: UK immigration advice must come from an IAA-registered firm or barrister. Unregistered advisers are operating unlawfully."
          },
          "name": "Can I handle the sponsor licence application myself without professional help?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes, if the person requires a UK work visa. Without a sponsor licence, you cannot issue a Certificate of Sponsorship (CoS), which is required for most UK work visas including the Skilled Worker visa. If the person already holds British citizenship, settled status (ILR), pre-settled status, or another visa that permits the work you are offering, a sponsor licence is not required for that individual. We can confirm which applies to your situation quickly."
          },
          "name": "Do I need a sponsor licence to hire someone from overseas?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. A UK-registered legal entity must hold the sponsor licence. This can include a UK branch or subsidiary of an overseas company. An overseas parent company cannot hold the licence directly. If you are an overseas business establishing a UK presence, you would typically incorporate a UK company first. Depending on your stage of establishment, the UK Expansion Worker licence may be relevant: it is specifically designed for overseas businesses setting up UK operations before they are fully trading."
          },
          "name": "Does my business need to be registered in the UK to apply for a sponsor licence?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "No. Most UK sponsor licences do not expire. The exceptions are the Scale Up Worker and UK Expansion Worker licences, which are both limited to 4 years. Regardless of licence type, the Home Office can suspend, downgrade or revoke a licence if duties are not met. This is why ongoing compliance matters as much as the initial application."
          },
          "name": "Do sponsor licences need renewing?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. Once your sponsor licence is granted, we can support CoS allocation requests, assignment, and any queries or refusals from the Home Office. We can also act as an additional Level 1 User on your Sponsor Management System (SMS), which means we can manage CoS requests and reporting directly without you needing to handle every step internally."
          },
          "name": "Do you support Certificates of Sponsorship (CoS) allocation requests and refusals?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Standard processing typically takes around 8 weeks from the date of submission. Priority processing, available at an additional Home Office fee, can reduce this to approximately 10 working days. Note: priority processing is not available for UK Expansion Worker licence applications. Newer businesses, higher-scrutiny sectors, or applications where the Home Office has concerns may face additional checks, including a digital assessment, document review, or site visit, which can extend the timeline."
          },
          "name": "How long does it take to get a sponsor licence?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "No. Priority processing is available for most sponsor licence applications but is not available for UK Expansion Worker licence applications. For all other licence types, priority processing can reduce the standard processing time from approximately 8 weeks to approximately 10 working days, subject to an additional Home Office fee."
          },
          "name": "Is priority processing available for all sponsor licence types?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Most refusals are preventable. The most common causes are: the business cannot demonstrate it is genuine and actively trading; the job vacancy is not credibly evidenced as a real and necessary role; key personnel are assessed as unsuitable or not available in practice; documentation is incomplete or in the wrong format; or the submission fails to address what the Home Office is likely to scrutinise. A refusal triggers a cooling-off period of up to 6 months, during which you cannot sponsor any overseas workers."
          },
          "name": "What are the main reasons a sponsor licence application gets refused?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Once your licence is approved, you gain access to the Sponsor Management System (SMS) and can begin assigning Certificates of Sponsorship to eligible overseas workers. Your first immediate obligations include confirming your key personnel on the SMS, understanding your ongoing reporting duties, and ensuring your Right to Work checking processes are in place. We provide a post-approval debrief covering all of these steps. Our Tier 3 package includes 90 days of post-approval support."
          },
          "name": "What happens after the sponsor licence is approved?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Before granting a licence, the Home Office may conduct a pre-licence compliance check, which can take the form of a digital assessment, a document review, or a physical site visit to your premises. This is more likely for newer businesses, higher-scrutiny sectors, and applications where the Home Office has identified concerns. A compliance check does not mean refusal; it means the Home Office wants to verify your business before granting the licence. Preparation significantly reduces the disruption. Our Tier 3 package includes pre-licence audit preparation and an Authorising Officer preparation call."
          },
          "name": "What is a pre-licence Home Office compliance check?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "It depends on your situation. For current fees and full package details, visit our dedicated fees page."
          },
          "name": "What does Immtell's sponsor licence service include, and which tier is right for my business?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The right route depends on your business structure and recruitment objective. Skilled Worker is for actively trading UK businesses hiring overseas workers long-term; workers can apply for ILR settlement after 5 years (under current rules, subject to review). GBM Senior/Specialist Worker is for overseas companies transferring senior or specialist employees to a linked UK entity; it is temporary, carries no settlement route, and requires corporate linkage. UK Expansion Worker is for overseas businesses establishing a UK presence before fully trading. A Combined licence covers businesses needing both Skilled Worker and GBM simultaneously. Scale Up is available for eligible fast-scaling businesses. We confirm the correct route as the first step of every engagement."
          },
          "name": "Which sponsor licence route do we need: Skilled Worker, GBM, or UK Expansion Worker?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Every application must name: an Authorising Officer (AO), the most senior person legally responsible for the licence, who must be legally resident and located in the UK; a Key Contact, the primary liaison with the Home Office (this role can be held by Immtell); and at least one Level 1 User, who accesses the SMS day-to-day, is usually required to be British, Irish, or settled (ILR) with limited exceptions, and must also be legally resident and located in the UK. The Home Office assesses each named person's suitability, availability, and capability before granting the licence. Immtell can be added as an additional Level 1 User once the licence is granted."
          },
          "name": "Who needs to be named on a UK sponsor licence as key personnel, and what are the requirements?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. If you already hold a sponsor licence and need to prepare for a Home Office compliance visit, this is covered under our Compliance Support service, see Protect Your Sponsor Licence →. If you are applying for a new licence and anticipate a pre-licence compliance check, our Tier 3 package includes specific preparation for that scenario."
          },
          "name": "Will you help us prepare for a Home Office audit?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. Immtell can serve as your Key Contact with the Home Office from the application stage. Once your licence is granted, we can also be added as an additional Level 1 User on your Sponsor Management System (SMS). This means we can assign your CoS, handle SMS reporting, and manage Home Office communications directly, without you needing to handle every step internally. This is particularly useful for businesses without dedicated immigration resource in-house."
          },
          "name": "Can Immtell act as our Key Contact or Level 1 User on the sponsor licence?"
        }
      ]
    }
  ]
}
```
</details>

### /resources/tools
- **URL:** https://immtell.com/resources/tools · **Type:** Resources hub · **Webflow page:**  (`6a8b8ad4264f7a970cb069dd`)
- **বর্তমান অবস্থা:** JSON valid, schema types: BreadcrumbList, CollectionPage, ContactPoint, Country, ImageObject, ItemList, ListItem, Organization, Person, PostalAddress, ProfessionalService, PropertyValue, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/resources/tools#webpage",
      "@type": "CollectionPage",
      "about": {
        "@id": "https://immtell.com/#organization"
      },
      "breadcrumb": {
        "@id": "https://immtell.com/resources/tools#breadcrumb"
      },
      "description": "Interactive checkers and calculators to help you understand where you stand, before you speak to our team. Answer a few questions and get a clear, immediate read on your situation.",
      "inLanguage": "en-GB",
      "isPartOf": {
        "@id": "https://immtell.com/#website"
      },
      "mainEntity": {
        "@id": "https://immtell.com/resources/tools#tools"
      },
      "name": "Tools",
      "url": "https://immtell.com/resources/tools"
    },
    {
      "@id": "https://immtell.com/resources/tools#tools",
      "@type": "ItemList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "description": "A quick self-assessment of how audit-ready your business is, with pointers on where to focus.",
          "name": "Compliance Health Check",
          "position": 1,
          "url": "https://immtell.com/resources/tool/compliance-health-check"
        },
        {
          "@type": "ListItem",
          "description": "Answer a few questions to see whether your business is likely to qualify for a sponsor licence.",
          "name": "Licence Eligibility Checker",
          "position": 2,
          "url": "https://immtell.com/resources/tool/licence-eligibility-checker"
        },
        {
          "@type": "ListItem",
          "description": "Estimate your exposure for illegal working penalties based on your circumstances.",
          "name": "Civil Penalty Calculator",
          "position": 3,
          "url": "https://immtell.com/resources/tool/civil-penalty-calculator"
        },
        {
          "@type": "ListItem",
          "description": "Find the right Standard Occupational Classification code for the role you want to sponsor.",
          "name": "SOC Code Lookup",
          "position": 4,
          "url": "https://immtell.com/resources/tool/soc-code-lookup"
        },
        {
          "@type": "ListItem",
          "description": "Answer a few questions to see which UK visa routes you may be eligible for.",
          "name": "Visa Route Finder",
          "position": 5,
          "url": "https://immtell.com/resources/tool/visa-route-finder"
        }
      ],
      "name": "Interactive tools",
      "numberOfItems": 5
    },
    {
      "@id": "https://immtell.com/resources/tools#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/resources",
          "name": "Resources",
          "position": 2
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/resources/tools",
          "name": "Tools",
          "position": 3
        }
      ]
    }
  ]
}
```
</details>

### /resources/visas-settlement-hub
- **URL:** https://immtell.com/resources/visas-settlement-hub · **Type:** Resources hub · **Webflow page:**  (`6a85d6c59dc242b9ee800ead`)
- **বর্তমান অবস্থা:** JSON valid, schema types: BreadcrumbList, CollectionPage, ContactPoint, Country, ImageObject, ItemList, ListItem, Organization, PeopleAudience, Person, PostalAddress, ProfessionalService, PropertyValue, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/resources/visas-settlement-hub#webpage",
      "@type": "CollectionPage",
      "about": {
        "@id": "https://immtell.com/#organization"
      },
      "audience": {
        "@type": "PeopleAudience",
        "audienceType": "Individuals applying for UK visas, settlement or British citizenship"
      },
      "breadcrumb": {
        "@id": "https://immtell.com/resources/visas-settlement-hub#breadcrumb"
      },
      "description": "Guides and updates for individuals on UK work, family, student and visitor visas, settlement (ILR) and British citizenship. From a former Home Office officer.",
      "inLanguage": "en-GB",
      "isPartOf": {
        "@id": "https://immtell.com/#website"
      },
      "lastReviewed": "2026-04-15",
      "mainEntity": {
        "@id": "https://immtell.com/resources/visas-settlement-hub#tools"
      },
      "name": "Visas & Settlement Resources Hub",
      "url": "https://immtell.com/resources/visas-settlement-hub"
    },
    {
      "@id": "https://immtell.com/resources/visas-settlement-hub#tools",
      "@type": "ItemList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "name": "Visa Route Finder",
          "position": 1,
          "url": "https://immtell.com/resources/tool/visa-route-finder"
        },
        {
          "@type": "ListItem",
          "name": "SOC Code Lookup",
          "position": 2,
          "url": "https://immtell.com/resources/tool/soc-code-lookup"
        }
      ],
      "name": "Interactive tools",
      "numberOfItems": 2
    },
    {
      "@id": "https://immtell.com/resources/visas-settlement-hub#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/resources",
          "name": "Resources",
          "position": 2
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/resources/visas-settlement-hub",
          "name": "Visas & Settlement Hub",
          "position": 3
        }
      ]
    }
  ]
}
```
</details>

### /resources/sponsor-licence-hub
- **URL:** https://immtell.com/resources/sponsor-licence-hub · **Type:** Resources hub · **Webflow page:**  (`6a855b6bb3d0c4f127bfaec7`)
- **বর্তমান অবস্থা:** JSON valid, schema types: BreadcrumbList, BusinessAudience, CollectionPage, ContactPoint, Country, ImageObject, ItemList, ListItem, Organization, Person, PostalAddress, ProfessionalService, PropertyValue, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/resources/sponsor-licence-hub#webpage",
      "@type": "CollectionPage",
      "about": {
        "@id": "https://immtell.com/#organization"
      },
      "audience": {
        "@type": "BusinessAudience",
        "audienceType": "UK employers"
      },
      "breadcrumb": {
        "@id": "https://immtell.com/resources/sponsor-licence-hub#breadcrumb"
      },
      "description": "Guides, tools and updates for UK employers on applying for a sponsor licence, staying compliant and managing sponsor duties. From a former Home Office officer.",
      "inLanguage": "en-GB",
      "isPartOf": {
        "@id": "https://immtell.com/#website"
      },
      "lastReviewed": "2026-06",
      "mainEntity": {
        "@id": "https://immtell.com/resources/sponsor-licence-hub#tools"
      },
      "name": "Sponsor Licence Resources Hub",
      "url": "https://immtell.com/resources/sponsor-licence-hub"
    },
    {
      "@id": "https://immtell.com/resources/sponsor-licence-hub#tools",
      "@type": "ItemList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "name": "Licence Eligibility Checker",
          "position": 1,
          "url": "https://immtell.com/resources/tool/licence-eligibility-checker"
        },
        {
          "@type": "ListItem",
          "name": "Civil Penalty Calculator",
          "position": 2,
          "url": "https://immtell.com/resources/tool/civil-penalty-calculator"
        },
        {
          "@type": "ListItem",
          "name": "Glossary",
          "position": 3,
          "url": "https://immtell.com/resources/glossary"
        }
      ],
      "name": "Interactive tools",
      "numberOfItems": 3
    },
    {
      "@id": "https://immtell.com/resources/sponsor-licence-hub#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/resources",
          "name": "Resources",
          "position": 2
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/resources/sponsor-licence-hub",
          "name": "Sponsor Licence Hub",
          "position": 3
        }
      ]
    }
  ]
}
```
</details>

### /resources
- **URL:** https://immtell.com/resources · **Type:** Resources hub · **Webflow page:**  (`6a843d1d52b1b319c4b8ab35`)
- **বর্তমান অবস্থা:** JSON valid, schema types: BreadcrumbList, CollectionPage, ContactPoint, Country, ImageObject, ListItem, Organization, Person, PostalAddress, ProfessionalService, PropertyValue, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/resources#collectionpage",
      "@type": "CollectionPage",
      "about": {
        "@id": "https://immtell.com/#organization"
      },
      "description": "Guides, analysis and practical tools on UK immigration for employers and individual applicants.",
      "isPartOf": {
        "@id": "https://immtell.com/#website"
      },
      "name": "Immtell UK Immigration Resources",
      "url": "https://immtell.com/resources"
    },
    {
      "@id": "https://immtell.com/resources#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/resources",
          "name": "Resources",
          "position": 2
        }
      ]
    }
  ]
}
```
</details>

### /contact-us
- **URL:** https://immtell.com/contact-us · **Type:** Contact · **Webflow page:**  (`6a83332c9bfc275db4ba9209`)
- **বর্তমান অবস্থা:** JSON valid, schema types: BreadcrumbList, ContactPage, ContactPoint, ImageObject, ListItem, Organization, Person, PostalAddress, PropertyValue, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "Organization",
      "@id": "https://immtell.com/#organization",
      "name": "Immtell",
      "url": "https://immtell.com",
      "logo": {
        "@type": "ImageObject",
        "@id": "https://immtell.com/#logo",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "foundingDate": "2023",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "email": "info@immtell.com",
      "telephone": "+44-20-3910-6641",
      "address": [
        {
          "@type": "PostalAddress",
          "streetAddress": "Level 18, 40 Bank Street, Canary Wharf",
          "addressLocality": "London",
          "postalCode": "E14 5NR",
          "addressCountry": "GB"
        },
        {
          "@type": "PostalAddress",
          "streetAddress": "83 Queens Road",
          "addressLocality": "Brighton",
          "addressRegion": "East Sussex",
          "postalCode": "BN1 3XE",
          "addressCountry": "GB"
        }
      ],
      "contactPoint": {
        "@type": "ContactPoint",
        "contactType": "customer service",
        "telephone": "+44-20-3910-6641",
        "email": "info@immtell.com",
        "areaServed": "GB",
        "availableLanguage": "English"
      },
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ]
    },
    {
      "@type": "WebSite",
      "@id": "https://immtell.com/#website",
      "name": "Immtell",
      "url": "https://immtell.com",
      "inLanguage": "en-GB",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@type": "Person",
      "@id": "https://immtell.com/#gavin-webster",
      "name": "Gavin Webster",
      "jobTitle": "Founder and Managing Director",
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      },
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ]
    },
    {
      "@type": "ContactPage",
      "@id": "https://immtell.com/contact-us#webpage",
      "url": "https://immtell.com/contact-us",
      "name": "Contact Immtell | UK Immigration Experts",
      "description": "Get in touch with Immtell's immigration team. Speak directly with a former Home Office officer about sponsor licences, compliance, or UK visa applications.",
      "isPartOf": {
        "@id": "https://immtell.com/#website"
      },
      "about": {
        "@id": "https://immtell.com/#organization"
      },
      "mainEntity": {
        "@id": "https://immtell.com/#organization"
      },
      "breadcrumb": {
        "@id": "https://immtell.com/contact-us#breadcrumb"
      },
      "inLanguage": "en-GB"
    },
    {
      "@type": "BreadcrumbList",
      "@id": "https://immtell.com/contact-us#breadcrumb",
      "itemListElement": [
        {
          "@type": "ListItem",
          "position": 1,
          "name": "Home",
          "item": "https://immtell.com"
        },
        {
          "@type": "ListItem",
          "position": 2,
          "name": "Contact",
          "item": "https://immtell.com/contact-us"
        }
      ]
    }
  ]
}
```
</details>

### /home-individual
- **URL:** https://immtell.com/home-individual · **Type:** Home (Individuals) · **Webflow page:**  (`6a7c5532dce29aceac102a8e`)
- **বর্তমান অবস্থা:** JSON valid, schema types: Answer, BreadcrumbList, CollectionPage, ContactPoint, Country, FAQPage, ImageObject, ListItem, Organization, Person, PostalAddress, ProfessionalService, PropertyValue, Question, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb; ❌ FAQ rich result (Aug 2023 থেকে শুধু govt/health site) — schema valid, AI/semantic এর জন্য রাখা হয়েছে

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/home-individual#collectionpage",
      "@type": "CollectionPage",
      "about": {
        "@id": "https://immtell.com/#organization"
      },
      "description": "Immtell's UK visa, settlement and citizenship services for individuals and families, led by a former Home Office officer.",
      "isPartOf": {
        "@id": "https://immtell.com/#website"
      },
      "name": "UK Immigration for Individuals",
      "url": "https://immtell.com/home-individual"
    },
    {
      "@id": "https://immtell.com/home-individual#breadcrumb",
      "@type": "BreadcrumbList",
      "itemListElement": [
        {
          "@type": "ListItem",
          "item": "https://immtell.com",
          "name": "Home",
          "position": 1
        },
        {
          "@type": "ListItem",
          "item": "https://immtell.com/home-individual",
          "name": "Individuals",
          "position": 2
        }
      ]
    },
    {
      "@id": "https://immtell.com/home-individual#faq",
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "You are not legally required to use an immigration adviser. However, UK visa applications involve strict documentation requirements, and a single error, a missing document, an inconsistency between your application and your Certificate of Sponsorship, or an incorrect answer, can result in refusal. Immtell prepares applications to reduce that risk. Whether it is worth using a professional depends on the complexity of your situation and the consequences of a refusal for your plans."
          },
          "name": "Do I need an immigration adviser to apply for a UK visa?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Gavin Webster spent 13+ years inside the UK Home Office, including 6+ years as a Visa Officer in British diplomatic missions overseas, assessing and deciding visa applications of the types Immtell now supports. He later held senior roles at EY and PwC/Vialto. Immtell is regulated by the Immigration Advice Authority (IAA, formerly OISC), registration number F202200109."
          },
          "name": "What qualifications does Immtell's founder have?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. Immtell is on the IAA register (F202200109). Under UK law, only IAA or SRA registered firms can legally provide immigration advice. If an individual or firm is providing immigration advice without IAA or SRA registration, they are acting illegally."
          },
          "name": "Is Immtell regulated to give immigration advice?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "A 30-minute consultation costs £150 + VAT and is conducted via Zoom. A 15-minute session costs £55 + VAT, and a 60-minute session costs £280 + VAT. Home Office application fees are separate; they are never included in Immtell's invoice."
          },
          "name": "How much does an immigration consultation cost?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "It depends on the visa route. The Graduate visa, UK Ancestry visa, and Youth Mobility Scheme do not require a job offer. The Skilled Worker visa does require a confirmed job offer from a UK employer that holds a sponsor licence. If you do not have a job offer, a consultation can help identify which routes are available to you."
          },
          "name": "Can I apply for a UK visa without a job offer?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "A refusal creates a record that is visible on all future UK visa applications and can affect your credibility with future Visa Officers. It does not automatically prevent reapplication, but understanding why the refusal happened and addressing it correctly before resubmitting is important. Immtell can help you review the refusal reasons and prepare a stronger application."
          },
          "name": "What happens if my UK visa application is refused?"
        }
      ]
    }
  ]
}
```
</details>

### /
- **URL:** https://immtell.com/ · **Type:** Home (Business) · **Webflow page:**  (`6a62296f2cc22231b28c6477`)
- **বর্তমান অবস্থা:** JSON valid, schema types: Answer, ContactPoint, Country, EntryPoint, FAQPage, ImageObject, Organization, Person, PostalAddress, ProfessionalService, PropertyValue, Question, SearchAction, WebSite

| সমস্যা | Severity | কারণ | সমাধান |
|---|---|---|---|
| domain www.immtell.com -> immtell.com (canonical) | Warning | Schema URL www.immtell.com কিন্তু canonical https://immtell.com — WebPage url canonical এর সাথে মেলে না | fixed code এ সংশোধিত |

- **কোথায় বসবে:** Page Settings → Schema markup (`jsonLdSchema`)
- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Organization (logo/knowledge panel signal); ❌ FAQ rich result (Aug 2023 থেকে শুধু govt/health site) — schema valid, AI/semantic এর জন্য রাখা হয়েছে

<details><summary>Fixed JSON-LD</summary>

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@id": "https://immtell.com/#organization",
      "@type": "Organization",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "contactPoint": {
        "@type": "ContactPoint",
        "areaServed": "GB",
        "availableLanguage": "English",
        "contactType": "customer service",
        "email": "info@immtell.com",
        "telephone": "+44-20-3910-6641"
      },
      "description": "UK immigration consultancy helping employers apply for and keep a sponsor licence, stay compliant with Home Office sponsor duties, and sponsor overseas workers on the Skilled Worker visa. Also supports individuals with UK visa, settlement and citizenship applications.",
      "founder": {
        "@id": "https://immtell.com/#gavin-webster"
      },
      "foundingDate": "2023",
      "identifier": {
        "@type": "PropertyValue",
        "name": "IAA Registration Number",
        "value": "F202200109"
      },
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "knowsAbout": [
        "UK sponsor licence",
        "Sponsor licence compliance",
        "Certificate of Sponsorship",
        "Skilled Worker visa",
        "Home Office sponsor duties",
        "Right to Work checks",
        "UK settlement and citizenship"
      ],
      "logo": {
        "@id": "https://immtell.com/#logo",
        "@type": "ImageObject",
        "url": "https://cdn.prod.website-files.com/6a62296c2cc22231b28c63f8/6ab66a982de02804bb4638b4_immtell-logoType%20WP.png"
      },
      "name": "Immtell",
      "sameAs": [
        "https://www.linkedin.com/company/immtell-ltd/",
        "https://maps.app.goo.gl/FReicNUDrWEFp8Dz8"
      ],
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#website",
      "@type": "WebSite",
      "inLanguage": "en-GB",
      "name": "Immtell",
      "potentialAction": {
        "@type": "SearchAction",
        "target": {
          "@type": "EntryPoint",
          "urlTemplate": "https://immtell.com/search?q={search_term_string}"
        }
      },
      "publisher": {
        "@id": "https://immtell.com/#organization"
      },
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#service",
      "@type": "ProfessionalService",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "GB",
        "addressLocality": "London",
        "postalCode": "E14 5NR",
        "streetAddress": "Level 18, 40 Bank Street, Canary Wharf"
      },
      "areaServed": {
        "@type": "Country",
        "name": "United Kingdom"
      },
      "description": "Regulated UK immigration advice for employers: sponsor licence applications, sponsor licence compliance, Certificates of Sponsorship, and Skilled Worker visas.",
      "image": {
        "@id": "https://immtell.com/#logo"
      },
      "name": "Immtell",
      "telephone": "+44-20-3910-6641",
      "url": "https://immtell.com"
    },
    {
      "@id": "https://immtell.com/#gavin-webster",
      "@type": "Person",
      "description": "Founder and Managing Director of Immtell. Former UK Home Office officer with 13+ years inside the Home Office, including 6+ years as a Visa Officer in British diplomatic missions, and later a senior immigration adviser at EY and PwC/Vialto. 23+ years in UK immigration.",
      "jobTitle": "Founder and Managing Director",
      "knowsAbout": [
        "UK sponsor licence compliance",
        "Skilled Worker visa",
        "Home Office sponsor duties"
      ],
      "name": "Gavin Webster",
      "sameAs": [
        "https://www.linkedin.com/in/gavin-webster-immtell-immigration/"
      ],
      "url": "https://immtell.com/about/gavin-webster",
      "worksFor": {
        "@id": "https://immtell.com/#organization"
      }
    },
    {
      "@id": "https://immtell.com/#faq",
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Usually yes. Most UK employers need a sponsor licence to hire workers who are not British or Irish, because the licence is what lets you assign the Certificate of Sponsorship that most UK work visas require."
          },
          "name": "Do I need a sponsor licence to hire from overseas?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Around 8 weeks from submission as standard, or about 10 working days with the Home Office priority service, which carries an extra Home Office fee. Priority is not available for UK Expansion Worker licence applications."
          },
          "name": "How long does it take to get a sponsor licence?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "It depends on the service and the scope of work. You will find the fee bands on each service page and the fees pages, and we confirm the figure for your situation on the first call."
          },
          "name": "How much does it cost to work with Immtell?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "A refusal can trigger a cooling-off period of up to six months before you can reapply. Most refusals come down to preparation, which is why we prepare the application against how the Home Office assesses it."
          },
          "name": "What happens if our application is refused?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. We prepare Home Office-ready business plans for routes that require one, including Self-Sponsorship, Innovator Founder, Global Talent, and Expansion Worker applications."
          },
          "name": "Do you write business plans for visa applications?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. Support for your own UK visa, settlement, and citizenship is in our separate section for individuals."
          },
          "name": "Can Immtell help individuals too?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "You get access to the Sponsor Management System and can assign Certificates of Sponsorship to eligible workers. We help you assign CoS, meet your ongoing sponsor duties, and handle anything the Home Office raises."
          },
          "name": "What happens after our sponsor licence is approved?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. We run compliance reviews and mock audits, train your team on sponsor duties, and help you respond to a Home Office query, request for information, or compliance visit."
          },
          "name": "We already hold a sponsor licence. Can you help us stay compliant?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "We manage the Home Office priority slot request process. Standard allocation requests can take up to 18 weeks; the priority route targets about 5 working days once a slot is secured."
          },
          "name": "What if our Certificate of Sponsorship allocation runs out?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. Some activities can be carried out on a visitor visa without a work visa. We assess what your employee can do before they travel, and handle the visitor visa application if one is needed."
          },
          "name": "Can you help with business visitors and short trips, not just sponsored workers?"
        },
        {
          "@type": "Question",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Yes. Immtell is regulated by the Immigration Advice Authority (IAA, formerly OISC), Registration No. F202200109, Level 1, which you can verify on the IAA public register. You work with a senior-level adviser throughout, led by founder Gavin Webster, a former Home Office officer."
          },
          "name": "Is Immtell regulated, and who will we deal with?"
        }
      ]
    }
  ]
}
```
</details>


## CMS collection templates

### Resources Template (`/resources-pages/*`)
- **কোথায়:** CMS field `schema-markup` (Rich Text → Embed → `<script type="application/ld+json">`), template এর Rich Text element এ bound
- **Item:** 111টা item এর schema পরীক্ষা ও সংশোধন (সব item, শুধু ৩টা sample নয়)

| Item | পরিবর্তন |
|---|---|
| uk-youth-mobility-scheme-visa | Organization identifier unified; Organization url normalised; Organization: added logo; Organization: added sameAs; WebSite url normalised; domain www.immtell.com -> immtell.com (canonical) |
| uk-visa-tracking-guide-stay-updated | Organization identifier unified; Organization url normalised; Organization: added logo; Organization: added sameAs; WebSite url normalised; domain www.immtell.com -> immtell.com (canonical) |
| uk-visa-sponsorship-in-the-uk-care-sector | Organization identifier unified; Organization url normalised; Organization: added logo; Organization: added sameAs; WebSite url normalised; domain www.immtell.com -> immtell.com (canonical) |
| uk-temporary-worker-religious-visa | Organization identifier unified; Organization url normalised; Organization: added logo; Organization: added sameAs; WebSite url normalised; domain www.immtell.com -> immtell.com (canonical) |
| uk-student-visa-application-student-visa | Organization identifier unified; Organization url normalised; Organization: added logo; Organization: added sameAs; WebSite url normalised; domain www.immtell.com -> immtell.com (canonical) |
| uk-minister-of-religion-visa | domain www.immtell.com -> immtell.com (canonical) |
| uk-international-sportsperson-visa-t2 | domain www.immtell.com -> immtell.com (canonical) |
| uk-india-young-professionals-scheme-visa | Organization identifier unified; Organization url normalised; Organization: added logo; Organization: added sameAs; WebSite url normalised; domain www.immtell.com -> immtell.com (canonical) |
| uk-hospitality-bridging-staff-shortages-with-visa-options | Organization identifier unified; Organization url normalised; Organization: added logo; Organization: added sameAs; WebSite url normalised; domain www.immtell.com -> immtell.com (canonical) |
| uk-health-and-care-worker-visa | Organization identifier unified; Organization url normalised; Organization: added logo; Organization: added sameAs; WebSite url normalised; domain www.immtell.com -> immtell.com (canonical) |
| uk-construction-immigration-visa-options | domain www.immtell.com -> immtell.com (canonical) |
| uk-citizenship-british-citizenship-by-descent-from-a-grandparent | Organization identifier unified; Organization url normalised; Organization: added logo; Organization: added sameAs; WebSite url normalised; domain www.immtell.com -> immtell.com (canonical) |
| uk-business-visitor-visa-a-guide-to-successful-applications | Organization identifier unified; Organization url normalised; Organization: added logo; Organization: added sameAs; WebSite url normalised; domain www.immtell.com -> immtell.com (canonical) |
| uk-business-residency-uk-self-sponsorship-and-expansion-worker-visas | Organization identifier unified; Organization url normalised; Organization: added logo; Organization: added sameAs; WebSite url normalised; domain www.immtell.com -> immtell.com (canonical) |
| uk-ancestry-visa | domain www.immtell.com -> immtell.com (canonical) |
| switch-from-ukraine-scheme-to-skilled-worker-visa | Organization identifier unified; Organization url normalised; Organization: added logo; Organization: added sameAs; WebSite url normalised; domain www.immtell.com -> immtell.com (canonical) |
| spouse-visa-uk-application-apply-for-partner-visa-in-2026 | Organization identifier unified; Organization url normalised; Organization: added logo; Organization: added sameAs; WebSite url normalised; domain www.immtell.com -> immtell.com (canonical) |
| indian-carers-and-nurses-seeking-work-in-the-uk | Organization identifier unified; Organization url normalised; Organization: added logo; Organization: added sameAs; WebSite url normalised; domain www.immtell.com -> immtell.com (canonical) |
| how-to-make-the-most-of-a-youth-mobility-visa-in-the-uk | Organization identifier unified; Organization url normalised; Organization: added logo; Organization: added sameAs; WebSite url normalised; domain www.immtell.com -> immtell.com (canonical) |
| home-office-contact-us | Organization identifier unified; Organization url normalised; Organization: added logo; Organization: added sameAs; WebSite url normalised; domain www.immtell.com -> immtell.com (canonical) |
| can-i-travel-after-my-citizenship-ceremony-and-before-receiving-my-first-british-passport | domain www.immtell.com -> immtell.com (canonical) |
| why-are-skilled-worker-visa-applications-being-refused-in-2025 | domain www.immtell.com -> immtell.com (canonical) |
| uk-innovator-founder-visa | domain www.immtell.com -> immtell.com (canonical) |
| uk-temporary-worker-government-authorised-exchange-visa | domain www.immtell.com -> immtell.com (canonical) |
| uk-graduate-visa | domain www.immtell.com -> immtell.com (canonical) |
| uk-dependent-visas | domain www.immtell.com -> immtell.com (canonical) |
| top-10-tips-for-a-successful-uk-visit-visa-application-in-2025 | domain www.immtell.com -> immtell.com (canonical) |
| mock-audit-with-an-ex-home-office-officer | domain www.immtell.com -> immtell.com (canonical) |
| sponsor-licence-cost-for-smes-in-brighton-sussex | domain www.immtell.com -> immtell.com (canonical) |
| guide-to-documents-required-for-a-uk-tourist-visa-from-india | domain www.immtell.com -> immtell.com (canonical) |
| why-right-to-work-checks-alone-wont-keep-you-compliant | domain www.immtell.com -> immtell.com (canonical) |
| uk-tourist-visa-from-india | domain www.immtell.com -> immtell.com (canonical) |
| uk-global-talent-visa | domain www.immtell.com -> immtell.com (canonical) |
| uk-fiance-visa | domain www.immtell.com -> immtell.com (canonical) |
| pros-and-cons-of-sponsoring-an-immigrant-in-uk | domain www.immtell.com -> immtell.com (canonical) |
| how-much-does-a-uk-sponsor-licence-cost-in-2025 | domain www.immtell.com -> immtell.com (canonical) |
| uk-student-visa | domain www.immtell.com -> immtell.com (canonical) |
| uk-skilled-worker-dependant-visa-process | domain www.immtell.com -> immtell.com (canonical) |
| uk-short-term-study-visa | domain www.immtell.com -> immtell.com (canonical) |
| uk-civil-partner-visa | domain www.immtell.com -> immtell.com (canonical) |
| the-real-risk-of-sponsoring-overseas-workers-in-the-uk-and-how-to-avoid-fines | domain www.immtell.com -> immtell.com (canonical) |
| the-most-trusted-sponsor-licence-advisers-in-the-uk-2025-guide | domain www.immtell.com -> immtell.com (canonical) |
| an-honest-review-of-the-uk-sponsor-licence-process | domain www.immtell.com -> immtell.com (canonical) |
| uk-creative-visitor-visa | domain www.immtell.com -> immtell.com (canonical) |
| uk-sports-visitor-visa | domain www.immtell.com -> immtell.com (canonical) |
| uk-medical-visitor-visa | domain www.immtell.com -> immtell.com (canonical) |
| uk-marriage-visitor-visa | domain www.immtell.com -> immtell.com (canonical) |
| will-the-home-office-exercise-discretion-when-applying-for-british-citizenship | domain www.immtell.com -> immtell.com (canonical) |
| uk-visa-invitation-letter-sample | domain www.immtell.com -> immtell.com (canonical) |
| uk-unmarried-partner-visa | domain www.immtell.com -> immtell.com (canonical) |
| uk-service-supplier-visa-global-business-mobility-visa | domain www.immtell.com -> immtell.com (canonical) |
| uk-family-visitor-visa | domain www.immtell.com -> immtell.com (canonical) |
| top-5-best-immigration-consultants-in-the-uk | domain www.immtell.com -> immtell.com (canonical) |
| the-hidden-risks-of-not-preparing-for-a-home-office-compliance-visit | domain www.immtell.com -> immtell.com (canonical) |
| the-biggest-problems-companies-face-during-a-sponsor-licence-application | domain www.immtell.com -> immtell.com (canonical) |
| guide-to-successfully-obtaining-a-uk-work-visa-in-2025 | domain www.immtell.com -> immtell.com (canonical) |
| uk-secondment-worker-visa-global-business-mobility-visa | domain www.immtell.com -> immtell.com (canonical) |
| uk-dual-nationality-and-multiple-citizenship | domain www.immtell.com -> immtell.com (canonical) |
| step-by-step-guide-to-the-uk-spouse-visa-application-process | domain www.immtell.com -> immtell.com (canonical) |
| right-to-work-guidance-supplementary-employment-students | domain www.immtell.com -> immtell.com (canonical) |
| how-to-tell-if-your-sponsor-licence-is-at-risk | domain www.immtell.com -> immtell.com (canonical) |
| how-to-get-a-work-visa-in-the-uk | domain www.immtell.com -> immtell.com (canonical) |
| how-much-does-a-uk-visa-cost-in-2025 | domain www.immtell.com -> immtell.com (canonical) |
| expertise-of-immigration-law-firms-for-corporations-and-businesses | domain www.immtell.com -> immtell.com (canonical) |
| do-brighton-smes-need-a-sponsor-licence-to-hire-overseas-talent | domain www.immtell.com -> immtell.com (canonical) |
| business-visas-for-the-uk-guide | domain www.immtell.com -> immtell.com (canonical) |
| who-can-sponsor-me-in-the-uk--eligibility | domain www.immtell.com -> immtell.com (canonical) |
| what-happens-during-a-home-office-compliance-audit | domain www.immtell.com -> immtell.com (canonical) |
| what-activities-can-a-business-visitor-undertake-in-the-uk | domain www.immtell.com -> immtell.com (canonical) |
| ukvi-majority-english-speaking-countries | domain www.immtell.com -> immtell.com (canonical) |
| uk-spouse-and-partner-visa | domain www.immtell.com -> immtell.com (canonical) |
| graduate-trainee-visa-uk-global-business-mobility-visa | domain www.immtell.com -> immtell.com (canonical) |
| settle-in-the-uk--british-citizenship-through-naturalisation | domain www.immtell.com -> immtell.com (canonical) |
| how-to-get-a-skilled-worker-visa-uk | domain www.immtell.com -> immtell.com (canonical) |
| choose-the-right-uk-immigration-consultancy-for-your-business | domain www.immtell.com -> immtell.com (canonical) |
| avoid-uk-illegal-working-penalties-right-to-work-compliance-2025 | domain www.immtell.com -> immtell.com (canonical) |
| 7-common-sponsor-duties-hr-teams-miss | domain www.immtell.com -> immtell.com (canonical) |
| what-to-expect-from-a-home-office-pre-licence-compliance-check | domain www.immtell.com -> immtell.com (canonical) |
| what-is-the-skilled-worker-visa-in-the-uk | domain www.immtell.com -> immtell.com (canonical) |
| what-does-having-indefinite-leave-to-remain-mean | domain www.immtell.com -> immtell.com (canonical) |
| uk-expansion-worker-visa-global-business-mobility-visa | domain www.immtell.com -> immtell.com (canonical) |
| uk-business-visitor-visa | domain www.immtell.com -> immtell.com (canonical) |
| the-challenges-of-obtaining-a-cos-allocation | domain www.immtell.com -> immtell.com (canonical) |
| life-in-the-uk-test-2025-guide | domain www.immtell.com -> immtell.com (canonical) |
| how-much-do-uk-business-immigration-consultants-charge | domain www.immtell.com -> immtell.com (canonical) |
| home-office-sponsor-licence-holders-reporting-duties | domain www.immtell.com -> immtell.com (canonical) |
| guide-to-england-family-visas | domain www.immtell.com -> immtell.com (canonical) |
| common-right-to-work-check-mistakes-that-could-lead-to-civil-penalties | domain www.immtell.com -> immtell.com (canonical) |
| become-a-sponsor-steps-for-employers-and-businesses | domain www.immtell.com -> immtell.com (canonical) |
| uk-temporary-worker-international-agreement-visa | domain www.immtell.com -> immtell.com (canonical) |
| sponsor-licence-challenges-brighton-hr-teams-face-in-2025 | domain www.immtell.com -> immtell.com (canonical) |
| immigration-skills-charge-a-guide-for-employers | domain www.immtell.com -> immtell.com (canonical) |
| uk-temporary-worker-creative-visa | domain www.immtell.com -> immtell.com (canonical) |
| self-sponsorship-visa-uk | domain www.immtell.com -> immtell.com (canonical) |
| mistakes-brighton-employers-make-with-sponsor-licences | domain www.immtell.com -> immtell.com (canonical) |
| uk-scale-up-visa | domain www.immtell.com -> immtell.com (canonical) |
| uk-temporary-worker-charity-visa | domain www.immtell.com -> immtell.com (canonical) |
| top-10-sponsor-licence-mistakes-employers-still-make-in-2025 | domain www.immtell.com -> immtell.com (canonical) |
| understanding-legal-responsibilities-as-a-uk-sponsor-licence-holder | domain www.immtell.com -> immtell.com (canonical) |
| uk-tourist-visitor-visa | FAQ answer matched to page (£135); domain www.immtell.com -> immtell.com (canonical) |
| uk-skilled-worker-visa | domain www.immtell.com -> immtell.com (canonical) |
| uk-senior-specialist-worker-visa-global-business-mobility-visa | domain www.immtell.com -> immtell.com (canonical) |
| the-uk-immigration-process-a-guide-for-newcomers | domain www.immtell.com -> immtell.com (canonical) |
| prepare-for-a-home-office-immigration-compliance-audit | domain www.immtell.com -> immtell.com (canonical) |
| indefinite-leave-to-remain-settle-in-the-uk | domain www.immtell.com -> immtell.com (canonical) |
| in-house-hr-team-vs-external-immigration-support-which-is-more-cost-effective | domain www.immtell.com -> immtell.com (canonical) |
| how-to-respond-when-your-home-office-sponsor-licence-is-revoked | domain www.immtell.com -> immtell.com (canonical) |
| guide-to-right-to-work-checks-in-2025 | domain www.immtell.com -> immtell.com (canonical) |
| family-visas-join-your-family-in-the-uk | domain www.immtell.com -> immtell.com (canonical) |
| certificate-of-sponsorship-a-guide-for-employers | domain www.immtell.com -> immtell.com (canonical) |
| all-you-need-to-know-about-sponsor-licences | domain www.immtell.com -> immtell.com (canonical) |

- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb; ✅ Article

### News Template (`/resource-article/*`)
- **কোথায়:** CMS field `schema-markup` (Rich Text → Embed → `<script type="application/ld+json">`), template এর Rich Text element এ bound
- **Item:** 34টা item এর schema পরীক্ষা ও সংশোধন (সব item, শুধু ৩টা sample নয়)

| Item | পরিবর্তন |
|---|---|
| welcome-immigration-updates-from-the-uk-government-for-visitors | NewsArticle: added image from CMS featured-image; Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| update-for-uk-sponsor-licence-holders-renewal-process-changes | NewsArticle: added image from CMS featured-image; Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| upcoming-uk-immigration-fee-increases-2025 | NewsArticle: added image from CMS featured-image; Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| uks-new-electronic-travel-authorisation-eta-system | NewsArticle: added image from CMS featured-image; Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| uk-visa-and-sponsorship-fee-increases-from-9-april-2025 | Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| uk-sponsor-guidance-update--new-duties-for-sponsors | Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| uk-immigration-rule-changes-october-2025-key-updates-for-employers-and-applicants | Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| uk-immigration-rule-changes-july-2025-key-updates-for-employers-and-applicants | Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| uk-immigration-rule-changes-april-2025-key-updates-for-employers | Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| uk-immigration-rule-changes--march-2026-statement-of-changes | Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| uk-immigration-fees-increasing-from-8-april-2026 | Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| uk-immigration-changes-confirmed-from-22-july-2025 | Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| uk-immigration-changes-april-2026-what-employers-need-to-do-now | Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| transition-to-uk-evisa-what-you-need-to-know | NewsArticle: added image from CMS featured-image; Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| the-2025-uk-immigration-white-paper-key-proposals-risks-and-what-comes-next | Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| sponsor-management-system-update-for-skilled-worker-sponsorship | NewsArticle: added image from CMS featured-image; Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| significant-changes-to-uk-immigration-rules-from-4-april-2024 | NewsArticle: added image from CMS featured-image; Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| new-guidance-for-sponsors-of-care-workers-and-senior-care-workers | NewsArticle: added image from CMS featured-image; Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| major-reform-to-uk-settlement-ilr-planned | Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| mac-report-on-salary-thresholds | Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| key-uk-immigration-dates-for-2024 | NewsArticle: added image from CMS featured-image; Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| important-alert-uk-skilled-worker-visa-health-surcharge-changes | NewsArticle: added image from CMS featured-image; Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| immtell-opens-new-brighton-office-to-support-sussex-based-employers-and-individuals | Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| imminent-changes-in-uk-skilled-worker-visa-fees-insights-for-employers | NewsArticle: added image from CMS featured-image; Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| ihs-increase-delayed | NewsArticle: added image from CMS featured-image; Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| home-secretarys-statement-on-migration-july-2024 | NewsArticle: added image from CMS featured-image; Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| final-rollout-uk-eta-mandatory-for-european-visitors-from-april-2025 | NewsArticle: added image from CMS featured-image; Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| eta-requirement-in-effect-for-non-european-travellers-to-the-uk | NewsArticle: added image from CMS featured-image; Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| confirmed-increase-to-immigration-health-surcharge-ihs-on-6-february-2024 | NewsArticle: added image from CMS featured-image; Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| care-worker-recruitment-requirement-from-9-april-2025 | NewsArticle: added image from CMS featured-image; Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| brp-and-brc-extension-new-deadline-for-uk-visa-holders | NewsArticle: added image from CMS featured-image; Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| automatic-settled-status-grants-for-eligible-pre-settled-status-holders | NewsArticle: added image from CMS featured-image; Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| australia-extends-working-holiday-visa-eligibility | NewsArticle: added image from CMS featured-image; Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| act-now-assign-cos-before-sms-goes-offline-at-1800-on-21-july | NewsArticle: added image from CMS featured-image; Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |

- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb; ✅ Article

### Topics Template (`/topics/*`)
- **কোথায়:** CMS field `schema-markup` (Rich Text → Embed → `<script type="application/ld+json">`), template এর Rich Text element এ bound
- **Item:** 13টা item এর schema পরীক্ষা ও সংশোধন (সব item, শুধু ৩টা sample নয়)

| Item | পরিবর্তন |
|---|---|
| buyer-commercial | domain www.immtell.com -> immtell.com (canonical) |
| global-business-mobility | domain www.immtell.com -> immtell.com (canonical) |
| visitor-short-term | domain www.immtell.com -> immtell.com (canonical) |
| settlement-ilr-citizenship | domain www.immtell.com -> immtell.com (canonical) |
| family-visas | domain www.immtell.com -> immtell.com (canonical) |
| work-sponsored-routes | domain www.immtell.com -> immtell.com (canonical) |
| general | domain www.immtell.com -> immtell.com (canonical) |
| enforcement-revocations-suspensions | domain www.immtell.com -> immtell.com (canonical) |
| sponsor-duties | domain www.immtell.com -> immtell.com (canonical) |
| right-to-work | domain www.immtell.com -> immtell.com (canonical) |
| certificates-of-sponsorship | domain www.immtell.com -> immtell.com (canonical) |
| sponsor-licence-applications | domain www.immtell.com -> immtell.com (canonical) |
| compliance-mock-audits | domain www.immtell.com -> immtell.com (canonical) |

- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb

### Case Studies Template (`/business/case-study/*`)
- **কোথায়:** CMS field `schema-markup` (Rich Text → Embed → `<script type="application/ld+json">`), template এর Rich Text element এ bound
- **Item:** 5টা item এর schema পরীক্ষা ও সংশোধন (সব item, শুধু ৩টা sample নয়)

| Item | পরিবর্তন |
|---|---|
| uk-immigration-support-for-an-international-consultancy | Article: added image from CMS featured-image; Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| powering-up-a-uk-nuclear-project-by-overcoming-cross-border-workforce-challenges | Article: added image from CMS featured-image; Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| paving-the-way-for-a-global-tech-companys-expansion | Article: added image from CMS featured-image; Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| global-healthcare-recruitment-for-carers-and-nurses | Article: added image from CMS featured-image; Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| compliance-support-for-a-universitys-international-student-programme | Article: added image from CMS featured-image; Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |

- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb; ✅ Article

### Team Template (`/about/*`)
- **কোথায়:** CMS field `schema-markup` (Rich Text → Embed → `<script type="application/ld+json">`), template এর Rich Text element এ bound
- **Item:** 2টা item এর schema পরীক্ষা ও সংশোধন (সব item, শুধু ৩টা sample নয়)

| Item | পরিবর্তন |
|---|---|
| ewen-mckenzie | Ewen jobTitle = visible "Head of Sponsor Compliance"; Ewen: added sameAs; Gavin url -> profile page; Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |
| gavin-webster | Ewen jobTitle = visible "Head of Sponsor Compliance"; Ewen: added sameAs; Organization logo unified (PNG); domain www.immtell.com -> immtell.com (canonical) |

- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb; ✅ Profile page; ❌ FAQ rich result (Aug 2023 থেকে শুধু govt/health site) — schema valid, AI/semantic এর জন্য রাখা হয়েছে

### Sectors Template (`/business/sectors/*`)
- **কোথায়:** CMS field `structured-data` (Rich Text → Embed → `<script type="application/ld+json">`), template এর Rich Text element এ bound
- **Item:** 13টা item এর schema পরীক্ষা ও সংশোধন (সব item, শুধু ৩টা sample নয়)

| Item | পরিবর্তন |
|---|---|
| technology | Gavin jobTitle unified; Gavin url -> profile page; Organization logo unified (PNG); breadcrumb: removed non-existent /business/sectors level; domain www.immtell.com -> immtell.com (canonical) |
| sports-athletics | Gavin jobTitle unified; Gavin url -> profile page; Organization logo unified (PNG); breadcrumb: removed non-existent /business/sectors level; domain www.immtell.com -> immtell.com (canonical) |
| retail | Gavin jobTitle unified; Gavin url -> profile page; Organization logo unified (PNG); breadcrumb: removed non-existent /business/sectors level; domain www.immtell.com -> immtell.com (canonical) |
| professional-services | Gavin jobTitle unified; Gavin url -> profile page; Organization logo unified (PNG); breadcrumb: removed non-existent /business/sectors level; domain www.immtell.com -> immtell.com (canonical) |
| manufacturing-engineering | Gavin jobTitle unified; Gavin url -> profile page; Organization logo unified (PNG); breadcrumb: removed non-existent /business/sectors level; domain www.immtell.com -> immtell.com (canonical) |
| hospitality | Gavin jobTitle unified; Gavin url -> profile page; Organization logo unified (PNG); breadcrumb: removed non-existent /business/sectors level; domain www.immtell.com -> immtell.com (canonical) |
| healthcare | Gavin jobTitle unified; Gavin url -> profile page; Organization logo unified (PNG); breadcrumb: removed non-existent /business/sectors level; domain www.immtell.com -> immtell.com (canonical) |
| fintech | Gavin jobTitle unified; Gavin url -> profile page; Organization logo unified (PNG); breadcrumb: removed non-existent /business/sectors level; domain www.immtell.com -> immtell.com (canonical) |
| financial-services | Gavin jobTitle unified; Gavin url -> profile page; Organization logo unified (PNG); breadcrumb: removed non-existent /business/sectors level; domain www.immtell.com -> immtell.com (canonical) |
| film-entertainment | Gavin jobTitle unified; Gavin url -> profile page; Organization logo unified (PNG); breadcrumb: removed non-existent /business/sectors level; domain www.immtell.com -> immtell.com (canonical) |
| energy | Gavin jobTitle unified; Gavin url -> profile page; Organization logo unified (PNG); breadcrumb: removed non-existent /business/sectors level; domain www.immtell.com -> immtell.com (canonical) |
| education | Gavin jobTitle unified; Gavin url -> profile page; Organization logo unified (PNG); breadcrumb: removed non-existent /business/sectors level; domain www.immtell.com -> immtell.com (canonical) |
| defence | Gavin jobTitle unified; Gavin url -> profile page; Organization logo unified (PNG); breadcrumb: removed non-existent /business/sectors level; domain www.immtell.com -> immtell.com (canonical) |

- **3-Pass QA:** Pass 1 ✅ · Pass 2 ✅ · Pass 3 ✅
- **Rich Result:** ✅ Breadcrumb; ❌ FAQ rich result (Aug 2023 থেকে শুধু govt/health site) — schema valid, AI/semantic এর জন্য রাখা হয়েছে
