## THE PAST, PRESENT & FUTURE OF LOCAL STORAGE FOR WEB APPLICATIONS

__DIVING IN:__

persistent local storage is one of the areas where native client applications have held an advantage over web applications. 

For native applications, the operating system typically provides an abstraction layer for storing and retrieving application-specific data like preferences or runtime state. 

These values may be stored in the registry, INI files, XML files, or some other place according to platform convention. 

If your native client application needs local storage beyond key/value pairs, you can embed your own database, invent your own file format, or any number of other solutions.

Historically, web applications have had none of these luxuries.

Cookies were invented early in the web’s history, and indeed they can be used for persistent local storage of small amounts of data. 

But they have three potentially dealbreaking downsides:

* Cookies are included with every HTTP request, thereby slowing down your web application by needlessly transmitting the same data over and over
* Cookies are included with every HTTP request, thereby sending data unencrypted over the internet (unless your entire web application is served over SSL)
* Cookies are limited to about 4 KB of data — enough to slow down your application (see above), but not enough to be terribly useful 

What we really want is

* a lot of storage space
* on the client
* that persists beyond a page refresh
* and isn’t transmitted to the server


Before HTML5, all attempts to achieve this were ultimately unsatisfactory in different ways.


__A BRIEF HISTORY OF LOCAL STORAGE HACKS BEFORE HTML5__

In the beginning, there was only Internet Explorer. 
Or at least, that’s what Microsoft wanted the world to think. 
To that end, as part of the [ First Great Browser Wars](https://en.wikipedia.org/wiki/Browser_wars#The_first_browser_war) Microsoft invented a great many things and included them in their browser-to-end-all-browser-wars, Internet Explorer.

 One of these things was called [ userData](https://docs.microsohttps://docs.microsoft.com/en-us/previous-versions//ms531424(v=vs.85)?redirectedfrom=MSDN).

__INTRODUCING HTML5 STORAGE__

What I will refer to as “HTML5 Storage” is a specification named [Web Storage](https://html.spec.whatwg.org/multipage/webstorage.html), which was at one time part of the HTML5 specification proper, but was split out into its own specification for uninteresting political reasons. 

Certain browser vendors also refer to it as “Local Storage” or “DOM Storage.” The naming situation is made even more complicated by some related, similarly-named, emerging standards that I’ll discuss later in this chapter.


__USING HTML5 STORAGE__

HTML5 Storage is based on named key/value pairs. 

You store data based on a named key, then you can retrieve that data with the same key. 

The named key is a string. The data can be any type supported by JavaScript, including strings, Booleans, integers, or floats. However, the data is actually stored as a string. 

If you are storing and retrieving anything other than strings, you will need to use functions like parseInt() or parseFloat() to coerce your retrieved data into the expected JavaScript datatype.

interface Storage {
  getter any getItem(in DOMString key);
  setter creator void setItem(in DOMString key, in any data);
};

Calling setItem() with a named key that already exists will silently overwrite the previous value. Calling getItem() with a non-existent key will return null rather than throw an exception.

__TRACKING CHANGES TO THE HTML5 STORAGE AREA__

If you want to keep track programmatically of when the storage area changes, you can trap the storage event. 

The storage event is fired on the window object whenever setItem(), removeItem(), or clear() is called and actually changes something.
 
For example, if you set an item to its existing value or call clear() when there are no named keys, the storage event will not fire, because nothing actually changed in the storage area.

__STORAGEEVENT OBJECT__


|PROPERTY|TYPE|DESCRIPTION|
|------|-------|----|
|key|string|the named key that was added, removed, or modified|
|oldValue|any|the previous value (now overwritten), or null if a new item was added|
|newValue|any|the new value, or null if an item was removed|
|url|string|the page which called a method that triggered this change|

__HTML5 STORAGE IN ACTION__

function saveGameState()


 {
    if (!supportsLocalStorage()) { return false; }
    localStorage[" halma.game.in.progress"] = gGameInProgress;
    for (var i = 0; i < kNumPieces; i++) {
	localStorage[" halma.piece." + i + ".row"] = gPieces[i].row;
	localStorage[" halma.piece." + i + ".column"] = gPieces[i].column;
    }
    localStorage[" halma.selectedpiece"] = gSelectedPieceIndex;
    localStorage[" halma.selectedpiecehasmoved"] = gSelectedPieceHasMoved;
    localStorage[" halma.movecount"] = gMoveCount;
    return true;
}



As you can see, it uses the localStorage object to save whether there is a game in progress (gGameInProgress, a Boolean).

If so, it iterates through the pieces (gPieces, a JavaScript Array) and saves the row and column number of each piece. 

Then it saves some additional game state, including which piece is selected (gSelectedPieceIndex, an integer), whether the piece is in the middle of a potentially long series of hops (gSelectedPieceHasMoved, a Boolean), and the total number of moves made so far (gMoveCount, an integer).
