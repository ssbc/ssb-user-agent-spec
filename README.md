:warning: **Status: gathering requirements** :warning

---

# ssb-user-agent-spec
_working title_

## Problem

We want to coordinate with another peer.
To do this we may need to know if they support some particular features.


## User Journeys

A collection of stories about how "user-agent" info would work in real situtations.

We can use these to more quickly surface the nature of the problem, and also as tests to have our potential solutions have to pass.

1. Encryption compatability:
    - I go to invite Mike to join my group. My app alerts me Mike doesn't support private groups yet (coordination failure avoided)
2. Deprecating support:
    - As an app developer I want to deprecate a feature. Published user-agent details help me make a more informed decision (especially if combined with opt-in analytics on user-agent details).
3. Meta-feed replication:
    - My app finds another peer, and I want to know if they support reading `contact` messages from a dedicated sub-feed. If they don't I may decide to publish duplicate `contact` messages to my legacy main feed

---

## Possible solutions

1. peers publish messages which describe what they support


## Principles

1. Simple to implement in multiple languages
2. Share as little info as possible


## Questions

1. what info do these messages need to carry?
    - a) can we make it self-describing enough that we don't need a spec per feature?
2. how do we support announcing "I'm dropping support for this feature"
3. meta feeds?
    - a) is there one user-agent description pre meta-feed tree, or is it defined on application sub-feeds, or both?
    - b) if we have one for all sub-feeds, how do we signal "time"
        - _e.g. I remove support for X ... you have some of my feeds, but maybe not all of them yet, do yo uneed to know where support lines up with different feeds?_
4. how can we make this very simple to tap into, but very strict?
    - a) JSON-schema?
    - b) clearly specified "reduce" method
        - _ssb-crut makes this VERY concrete, but might be hard for others to implement_
5. privacy
    - a) are there any risks to consider about declaring you support some feature?
        - we should aim for the minimal required info sharing
    - b) do we want to support "private user-agent messages"?
6. what could different levels of this spec look like?
    - could it be broken into simple basic features, and then more advanced features?
7. how will applications use this info?
    - (see User Journeys)




