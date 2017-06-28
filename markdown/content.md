<!-- .slide: data-background="images/backgrounds/shutterstock_150137660.jpg" data-state="inverted" -->

# HTTP/2

Die Zukunft beginnt jetzt.

---
<!-- .slide: data-background="images/backgrounds/shutterstock_197424404.jpg" data-state="inverted" -->

Wir schreiben das Jahr...

<h1 class="fragment">1991</h1>
---
<!-- .slide: data-background="images/backgrounds/shutterstock_147916586.jpg" data-state="inverted" -->

# Ende der Sowjetunion
---
<!-- .slide: data-background="images/backgrounds/nevermind.jpg" data-state="inverted" -->

# Nirvana Nevermind
---
<!-- .slide: data-background="images/backgrounds/1280px-Tim_Berners-Lee_CP_2.jpg" data-state="inverted faded grayscaled" -->

und

# HTTP/0.9

findet seine erste Erwähnung
---
<!-- .slide: data-background="images/backgrounds/shutterstock_4021051.jpg" data-state="inverted faded" -->

# 1996

offiziell als HTTP/1.0 spezifiziert.
---
# HTTP/1.0

Je eine kurzlebige TCP-Verbindung pro HTTP-Abfrage/Antwort-Pärchen

![HTTP/1.0 TCP](images/HTTP-1.0-TCP.png)
---
# HTTP/1.0

Daten werden ASCII codiert übertragen

![HTTP-Request](images/HTTP-Request.png)
---
# HTTP/1.0
<!-- .slide: data-background="images/backgrounds/shutterstock_4021051.jpg" data-state="inverted faded" -->

Header sind beliebig erweiterbar und werden bei jeder Anfrage mitgeschickt

```
GET /fotostrecke/screenshots-spiegel-online-1996-bis-heute-fotostrecke-16056-3.html HTTP/1.1
Host: www.spiegel.de
Connection: keep-alive
Cache-Control: no-cache
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Pragma: no-cache
User-Agent: Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/35.0.1916.114 Safari/537.36
DNT: 1
Accept-Encoding: gzip,deflate,sdch
Accept-Language: de-DE,de;q=0.8,en-US;q=0.6,en;q=0.4,fr;q=0.2
Cookie: POPUPCHECK=1402636825271; JSESSIONID=FC8674D0216AB1B92E09619BCD8CC9C7; spVcData2=6-10%3B10-15; __utma=159392383.976977501.1321345516.1402553897.1402569936.627; __utmc=159392383; __utmz=159392383.1402553897.626.40.utmcsr=facebook.com|utmccn=(referral)|utmcmd=referral|utmcct=/; __utmv=159392383.|1=custID=f380b31359c26298908199a247d8a3f1=1; mx_nam_id=03de4a6b-b79e-4c74-81eb-7c4999e36205
 ```
---
<!-- .slide: data-background="images/backgrounds/shutterstock_4021051.jpg" data-state="inverted faded" -->

# ab 1997

wird HTTP/1.1 entwickelt. Es wird 1999 spezifiziert.
---
# HTTP/1.1

Spezifiziert persistente TCP-Verbindungen

![HTTP/1.1 TCP](images/HTTP-1.1-TCP.png)
---
# Persistente TCP-Verbindungen

...helfen, den Effekt von TCP Slow Start zu reduzieren

![TCP Slow Start](images/tcp_slow_start.png)

[Quelle](https://libosong.appspot.com/spdy/index.html#20)
---
# TCP Slow Start

![TCP Slow Start](images/slow_start_graph.png)

[Quelle](http://packetlife.net/blog/2011/jul/5/tcp-slow-start/)
---
# TCP Slow Start

![TCP Slow Start](images/tcp_slow_start_request.png)

[Quelle](https://libosong.appspot.com/spdy/index.html#21)
---
# HTTP/1.1

Um die Serverlast herunterzufahren wird die Anzahl erwünschter TCP-Verbindungen eingeschränkt:

> single-user client SHOULD NOT maintain more than 2 connections with any server or proxy.

In der Praxis halten die Browser 6 Verbindungen zu einem Host auf.

<p class="fragment">Stehen sie hinter einem Proxy <a href="https://www.stevesouders.com/blog/2008/03/20/roundup-on-parallel-connections/">sind es nur 2 - 4</a>.</p>
---
# HTTP/1.1

Spezifiziert außerdem Pipelining

![HTTP/1.1 TCP](images/HTTP-1.1-TCP-Pipelining.png)
---
# HTTP/1.1

Beim Pipelining kann ein Requests abgesetzt werden, noch BEVOR die Antwort des vorherigen da ist.

![HTTP/1.1 TCP](images/HTTP-1.1-TCP-Pipelining-2.png)
---
# HTTP/1.1

Durch Pipelining werden Latenzen zwischen den Requests einer TCP-Verbindung nicht mehr aufaddiert.

<p class="fragment">Pardon: WÜRDEN...</p>
---
<!-- .slide: data-background="images/reactions/tumblr_lbdnzkTGkq1qe0eclo1_r1_500.gif" data-state="inverted" -->

<br><br><br><br>
<br><br><br><br>
<br>
# Proxies sagen leider nein zu Pipelining.

<p class="fragment">Schade.</p>
---
# Pipelining Support

| System  |                                   |
|---------|-----------------------------------|
| IE      | NEIN                              |
| Chrome  | JA, aber abgeschaltet             |
| Firefox | JA, aber abgeschaltet             |
| Server  | JA                                |
| Proxies | NEIN                              |

[Quelle](https://libosong.appspot.com/spdy/index.html#17)
---
<!-- .slide: data-background="images/backgrounds/shutterstock_197553677.jpg" data-state="inverted" -->

# Währenddessen im Web...
---
<!-- .slide: data-background="images/backgrounds/website-1991.png" data-state="inverted" -->

# Webseite 1991
---
<!-- .slide: data-background="images/backgrounds/website-1991.png" data-state="inverted faded" -->

# 1 Request
---
<!-- .slide: data-background="images/reactions/tumblr_inline_my8bn7Af5g1raprkq.gif" data-state="inverted" -->

<br><br><br><br>
<br><br><br><br>
# Seite schnell, alles smooth, macht Spaß!
---
<!-- .slide: data-background="images/backgrounds/website-1996.png" data-state="inverted" -->

# Webseite 1996
---
<!-- .slide: data-background="images/backgrounds/website-1996.png" data-state="inverted faded" -->

# 7 Requests
---
<!-- .slide: data-background="images/reactions/tumblr_inline_my8bn7Af5g1raprkq.gif" data-state="inverted" -->

<br><br><br><br>
<br><br><br><br>
# Alles okay!
---
<!-- .slide: data-background="images/backgrounds/website-1998.png" data-state="inverted" -->

# Webseite 1998
---
<!-- .slide: data-background="images/backgrounds/website-1998.png" data-state="inverted faded" -->

# 85 Requests
---
<!-- .slide: data-background="images/reactions/r4lKi9i.gif" data-state="inverted" -->

<br><br><br><br>
<br><br><br><br>
# Ähm... 85 Requests?
---
<!-- .slide: data-background="images/backgrounds/website-2014.png" data-state="inverted" -->

# Webseite heute
---
<!-- .slide: data-background="images/backgrounds/website-2014.png" data-state="inverted faded" -->

# 172 Requests
<h1 class="fragment">(ohne Werbung)</h1>

---
<!-- .slide: data-background="images/reactions/OaR0Y38.gif" data-state="inverted" -->

<br><br><br><br>
<br><br><br><br>
# 172 Requests? WTF-Copter!
---
# 1995 - heute

![HTTP Archive Trends](images/HTTP-Archive-Trends-Total-Size.png)

HTTP Requests: von 3 auf 96
---
<!-- .slide: data-background="images/ecommerce-loadingtime.png" data-state="inverted" -->

<br><br><br><br><br>
<br><br><br><br><br>
<br><br><br><br>
[Quelle](http://blog.radware.com/applicationdelivery/applicationaccelerationoptimization/2014/04/report-state-of-the-union-for-ecommerce-web-performance-spring-2014/)
---
<!-- .slide: data-background="images/backgrounds/shutterstock_195671744.jpg" data-state="inverted" -->

# Breitband to the Rescue?
---
# Nope!

![Bandwidth Benefits](images/Bandwidth-Benefits.png)

[Quelle](https://docs.google.com/a/chromium.org/viewer?a=v&pid=sites&srcid=Y2hyb21pdW0ub3JnfGRldnxneDoxMzcyOWI1N2I4YzI3NzE2)
---

> An increase from 5Mbps to 10Mbps results in a disappointing 5% improvement in page load times.

[Google](https://docs.google.com/a/chromium.org/viewer?a=v&pid=sites&srcid=Y2hyb21pdW0ub3JnfGRldnxneDoxMzcyOWI1N2I4YzI3NzE2)

---

# Problem Nr. 1: Latenzen!

---

# Latenz durch Distanz

| innerhalb Deutschlands | < 50 ms       |
|------------------------|---------------|
| USA                    | 100–150 ms    |
| Fernost                | bis zu 300 ms |

---

# Latenz durch Technologie

| 100BaseT-Ethernet      | 1 ms        |
|------------------------|-------------|
| WLAN 802.11b           | 10 ms       |
| Kabel allgemein        | 10 ms       |
| DSL-6000 ohne Fastpath | 40 ms       |
| DSL-2000 ohne Fastpath | 55 ms       |
| ISDN                   | 200 ms      |
| UMTS                   | 300–400 ms  |
| GPRS                   | 700–1000 ms |

---

# Blockade durch serverseitige Verarbeitung

Zeitverlust abhängig von Servergeschwindigkeit

---

# Einwirkung von Latenzen: ...

---

<video data-autoplay class="stretch" loop src="images/Bandbreite%20low.mp4"></video>

---

| Abschnitt        | Zeitverlust |
|------------------|-------------|
| Entfernungslatenz | 90 ms       |
| Übertragungszeit | 135 ms      |
| Wartezeit Server | 45 ms       |
| **Gesamtzeit**   | **270 ms**  |

---

# Effekt von 3-facher Bandbreite: ...

---

<video data-autoplay class="stretch" loop src="images/Bandbreite%20low%20and%20high.mp4"></video>

---

| Abschnitt        | 1x Bandbreite | 3x Bandbreite |
|------------------|---------------|---------------|
| Entfernungslatenz | 90 ms         | 90 ms         |
| Übertragungszeit | <span style="color: #FF6666">135 ms</span>        | <span style="color: #66FF99">45 ms</span>         |
| Wartezeit Server | 45 ms         | 45 ms         |
| Gesamtzeit       | <span style="color: #FF6666">270 ms</span>        | <span style="color: #66FF99">180 ms</span>         |

---

| Abschnitt        | 1x Bandbreite | 10x Bandbreite |
|------------------|---------------|---------------|
| Entfernungslatenz | 90 ms         | 90 ms         |
| Übertragungszeit | <span style="color: #FF6666">135 ms</span>        | <span style="color: #66FF99">13 ms</span>         |
| Wartezeit Server | 45 ms         | 45 ms         |
| Gesamtzeit       | <span style="color: #FF6666">270 ms</span>        | <span style="color: #66FF99">148 ms</span>         |

---

<!-- .slide: data-background="images/backgrounds/shutterstock_4021051.jpg" data-state="inverted" -->

# Problem Nr. 2: HTTP/1.x!

---
# Geringe Parallelisierbarkeit

![Bandwidth Benefits](images/HTTP-Blockade.png)

Browser machen nur 6 parallele TCP-Verbindungen auf.

<p class="fragment">(bzw. 2 - 4 hinter einem Proxy)</p>

<p class="fragment">Das Ergebnis: Aufaddieren von Latenzen</p>
---
# Ungenutzte Wartezeiten

![Bandwidth Benefits](images/HTTP-Latencies.png)

Requests müssen in Reihe abgearbeitet werden.

Pipelining würde da helfen.

<p class="fragment">Auch ein Problem: Das &quot;First in Line Blocking&quot;<p>
---
# Kein Abbruchmechanismus

Sind alle TCP-Verbindungen mit Anfragen belegt, kann sich der Browser vorerst nicht mehr umentscheiden.

<p class="fragment">Blöd, wenn der Browser genau dann das `<script>`-Tag im Fuß der Seite findet.</p>
---
# Aufgeblasene Header

Das ständige Mitsenden der Header führt zu langsameren Anfragen.

<p class="fragment">Ein durchschnittlicher Header liegt bei 600 Bytes.</p>

<p class="fragment">Der SPON Header mit samt Cookie kommt z.B. auf knapp 1 KB.</p>

<p class="fragment">Übertragungszeit bei einem 1 MBit/s Upstream: 10 ms pro Request.</p>
---
<!-- .slide: data-background="images/reactions/tumblr_inline_mmrb6wlC0g1qz4rgp.gif" data-state="inverted" -->

<br><br><br><br>
<br><br><br><br>
# Was tun wir bisher dagegen?
---
<!-- .slide: data-background="images/backgrounds/shutterstock_4021051.jpg" data-state="inverted faded" -->

# Concatenieren

```js
grunt.initConfig({
  concat: {
    options: {
      separator: ';',
    },
    dist: {
      src: ['src/a.js', 'src/b.js', 'src/c.js'],
      dest: 'dist/scripts.js',
    },
  },
});
```
---
<!-- .slide: data-background="images/old_structure_resized.png" data-state="inverted faded" -->

# Bitmap-Spriting

```js
grunt.initConfig({
    sprite:{
      all: {
        src: 'path/to/your/sprites/*.png',
        destImg: 'destination/of/spritesheet.png',
        destCSS: 'destination/of/sprites.css'
      }
    }
  });
```
---
<!-- .slide: data-background="images/1351212646_ap_icons_white_social.png" data-state="inverted faded" -->

# SVG-Spriting

```html
<svg viewBox="0 0 100 100">
   <use xlink:href="defs.svg#icon-1"></use>
</svg>
```
---
<!-- .slide: data-background="images/icomoon.png" data-state="inverted faded" -->

# Icon Fonts verwenden
---
<!-- .slide: data-background="images/datauri.png" data-state="inverted" -->

# Ressourcen via Data-URIs inlinen
<br><br><br><br>
---
<!-- .slide: data-background="images/huey_pushed_vietnam.jpg" data-state="inverted faded" -->

# Nachteil:

Ändert sich ein Fragment aus diesen Datei-Paketen, muss alles neu übertragen werden.
---
<!-- .slide: data-background="images/backgrounds/shutterstock_201459827.png" data-state="inverted faded" -->

# Desweiteren: Ressourcen über mehrere Hosts verteilen

<p class="fragment">&quot;Domain Sharding&quot;</p>

<ul>
	<li class="fragment">Jeder Extra-Host ermöglicht 6 zusätzliche TCP-Verbindungen</li>
	<li class="fragment">Cookie-Header werden nur noch an den Haupt-Host gesendet</li>
</ul>
---
<!-- .slide: data-background="images/backgrounds/shutterstock_201459827.png" data-state="inverted faded" -->

# Nachteile:

Jeder zusätzliche Host muss per DNS-Abfrage aufgelöst werden.
<p class="fragment">Jeder zusätzliche Host muss durch die TCP Slow Start Phase.</p>
<p class="fragment">Ab 4 Hosts dreht sich der Vorteil ins Negative um.</p>
---
<!-- .slide: data-background="images/reactions/tumblr_inline_n1h1w9xP6K1raprkq.gif" data-state="inverted" -->

<br><br><br><br>
<br><br><br><br>
# Puh, was für ein Aufwand!
---
<!-- .slide: data-background="images/reactions/SJxHr.gif" data-state="inverted" -->

<br><br><br><br>
<br><br><br><br>
# Enter HTTP/2!
---
<!-- .slide: data-background="images/backgrounds/timeline.jpg" data-state="inverted" -->
<br><br>

# HTTP/2 &asymp; SPDY

<br><br><br><br>
<br><br><br><br>

(siehe auch: [Genesis](https://en.wikipedia.org/wiki/HTTP/2#Genesis_in_and_later_differences_from_SPDY))
---
# HTTP/2
<!-- .slide: data-background="images/backgrounds/1761049_o.gif" data-state="inverted" -->

Daten werden binär codiert übertragen.

<ul>
	<li class="fragment">Effizienter zu parsen</li>
	<li class="fragment">Kompakter</li>
	<li class="fragment">Weniger fehleranfällig</li>
</ul>
---
# HTTP/2
<!-- .slide: data-background="images/backgrounds/1761049_o.gif" data-state="inverted" -->

> textual protocols like HTTP/1.x [...] often have a number of affordances to “help” with things like whitespace handling, capitalisation, line endings, blank links and so on.

[Quelle](http://http2.github.io/faq/#why-is-http2-binary)
---
# HTTP/2

Headerdaten werden nur einmal zwischen den Parteien ausgetauscht. Sie gelten fortan für alle nachfolgenden Requests automatisch.

<p class="fragment">Wenn sich Header-Abschnitte später ändern, werden nur diese Teile neu übertragen (z.B. nach einem Login).</p>
---
# HTTP/2

Headerdaten werden komprimiert.

> Google observed an ~88% reduction in the size of request headers and an ~85% reduction in the size of response headers after enabling compression. This amounted to a saving of between 45 and 1142 ms in the overall page load time.

[Quelle](http://blog.teamtreehouse.com/making-the-web-faster-with-spdy)
---
# HTTP/2

[Tests der University of Delaware](http://www.eecis.udel.edu/~amer/PEL/poc/pdf/SPDY-Fan.pdf):

| Request headers | 1st         | 2nd        |
|-----------------|-------------|------------|
| HTTP Request    | 686.2       | 636.4      |
| SPDY Request    | 379.4 (55%) | 68.6 (10%) |

| Response headers | 1st         | 2nd        |
|------------------|-------------|------------|
| HTTP Response    | 444.6       | 418.7      |
| SPDY Response    | 202.0 (45%) | 69.2 (17%) |
---
<!-- .slide: data-background="images/backgrounds/shutterstock_200991887_B.jpg" data-state="inverted faded" -->

# HTTP/2

Es wird nur eine einzelne TCP-Verbindung zu jedem Host geöffnet.

<p class="fragment">Alle Übertragungsfragmente werden in diesen einen Datenstrom hineingewoben<span class="fragment"> (gemultiplexed)</span></p>

<p class="fragment">Es handelt sich also um ein automatisches Spriting/Concatenieren auf Protokollebene!</p>
---
<!-- .slide: data-background="images/HTTP-1.0-vs-SPDY.png" data-state="inverted" -->
<br><br><br><br><br><br><br><br><br><br><br><br><br><br>
[Quelle](http://de.slideshare.net/AndyDavies/are-todays-good-practices-tomorrows-performance-antipatterns-28286548#)
---
# Der Vergleich

<video data-autoplay class="stretch" loop src="images/mod_spdy%20World%20Flags%20Demo.mp4"></video>

---
<!-- .slide: data-background="images/backgrounds/shutterstock_199661090_b.jpg" data-state="inverted" -->

<br><br><br><br>

## Prioritized Streams

HTTP/2 kann das Mischverhältnis der in seinen Datenstrom gewobenen Daten zu jeder Zeit verändern und an neue Gegebenheiten anpassen.

<p class="fragment">Auch kann die Übertragung einer angefangenen Datei komplett gestoppt und verworfen werden.</p>
---
<!-- .slide: data-background="images/backgrounds/shutterstock_199661090_b.jpg" data-state="inverted" -->

<br><br><br><br>

## Prioritized Streams

Der Browser kann so Ressourcen mit verschiedenen Prios anfordern:

<ul>
	<li class="fragment">Hoch: Hauptdokument & Frames</li>
	<li class="fragment">Mittel: JavaScript, CSS und Fonts</li>
	<li class="fragment">Niedrig: `<link rel="subresource">`, `<video>`, `<audio>`, `<object>` und AJAX-Calls</li>
	<li class="fragment">Sehr niedrig: Bilder, Favicon</li>
</ul>
---
<!-- .slide: data-background="images/backgrounds/shutterstock_199661090_b.jpg" data-state="inverted" -->

<br><br><br><br>

## Prioritized Streams

Ebenso kann der Server Ressourcen, die er für relevant hält, initiativ durch die Leitung drücken.

<p class="fragment">Das nennt sich dann "Server Push".</p>
---
## Server Push

Von 640 Bildfragmenten werden zuerst die des Schriftzugs Übertragen:

<video data-autoplay class="stretch" loop src="images/server-push.mp4"></video>
<!-- <iframe width="420" height="315" src="//www.youtube.com/embed/4Ai_rrhM8gA" frameborder="0" allowfullscreen></iframe> -->
---
<!-- .slide: data-background="images/backgrounds/shutterstock_201625775_b.jpg" data-state="inverted faded" -->

# HTTP/2

ist bestandskompatibel und vollkommen transparent.

<p class="fragment">HTTP/2 wird grundsätzlich SSL-verschlüsselt verpackt, damit keine Übermittlungsstelle und auch kein Proxy etwas kaputt macht.</p>

<p class="fragment">(um zu vermeiden, was mit HTTP-Pipelining passiert ist)</p>
---
<!-- .slide: data-background="images/backgrounds/shutterstock_201625775_b.jpg" data-state="inverted faded" -->

# HTTP/2

Zudem wird die SSL-Handshake-Phase genutzt, um sich gegenseitig über HTTP/2-Fähigkeiten zu informieren.
---
Eine Aushandlung via unverschlüsseltem HTTP ist möglich:
```
GET /page HTTP/1.1
Host: server.example.com
Connection: Upgrade, HTTP2-Settings
Upgrade: HTTP/2.0
HTTP2-Settings: (SETTINGS payload in Base64)
```
Gegenstelle kann kein HTTP/2:
```
HTTP/1.1 200 OK 3
Content-length: 243
Content-type: text/html
(... HTTP 1.1 response ...)
```
Gegenstelle kann HTTP/2:
```
HTTP/1.1 101 Switching Protocols 4
Connection: Upgrade
Upgrade: HTTP/2.0
(... HTTP 2.0 response ...)
```
<p class="fragment">(Anwendungsszenario: Server-zu-Server-Kommunikation)</p>
---
<!-- .slide: data-background="images/backgrounds/shutterstock_334616300.jpg" data-state="inverted faded" -->

# Serverseitige Vorteile

> SPDY clients consume one Apache worker instead of six

[Quelle](http://www.neotys.com/blog/performance-of-spdy-enabled-web-servers/)
---
<!-- .slide: data-background="images/backgrounds/shutterstock_334616300.jpg" data-state="inverted faded" -->

# Benchmark

> Ramp-up from 1 to 1000 users for 20 minutes.<br>1 page call, wait for 5s, restart.

[Quelle](http://www.neotys.com/blog/performance-of-spdy-enabled-web-servers/)
---
<!-- .slide: data-state="smaller" -->

# Ergebnisse

|                                                         | HTTP                                     | HTTPS                                    |SPDY                                     |
|---------------------------------------------------------|------------------------------------------|------------------------------------------|-----------------------------------------|
| Max. pages/s                                            | 16.3 @ 120 users                         | 15.9 @ 120 users                         | 98 @ 777 users                          |
| Response @ 100 users                                    | 1.1s                                     | 1.3s                                     | 1.1s                                    |
| Response @ 120 users                                    | 1.4 s                                    | 1.5s                                     | 1.1s                                    |
| Response @ 200 users                                    | 7.1s                                     | 7.8s                                     | 1.1s                                    |
| Response @ 777 users                                    | 70.2s                                    | 72s                                      | 2.7s                                    |
| First error                                             | 405 Users                                | 225 Users                                | 884 Users                               |

---
# Speicherverbrauch

| System Memory | 01:00    | 02:00    | Diff = Consumed              |
|---------------|----------|----------|------------------------------|
| HTTP          | 3,357 MB | 3,416 MB | 59 MB                        |
| HTTPS         | 3,500 MB | 3,579 MB | 79 MB                        |
| SPDY          | 3,607 MB | 3,631 MB | 24 MB                        |

---
# CPU Idle-Time

![CPU Idle Times](images/spdy-linux-cpu-idle.png)

(weniger ist besser)

---
<!-- .slide: data-background="images/Caniuse-HTTP2.png" data-state="inverted" -->

# Browser-Support Weltweit: 
# 78.33%
---
<!-- .slide: data-background="images/Caniuse-HTTP2.png" data-state="inverted" -->

# Browser-Support Deutschland: 
# 91.24%
---
#  HTTP/2 Support Desktop

| ![Chrome](images/browserlogos/chrome.png) | ![Safari](images/browserlogos/safari.png) | ![Firefox](images/browserlogos/firefox.png) | ![IE](images/browserlogos/ie.png) | ![Edge](images/browserlogos/edge.png) |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| &#10004; | 9+* | &#10004; | 11** | &#10004;

\*= ab OSX 10.11+<br>
\**= auf Windows 10+, auf Windows 8 nur SPDY

[Can I Use](http://caniuse.com/#feat=http2)
---
# HTTP/2 Support Mobile

| ![Android](images/browserlogos/android.png) | ![Chrome](images/browserlogos/chrome.png) | ![Safari](images/browserlogos/ios.png) | ![Firefox](images/browserlogos/firefox.png) | ![IE](images/browserlogos/ie.png) | ![Edge](images/browserlogos/edge.png) |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| &#10008;* | &#10004; | 9,2+ | &#10004; | &#10008;** | &#10004; |

\*= Wird gerade durch Chrome (Views) ersetzt<br>
\**= IE 11 auf Windows Mobile 8.1 kann nur SPDY

[Can I Use](http://caniuse.com/#feat=http2)
---
# Serverseitige Unterstützung

* Apache HTTP Server 2.4.17+ (ansonsten: [mod_h2](https://github.com/icing/mod_h2))
* Apache Tomcat 8.5+
* NGINX 1.9.5+
* IIS auf Windows 10 und Windows Server 2016
* Node.js 5.0+
* Jetty 9.3+
* und noch viele mehr&hellip;

Siehe [HTTP/2 Implementations](https://github.com/http2/http2-spec/wiki/Implementations) und [Wikipedia](https://en.wikipedia.org/wiki/HTTP/2#Software_and_services_supporting_HTTP.2F2)
---
# Unterstützung seitens CDNs

* Akamai <b class="fragment">(mit Server Push!)</b>
* CloudFlare
* Amazon CloudFront
* Fastly <b class="fragment">(mit Server Push!)</b>
* und noch ein paar mehr.

[Wikipedia](https://en.wikipedia.org/wiki/HTTP/2#Software_and_services_supporting_HTTP.2F2)
---
<!-- .slide: data-background="images/backgrounds/5261568726_d51149d62c_b.jpg" data-state="inverted faded" -->

# Firmen und Webseiten, die HTTP/2 nutzen

* Google
* Yahoo
* Facebook
* Twitter
* WordPress.com
* Synology

---
<!-- .slide: data-background="images/reactions/tumblr_inline_mxzcnayKCb1raprkq.gif" data-state="inverted" -->

<br><br><br><br>
<br><br><br><br>
# Handlungsempfehlungen
---
<!-- .slide: data-background="images/backgrounds/shutterstock_156956813_b.jpg" data-state="inverted faded" -->

<br><br><br><br>
<br><br><br><br>
<br><br><br>
# Ab jetzt HTTP/2 nutzen!

<p class="fragment">(Notfalls via [zwischengeschaltetem HTTP/2-fähigem Load-Balancer](https://www.google.de/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=0ahUKEwih0sauv9rQAhUFEywKHYS3DTAQFggaMAA&url=https%3A%2F%2Fwww.safaribooksonline.com%2Flibrary%2Fview%2Fhigh-performance-browser%2F9781449344757%2Fch13.html&usg=AFQjCNGJiVCDdoF0iAC2ch9b66idBsmcuA&sig2=_nJIXeYIw0Xn2xmEnoSlpA&bvm=bv.139782543,d.bGg))
---
<!-- .slide: data-background="images/backgrounds/shutterstock_201459827.png" data-state="inverted faded" -->

# Domain-Sharding vermeiden!

Es bringt uns keinerlei Vorteile mehr.

<p class="fragment">(stattdessen erzeugt es nur überflüssige DNS-Lookups)</p>

<p class="fragment">Außerdem: Ein einzelner Host kann die Ressourcen-Priorisierung besser verwalten.</p>

<p class="fragment">[Den Einsatz von CDNs neu abwägen](https://thethemefoundry.com/blog/why-we-dont-use-a-cdn-spdy-ssl/).</p>
---
<!-- .slide: data-background="images/backgrounds/shutterstock_4021051.jpg" data-state="inverted faded" -->

# Spriting und Concatenieren absolut vermeiden!

<p class="fragment">Stattdessen: Zusehen, ob man seine Dateien nicht automatisiert noch kleiner bekommt!</p>

<p class="fragment">(verrückt, oder?)</p>

<p class="fragment">(Aber so kommen wir nah an das Konzept von Delta-Updates heran)</p>
---
# Server Push aktivieren

Server Push für alle kritischen Ressourcen konfigurieren!

---
# Server Push aktivieren

Inoffizieller Standard , solche Ressourcen für den Server zu kennzeichnen, läuft via Header-Directive:

```
X-Associated-Content: "/foo.css":1,"/bar.js":1,"/baz.js":1
```

(Prio 0 = Hoch, Prio 7 = Niedrig)
---
<!-- .slide: data-background="images/backgrounds/xp.jpg" data-state="inverted faded" -->

# Legacy Browser?

Was tun, wenn man gleichzeitig viele alte Clients bedienen muss?
---
# Apaches mod_pagespeed

```
# Disable concatenation for SPDY/HTTP 2.0 clients
<ModPagespeedIf spdy>
  ModPagespeedDisableFilters combine_css,combine_javascript
</ModPagespeedIf>

# Shard assets for HTTP 1.x clients only
<ModPagespeedIf !spdy>
  ModPagespeedShardDomain www.site.com s1.site.com,s2.site.com
</ModPagespeedIf>
```
---
<!-- .slide: data-background="images/reactions/tumblr_mnj888Jab71s6z99jo1_500.gif" data-state="inverted" -->

<br><br><br><br>
<br><br><br><br>
<br><br>
# Profit!
---
<!-- .slide: data-background="images/backgrounds/8207553734_1cacc702f3_o.jpg" data-state="inverted faded" -->

<br><br><br><br><br><br>
## Danke!

* Slides: [http://schepp.github.io/HTTP-2](http://schepp.github.io/HTTP-2)
* Twitter: [@derSchepp](https://twitter.com/derSchepp)
* Podcast: [Working Draft](http://workingdraft.de)

---
# Weiterführende Literatur

* [HTTP/2 Frequently Asked Questions](http://http2.github.io/faq/)
* [High Performance Networking](http://chimera.labs.oreilly.com/books/1230000000545/ch12.html#HTTP2_UPGRADE)
* [Making The Web Faster With SPDY](http://blog.teamtreehouse.com/making-the-web-faster-with-spdy)
* [SPDYCheck.org](http://spdycheck.org/)
* [Evaluating the Performance of SPDY-enabled Web Servers](http://www.neotys.com/blog/performance-of-spdy-enabled-web-servers/)
---
## Bildnachweise

<ul class="multicolumn">

<li>Golden abstract science fiction: Shutterstock - pixelparticle
<li>Sonnenuntergang: Shutterstock - Natalia Dobryanskaya
<li>Soviet: Shutterstock -  Triff
<li>Tim Berners Lee: Wikipedia
<li>Code Matrix: Shutterstock - Sebastian Kaulitzki
<li>Frau mit Laptop: Shutterstock - Voyagerix
<li>Cables: Shutterstock - Eugene Sergeev
<li>Deutschlandkarte: DeStatis, David Liuzzo
<li>Hubschrauber: usmilitaryhelicopters.org
<li>Cloud Computing Concept: Shutterstock - olegganko
<li>shiny space, futuristic wave: Shutterstock - majcot
<li>Prism: Shutterstock - mejnak
<li>Grass: Shutterstock - noppharat
<li>Engine start stop button: Shutterstock - Peter Gudella
<li>Planet Facebook or Planet Earth? - Paul Butler
<li>Walt Disney Concert Hall - Graham@Flickr
<li>Schnappschuss: Stefan Nitzsche
<li>Animierte GIFs: devopsreactions.tumblr.com & gifsoup.com

</ul>