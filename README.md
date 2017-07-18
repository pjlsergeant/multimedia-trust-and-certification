
This repository exists as a place for me to collect some thoughts I've been having recently on the certification of the authenticity of media.

If I don't know you and you have thoughts or comments, do feel free to open a pull request or issue or something. This vaguely feels like the start of a PhD proposal.

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

* As @Tynan points out, I forgot to mention that this sounds a lot like a good application for a distributed blockchain of some type. Ideally you should be able to download the whole ledger, but hosted versions are also available as per bitcoin.

* If you're signing something cryptographically, keys will get lost and stolen. Someway to revoke keys is needed, but also some kind of trust authority to say "this keypair really does belong to Library of Congress". To what degree could current TLS keypairs be re-used at least initially?

* That a [given image on the NYtimes website](https://static01.nyt.com/images/2017/07/13/sports/00mountain2/00mountain2-superJumbo.jpg) is hosted with an EV certificate already suggests a fair amount of trust in the image, albeit without any embedded meta-data or caption. This could be a good bootstrapping method, althought the lack of captioning is already problematic. Consider [this well-known doctored image](https://static01.nyt.com/images/2008/07/10/world/ledemissiles1.jpg) ([see this article](https://thelede.blogs.nytimes.com/2008/07/10/in-an-iranian-image-a-missile-too-many/)). That it's served by the NYTimes webservers currently only says it's newsworthy, not that it's an authentic depiction of events.

* @RobP points out that this is distinct from copyright; copyright assigns ownership and credit. If a newsorg sends you out to take a photo, you certify your photo AND the newsorg certifies the photo AND perhaps the newsorg's ownership trust signs it, and so on. News organizations become not just a general record of events, they become ceritifiers of the authenticity of an event, which gives them power

* Does it cost anything to add to the chain? How does that work? Who pays? What motivates them to pay? What's the return on investment?

* Wikisource / Wikimedia Commons maintains (currently) pretty credible provenance and authenticity data for a lot of assets. 

## @devulrandom speaks:

> Especially when it comes to video where by necessity it’s chopped/cropped/etc and thus it does legitimately change due to various visual & audio treatments, even something as simple as volume leveling.

> - Keyframe signing for video?

> - Chain of trust - Does the editing/raw-importing software from the individual photog/cameraguy sign it, and it’s then endorsed up the chain of trust in the organization as it moves around? e.g should organizations be saying “we” produced this, don’t worry about how, or is it John Smith, personally reputable photographer, says he took this photo, and his parent org also certifies it, but he’s putting his personal reputation on the line as well as the org. Thinking about situations where state security services may direct an organization to produce certain media and certify it as genuine

> - Reputational insight - does each piece of work stand on its own, or is there a trust metric derived from how often assets are used/verified by others? (i.e a bastardization of pagerank)

> - Cross-certification. If NYT takes a video of a building being bombed, and CNN also takes a video independently, do their cameramen certify each others distinct copies, sort of like witnesses who are testifying the content is correct.

> I realize I’ve veered a bit here into authenticity vs provenance, but saying something is “definitely from CNN” by itself isn’t enough, there needs to be a way to say it’s “definitely from CNN, and this 4 second clip of trump punching a baby is certified digitally as true by the cameraman who shot it, the boom guy who got the audio, the runner on site, and the visual effects person who took the original and performed the standard CNN color adjustment/crop/stabilization treatments on it”

## On Wikileaks images, for example, via perigirin

> 22:06 <•perigrin> One other issue that I see that hasn't been mentioned is the need to verify provenance but maintain anonymity

> 22:07 <•perigrin> "this picture is accurate but telling you I took it will cause me to go to jail|the gallows"

> 22:12 <•pete> I think that has its place but is not directly the problem this is trying to solve

> 22:12 <•pete> What if WikiLeaks signs it?

> 22:12 <•pete> You're not trying to show ownership

> 22:12 <•pete> You're asking several people to show trust

> 22:13 <•pete> Anonymous signing is basically pointless as an anonymous signer has no trust in the system

> 22:13 <•perigrin> that's rather my point

> 22:14 <•perigrin> some of the most important pictures are the ones that won't be signed ... the videos that Chelsea Manning released

> 22:14 <•perigrin> for example.

> 22:14 <•pete> But that's good because we shouldn't trust random images that show up

> 22:14 <•pete> HOWEVER

> 22:14 <•pete> WikiLeaks saying "We think this is authentic" is huge

> 22:15 <•perigrin> I'm not so sure it is anymore but how is that any different than Wikileaks *just posting* that image?

> 22:16 <•pete> That's discussed -- images being served by an organisation under an EV cert already have some trust

> 22:16 <•pete> But the problem being solved here is:

> 22:16 <•pete> Someone on Facebook says "this image is in the 200gb trove of WikiLeaks images"

> 22:17 <•pete> And you saying "What's its certification ID?"

> 22:17 <•pete> And oh look, also signed by the Guardian and a bunch of other news media who received that particular image

> 22:17 <•pete> A jpeg suddenly has an evidence chain
