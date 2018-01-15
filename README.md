# polyglot-service
A micro service for small natural language processing, powered by Polyglot.

# About Polyglot
- https://github.com/aboSamoor/polyglot
- http://polyglot.readthedocs.io/

# Launch example

    #!/bin/sh
    docker run --rm -d -p 34567:80 gaving/polyglot-service

# Services Available
## Detect Language
After launching, try this requests:

```
curl -XPOST http://localhost:34567/detect -H "Content-Type: application/json" \ 
-d '{"text":"Trump lashed out at his former rival on Saturday in New York,
calling Clinton the worst (and biggest) loser of all time, after the
ex-Democratic Party nominee made pointed criticisms in a series of interviews
about Trumps political and moral legitimacy."}'
```

### Detect Language Responses
The responses will be JSON, featuring HTML-oriented "locale", confidence level,
and the count of "read_bytes":

```json
    {
      "locale": "en",
      "confidence": 99,
      "read_bytes": 1114,
      "entities": [
        {
          "tag": "I-PER",
          "entity": [
            "Trump"
          ]
        },
        {
          "tag": "I-LOC",
          "entity": [
            "New",
            "York"
          ]
        },
        {
          "tag": "I-PER",
          "entity": [
            "Clinton"
          ]
        },
        {
          "tag": "I-ORG",
          "entity": [
            "Democratic",
            "Party"
          ]
        }
      ]
    }
```

# Copyright & License
Copyright (C) 2017  Turbulent Media inc.

GPLv3 - See LICENSE file
