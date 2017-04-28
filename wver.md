# wver

The main engine for rev.

![](/assets/Screen Shot 2017-04-28 at 3.19.02 AM.png)

### Components

* wver is comprised of two main components:
  * Feedback
  * Document Viewer

#### DocumentViewer

The document viewer is powered by the awesome [CodeMirror](https://codemirror.net) and provides access to various files via the nav bar and also to diffs \(when using vcs\) via the diff button \(-&gt; &lt;-\)

#### Feedback

Feedback comprises an on-demand chat system that links to the DocumentViewer component and provides the following :

* Realtime chat
* Color based status system
  * Red = Rejected
  * Blue = Reply
  * Yellow = Regular
  * Green = Accepted
* Emoji!
* Line references, get lines to highlight when they're referenced using the `[:num]` syntax in your messages
* Mentions
* In-line replies

### UI Playground

Checkout all of the various react components used with wver on our storybook -&gt; [here](https://rev.vaemoi.co/storybook)

### Routing

Routing is just a map of our applications state, linking different "locations" with the "screens" that display components for carrying out the desired actions or displaying the proper data.

![](/assets/junctions.jpg)

