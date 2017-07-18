
This repository exists as a place for me to collect some thoughts I've been having recently on the certification of the authenticity of media.

# Abstract

Various neural network technologies appear to be able to already generate convincing images, audio, and video of events that didn't happen, or happened differently to their portrayl in that video. Soon that generated multimedia will become very difficult to distinguish from authentic recordings.

This changes the mental paradigm that possession of multimedia purporting to show an event means that even most likely occured -- seeing will no longer be believing.

Generation of fake multimedia already exists today, but its generation involves a lot of time and work, so authentic media occurs far more regularly than faked media. The work needed to generate this media is likely to diminish significantly in the next few years.

Some form of certifying and then authenticating multimedia would be helpful.

A photographer can already create a digital signature for their work using public/private keys. However, there's no central repository for these signatures, and no infrastructure for verifying them. Further, the general public is unlikely to recognize the names of individual photographers -- it would be useful to have a web of trust where provenance of media can be recorded, and where institutional certifiers of multimedia can also signal their trust in the multimedia. If a newspaper publishes an image, or a speech, they're (usually) signalling that they believe it to be authentic. This information may well be useful to a consumer of the media trying to find out more about it.

[Obama lip-sync video from SIGRAPH](https://www.youtube.com/watch?v=9Yq67CjDqvw)

# ... and the rest

Follows a brain dump that will hopefully coalesce into something more substantial with time...

* Media will need a description of the media. The NYT publishing a photo of missiles that they believe has been doctored will want to authenticate not that the image is a true depiction of what happened, but that it's an image they've received from a state news source

* Cryptographically signing media will work reasonably well for small media, say photos, but for larger items - an hour-long video of a speech - some kind of fingerprinting may be needed. This doesn't feel like it should form part of any specification, it feels like the system should be flexible to allow the certifier to choose the form of the certification. Should a certification of an image work for the same image with a slightly different colour cast? Perhaps, perhaps not

* It would be useful for this to be decentralized

* Much as papers can be cited, it'd be useful to have an alphanumeric ID to use as the certification handle for some media; when presented with multimedia, it'd be useful to ask for an ID that the certification process has created

* It'd be useful to have a mechanism whereby derivative portions of media can be certified deterministically -- eg: if you have the certification id for an image, it should be easy for a non-trusted user to generate an id that still works for 30 specific seconds of that media

* As @Tynan points out, I forgot to mention that this sounds a lot like a good application for a distributed blockchain of some type

* If you're signing something cryptographically, keys will get lost and stolen. Someway to revoke keys is needed, but also some kind of trust authority to say "this keypair really does belong to Library of Congress"

