# Peerpad Tech Deep Dive Sep 14

**Participants:**

- David Dias (@diasdavid)
- Pedro Teixeira (@pgte)

## Agenda:

- Identify what points of coordination (the interfaces)
- Go through features and requirements

## Notes:

### Identify what points of coordination (the interfaces)

We both agreed that are three major points of documents that need to exist in order for us to coordinate amongst ourselves and enable others to join and contribute to the project when it is necessary. These points are:

- The tech stack - A prescriptive list of what to use
- The API - What separates the front-end from the pseudo back-end (peer-end?)
- Requirements list that trickle into how the architecture is built

##### The tech stack

- Technologies
  - React
  - Webpack
  - JEST for testing
  - {editing library} - Still to be decided upon research is concluded
- Principles
  - Every call must have tests
  - Every code change should be done through PR + CR, reviewed by at least one other person
  - Code Coverage should always go up or maintain per PR
  - Tests need to run in simulated envinronment

##### The API

peerpad "core" should have its interface defined and reviewed asap (README driven development style). It should contemplate the needs for achieve the requirements defined.

##### Requirements

We understand clearly that peerpad requirements are:

- Guarantees non repudation
- Enables users to see history
- Private
- Snapshots of the pad can be published and viewed throught hthe IPFS network
- Peerpad must resist netsplits
- Authentication is independent of IPFS
- Permissions and ACL
  - WOT
  - Revocation
  - MegaOLM

We need a document that goes through each requirement and explains the considerations, constraints and proposes a way to implement.


```
Example - Non Repudiaton:

- Non Repudiation
  - per node Id
    - history should show which node Ids contributed with changes
  - per user Id -> depends uPort integration <-

not use -> conn.getPeerInfo

instead use -> peerpad.keys.add(ipfs.key.getPriv) <- default: peerId
to enable -> peerpad.keys.add(otherSystem.) <- 
```

### Todo

- [ ] Document every API call (@pgte)
- [ ] Improve the architecture doc to answer all the requirements generated questions (@pgte)
- [ ] Review both docs ^^ (@diasdavid)
- [ ] Plan for Security Audit (@diasdavid)

### Decisions that need to be made#

- Native representation Rich text vs Markdown vs Code
  - all of them. must have a codec to indentify and/or support in the future
- Select the editor
  - Pedro is doing the review on all of them

Other to ask later:
- Can we use datastore for pubsub-room now?
