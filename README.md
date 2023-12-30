# mCompose
## about mCompose
**mCompose** is an ongoing (just for fun) project to develop an alternative set of user-defined key sequences to be used with [WinCompose](https://github.com/samhocevar/wincompose/) (an application for using a compose key in Windows) in place of the original default set of sequences.

At the moment, the defined sequences use these keys.

- the basic latin alphabet a–z, A–Z
- numbers 0–9
- symbols on the number row !@#$%^&\*()-=\_+
- other basic symbols []{}\\|;:'",./<>?
- space
- arrow keys ↑↓←→

That is, keyboards at the 75% and above size, using the basic English keyboard layout should work fine with mCompose's sequences.

As this is an ongoing project, there will be breaking changes.

### How to use compose sequences in this repo
Some of mCompose's sequences conflict with WinCompose's default ones, so it is recommended you disable WinCompose's default sequences when using mCompose.

1. **Completely disable WinCompose's default sequences**
	1. Right click the WinCompose icon in systray > select <kbd class="gui">Options...</kbd>
	2. In the <kbd class="gui">Composing</kbd> tab, under <samp class="gui">Sequences</samp>, deselect all checkboxes. (That is, disable sequences from Xorg, XCompose, or WinCompose emoji sequences.)
2. **Update WinCompose's <code class="path">.XCompose</code> file**
	1. Right click the WinCompose icon in systray > select <kbd class="gui">Show Sequences...</kbd>
	2. Under <samp class="gui">User-defined sequences</samp> (bottom-left) click <kbd class="gui">Edit</kbd>. This will open a file with the name <code class="path">.XCompose</code>
	3. Overwrite the whole content of said <code class="path">.XCompose</code> file with the content of this repo's <code class="path">.XCompose</code> file.
	4. Load the new sequences into WinCompose by going back to WinCompose's Show Sequences window, then under <samp class="gui">User-defined sequences</samp> click <kbd class="gui">Reload</kbd>.
3. You can now use the sequences defined in this repo's <code class="path">.XCompose</code> file.

## A short summary of mCompose's sequences
In this README file, the symbol ⎄ denotes the compose key.

There are mainly 4 types of compose sequences in mCompose:

1. Most are in the form <kbd>⎄<var>[prefix]<var><var>[base]<var></kbd>
2. Ligatures and digraphs are in the form <kbd>⎄<var>[char_1]<var><var>[char_2]<var></kbd>
3. Ungrouped characters are given ad hoc sequences
4. A few other sequences are defined for easier access ("shortcut sequences")

### prefix
Prefixes are defined for each group of characters sharing some common feature.

For example, `ĀāƂƃƋƌĒēḠḡĪīꝈꝉŌōŪūȲȳ` all have "high bars", and for every character in this group, the common prefix `-` is defined. That is, every character's sequence is of the form <kbd>⎄-<var>[base]<var></kbd>, for example <kbd>⎄-G</kbd>→`Ḡ`

Prefixes of difference groups may coincide, but the complete sequences never collide with each other.

### complex compose sequences
The <kbd><var>[base]<var></kbd>, <kbd><var>[char_1]<var></kbd>, <kbd><var>[char_2]<var></kbd> part of compose sequences can be replaced by any compose sequence that composes to that character, creating a complex compose sequence.

For example,

- the following is defined: <kbd>⎄ae</kbd>→`æ`
- the following is defined: <kbd>⎄-æ</kbd>→`ǣ`
- hence the following is also defined: <kbd>⎄-⎄ae</kbd>→`ǣ`

Complex compose sequences offers a systematic way to create more complex characters like ǣ with the basic English keyboard layout via composable subparts, while also offering a shorter sequence for users that can type æ without composing.

### shortcut sequences
Some characters by their forms hint at a more ad hoc but intuitive sequence than the systematic one. So we also include those intuitive sequnces in mCompose.

For example, `ť` is actually a [small T with a caron](https://en.wikipedia.org/wiki/Ť) but looks more like a small T with an apostrophe, so we also include the sequence <kbd>t'</kbd>→`ť` as a "shortcut sequence".

## sequences (prefix-base form)
### simple prefixes

|group|char(s)|prefix|
|:-:|-|:-:|
|acute|Áá, Ćć, Éé, Ǵǵ, Íí, Ḱḱ, Ĺĺ, Ḿḿ, Ńń, Óó, Ṕṕ, Ŕŕ, Śś, Úú, Ẃẃ, Ýý, Źź|<kbd>'</kbd>|
|acute (double)|Őő, Űű|<kbd>''</kbd>|
|breve|Ăă, Ĕĕ, Ğğ, Ĭĭ, Ŏŏ, Ŭŭ|<kbd>u</kbd>|
|breve below|Ḫḫ|<kbd>vv</kbd>|
|breve inverted|Ȃȃ, Ȇȇ, Ȋȋ, Ȏȏ, Ȓȓ, Ȗȗ|<kbd>]</kbd>|
|caron|Ǎǎ, Čč, Ď*ď*, Ěě, Ǧǧ, Ȟȟ, Ǐǐ, ǰ, Ǩǩ, *Ľľ*, Ňň, Ǒǒ, Řř, Šš, Ť*ť*, Ǔǔ, Žž|<kbd>v</kbd>|
|cedilla|Çç, *Ḑḑ*, Ȩȩ, *Ģģ*, Ḩḩ, *Ķķ*, *Ļļ*, *Ņņ*, *Ŗŗ*, Şş, Ţţ|<kbd>,</kbd>|
|circumflex|Ââ, Ĉĉ, Êê, Ĝĝ, Ĥĥ, Îî, Ĵĵ, Ôô, Ŝŝ, Ûû, Ŵŵ, Ŷŷ, Ẑẑ|<kbd>w</kbd>|
|circumflex below|Ḓḓ, Ḙḙ, Ḽḽ, Ṋṋ, Ṱṱ, Ṷṷ|<kbd>vv</kbd>|
|comma below|Șș, Țț|<kbd>,,</kbd>|
|descender|Ⱨⱨ, Ⱪⱪ, Ꞑꞑ, Ⱬⱬ|<kbd>,,</kbd>|
|diaeresis|Ää, Ëë, Ḧḧ, Ïï, Öö, ẗ, Üü, Ẅẅ, Ẍẍ, Ÿÿ|<kbd>;</kbd>|
|diaeresis below|Ṳṳ|<kbd>;;</kbd>|
|dot above|Ȧȧ, Ḃḃ, Ċċ, Ḋḋ, Ėė, Ḟḟ, Ġġ, Ḣḣ, İ, Ṁṁ, Ṅṅ, Ȯȯ, Ṗṗ, Ṙṙ, Ṡṡ, Ṫṫ, Ẇẇ, Ẋẋ, Ẏẏ, Żż|<kbd>.</kbd>|
|dot below|Ạạ, Ḅḅ, Ḍḍ, Ẹẹ, Ḥḥ, Ịị, Ḳḳ, Ḷḷ, Ṃṃ, Ṇṇ, Ọọ, Ṛṛ, Ṣṣ, Ṭṭ, Ụụ, Ṿṿ, Ẉẉ, Ỵỵ, Ẓẓ|<kbd>..</kbd>|
|dot above and below|Ṩṩ|<kbd>.,</kbd>|
|glottal|Ꞻꞻ, Ꞽꞽ, Ꞿꞿ|<kbd>)</kbd>|
|grave|Àà, Èè, Ìì, Ǹǹ, Òò, Ùù, Ẁẁ, Ỳỳ|<kbd>`</kbd>|
|grave (double)|Ȁȁ, Ȅȅ, Ȉȉ, Ȍȍ, Ȑȑ, Ȕȕ|<kbd>``</kbd>|
|hook above|Ảả, Ẻẻ, Ỉỉ, Ỏỏ, Ủủ, Ỷỷ|<kbd>3</kbd>, <kbd>?</kbd>|
|hook (palatal)|ᶀ, Ꞔꞔ, ᶁ, ᶂ, ᶃ, ꞕ, ᶄ, ᶅ, ᶆ, ᶇ, ᶈ, ᶉ, ᶊ, ƫ, ᶌ, ᶍ, Ᶎᶎ|<kbd>j</kbd>|
|hook (retroflex)|ᶏ, 𝼝, Ɖɖ, ᶒ, ᶖ, ɭ, ɳ, 𝼛, Ɋɋ, Ɽɽ, Ʂʂ, Ʈʈ, ᶙ, ʐ|<kbd>r</kbd>|
|hook (to left)|Ƒƒ, Ɱɱ, Ɲɲ, Ʋʋ, Ȥȥ|<kbd>]</kbd>|
|hook (to right)|Ɓɓ, Ƈƈ, Ɗɗ, Ɠɠ, Ɦɦ, Ƙƙ, 𝼑, Ƥƥ, ʠ, ɾ, Ƭƭ, ⱱ, Ⱳⱳ, Ƴƴ|<kbd>[</kbd>|
|horn|Ơơ, Ưư|<kbd>j</kbd>|
|line high (macron)|Āā, Ƃƃ, Ƌƌ, Ēē, Ḡḡ, Īī, Ꝉꝉ, Ōō, Ūū, Ȳȳ|<kbd>-</kbd>|
|line low (macron below)|Ḇḇ, Ḏḏ, ẖ, Ḵḵ, Ḻḻ, Ṉṉ, Ꝑꝑ, Ṟṟ, Ṯṯ, Ẕẕ|<kbd>--</kbd>|
|line mid (stroke)|Ƀƀ, Ꞓꞓ, Đđ, ꬳ, Ꞙꞙ, Ǥǥ, Ħħ, Ɨɨ, Ɉɟ, Ꝁꝁ, Ƚƚ, Ꝋꝋ, Ᵽᵽ, Ɍɍ, Ꟊꟊ, Ŧŧ, Ʉʉ, Ɏɏ, Ƶƶ, ƻ|<kbd>9</kbd>|
|ogonek|Ąą, Ęę, Įį, Ǫǫ, Ųų|<kbd>c</kbd>|
|ring above|Åå, Ůů, ẘ, ẙ|<kbd>o</kbd>|
|ring below|Ḁḁ|<kbd>0</kbd>|
|slash|Ⱥⱥ, Ȼȼ, Ɇɇ, Ꞡꞡ, Łł, Ꞣꞣ, Ꞥꞥ, Øø, Ꞧꞧ, Ꞩꞩ, Ⱦⱦ, Ꞹꞹ, Ꝟꝟ|<kbd>/</kbd>|
|tilde|Ãã, Ẽẽ, Ĩĩ, Ññ, Õõ, Ũũ, Ṽṽ, Ỹỹ|<kbd>2</kbd>|
|tilde below|Ḛḛ, Ḭḭ, Ṵṵ|<kbd>22</kbd>|
|tilde middle|ᵬ, ᵭ, ᵮ, Ɫɫ, ᵯ, ᵰ, ᵱ, ᵲ, ᵴ, ᵵ, ᵶ|<kbd>29</kbd>|

### compound prefixes (above+below)

- When diacritics are stacked, we list the diacritics outwards from the base character outwards. First go up ↑ the top half, then down ↓ the bottom half. Then combine the prefixes of each diacritics in that order.
- "Dot below" in a compound prefix is abbreviated from `..` to just `.`
- "Grave" in a compound prefix can be changed from `` ` `` to `\`
	- on QWERTY, this gives a right hand key alternative for the prefix

|group|char(s)|prefix|
|:-:|-|:-:|
|acute + cedilla|Ḉḉ|<kbd>',</kbd>|
|acute + dot above|Ṥṥ|<kbd>'.</kbd>|
|breve + acute|Ắắ|<kbd>u'</kbd>|
|breve + cedilla|Ḝḝ|<kbd>u,</kbd>|
|breve + dot below|Ặặ|<kbd>u.</kbd>|
|breve + grave|Ằằ|<kbd>u`</kbd>, <kbd>u\\</kbd>|
|breve + hook above|Ẳẳ|<kbd>u3</kbd>, <kbd>u?</kbd>|
|breve + tilde|Ẵẵ|<kbd>u2</kbd>|
|caron + dot above|Ṧṧ|<kbd>v.</kbd>|
|circumflex + acute|Ấấ, Ếế, Ốố|<kbd>w'</kbd>|
|circumflex + dot below|Ậậ, Ệệ, Ộộ|<kbd>w.</kbd>|
|circumflex + grave|Ầầ, Ềề, Ồồ|<kbd>w\`</kbd>, <kbd>w\\</kbd>|
|circumflex + hook above|Ẩẩ, Ểể, Ổổ|<kbd>w3</kbd>, <kbd>w?</kbd>|
|circumflex + tilde|Ẫẫ, Ễễ, Ỗỗ|<kbd>w2</kbd>|
|diaeresis + acute|Ḯḯ, Ǘǘ|<kbd>;'</kbd>|
|diaeresis + caron|Ǚǚ|<kbd>;v</kbd>|
|diaeresis + grave|Ǜǜ|<kbd>;`</kbd>, <kbd>;\\</kbd>|
|diaeresis + macron|Ǟǟ, Ȫȫ, Ǖǖ|<kbd>;-</kbd>|
|dot above + macron|Ǡǡ, Ȱȱ|<kbd>.-</kbd>|
|horn + acute|Ớớ, Ứứ|<kbd>j'</kbd>|
|horn + dot below|Ợợ, Ựự|<kbd>j.</kbd>|
|horn + grave|Ờờ, Ừừ|<kbd>j\`</kbd>, <kbd>j\\</kbd>|
|horn + hook above|Ởở, Ửử|<kbd>j3</kbd>, <kbd>j?</kbd>|
|horn + tilde|Ỡỡ, Ữữ|<kbd>j2</kbd>|
|macron + acute|Ḗḗ, Ṓṓ|<kbd>-'</kbd>|
|macron + dot below|Ḹḹ, Ṝṝ|<kbd>-.</kbd>|
|macron + grave|Ḕḕ, Ṑṑ|<kbd>-`</kbd>, <kbd>-\\</kbd>|
|macron + diaeresis|Ṻṻ|<kbd>-;</kbd>|
|macron + ogonek|Ǭǭ|<kbd>-c</kbd>|
|ring above + acute|Ǻǻ|<kbd>o'</kbd>|
|tilde + acute|Ṍṍ, Ṹṹ|<kbd>2'</kbd>|
|tilde + diaeresis|Ṏṏ|<kbd>2;</kbd>|
|tilde + macron|Ȭȭ|<kbd>2-</kbd>|

### greek

- These are intended to be used as standalone letters (such as symbols in linguistics or mathematics). For inputting whole words and sentences in Greek, a full Greek keyboard layout is recommended.
- The prefixes for each mode of Greek letters are in the parentheses.
- Latin characters are mapped to Greek ones according to the [Greek keyboard layout](https://en.wikipedia.org/wiki/Keyboard_layout#Greek).

|base|detail|latinized (<kbd>G</kbd>)|greek (<kbd>g</kbd>)|
|:-:|:-:|:-:|:-:|
|Aa|alpha|Ɑɑ|Αα|
|Bb|beta|Ꞵꞵ|Ββ|
|Cc|psi||Ψψ|
|Dd|delta|ẟ|Δδ|
|Ee|epsilon|Ɛɛ|Εε|
|Ff|phi|ɸ|Φφ|
|Gg|gamma|Ɣɣ|Γγ|
|Hh|eta||Ηη|
|Ii|iota|Ɩɩ|Ιι|
|Jj|xi||Ξξ|
|Kk|kappa||Κκ|
|Ll|lambda||Λλ|
|Mm|mu||Μμ|
|Nn|nu||Νν|
|Oo|omicron||Οο|
|Pp|pi||Ππ|
|Rr|rho||Ρρ|
|Ss|sigma||Σσ|
|Tt|tau||Ττ|
|Uu|theta||Θθ|
|Vv|omega|Ꞷꞷ|Ωω|
|w|sigma (final)||ς|
|Xx|chi|Ꭓꭓ|Χχ|
|Yy|upsilon|Ʊʊ|Υυ|
|Zz|zeta||Ζζ|

### non-conventional prefixes

|group|char(s)|prefix|
|:-:|-|:-:|
|ff|ﬃ, ﬄ|<kbd>f.</kbd>|
|long|ꟾ, Ƞƞ, ɼ, ſ, ꭗ|<kbd>[SPACE]</kbd>|
|math blackboard bold|𝔸𝕒, 𝔹𝕓, ℂ𝕔, 𝔻𝕕, 𝔼𝕖, 𝔽𝕗, 𝔾𝕘, ℍ𝕙, 𝕀𝕚, 𝕁𝕛, 𝕂𝕜, 𝕃𝕝, 𝕄𝕞, ℕ𝕟, 𝕆𝕠, ℙ𝕡, ℚ𝕢, ℝ𝕣, 𝕊𝕤, 𝕋𝕥, 𝕌𝕦, 𝕍𝕧, 𝕎𝕨, 𝕏𝕩, 𝕐𝕪, ℤ𝕫, 𝟘, 𝟙, 𝟚, 𝟛, 𝟜, 𝟝, 𝟞, 𝟟, 𝟠, 𝟡|<kbd>B</kbd>|
|math fraktur|𝔄𝔞, 𝔅𝔟, ℭ𝔠, 𝔇𝔡, 𝔈𝔢, 𝔉𝔣, 𝔊𝔤, ℌ𝔥, ℑ𝔦, 𝔍𝔧, 𝔎𝔨, 𝔏𝔩, 𝔐𝔪 ,𝔑𝔫, 𝔒𝔬, 𝔓𝔭, 𝔔𝔮, ℜ𝔯, 𝔖𝔰, 𝔗𝔱, 𝔘𝔲, 𝔙𝔳, 𝔚𝔴, 𝔛𝔵, 𝔜𝔶, ℨ𝔷|<kbd>f-</kbd>|
|math fraktur bold|𝕬𝖆, 𝕭𝖇, 𝕮𝖈, 𝕯𝖉, 𝕰𝖊, 𝕱𝖋, 𝕲𝖌, 𝕳𝖍, 𝕴𝖎, 𝕵𝖏, 𝕶𝖐, 𝕷𝖑, 𝕸𝖒, 𝕹𝖓, 𝕺𝖔, 𝕻𝖕, 𝕼𝖖, 𝕽𝖗, 𝕾𝖘, 𝕿𝖙, 𝖀𝖚, 𝖁𝖛, 𝖂𝖜, 𝖃𝖝, 𝖄𝖞, 𝖅𝖟|<kbd>F</kbd>|
|math monospace|𝙰𝚊, 𝙱𝚋, 𝙲𝚌, 𝙳𝚍, 𝙴𝚎, 𝙵𝚏, 𝙶𝚐, 𝙷𝚑, 𝙸𝚒, 𝙹𝚓, 𝙺𝚔, 𝙻𝚕, 𝙼𝚖, 𝙽𝚗, 𝙾𝚘, 𝙿𝚙, 𝚀𝚚, 𝚁𝚛, 𝚂𝚜, 𝚃𝚝, 𝚄𝚞, 𝚅𝚟, 𝚆𝚠, 𝚇𝚡, 𝚈𝚢, 𝚉𝚣, 𝟶, 𝟷, 𝟸, 𝟹, 𝟺, 𝟻, 𝟼, 𝟽, 𝟾, 𝟿|<kbd>m</kbd>|
|math script|𝒜𝒶, ℬ𝒷, 𝒞𝒸, 𝒟𝒹, ℰℯ, ℱ𝒻, 𝒢ℊ, ℋ𝒽, ℐ𝒾, 𝒥𝒿, 𝒦𝓀, ℒ𝓁, ℳ𝓂, 𝒩𝓃, 𝒪ℴ, 𝒫𝓅, 𝒬𝓆, ℛ𝓇, 𝒮𝓈, 𝒯𝓉, 𝒰𝓊, 𝒱𝓋, 𝒲𝓌, 𝒳𝓍, 𝒴𝓎, 𝒵𝓏|<kbd>c-</kbd>|
|math script bold|𝓐𝓪, 𝓑𝓫, 𝓒𝓬, 𝓓𝓭, 𝓔𝓮, 𝓕𝓯, 𝓖𝓰, 𝓗𝓱, 𝓘𝓲, 𝓙𝓳, 𝓚𝓴, 𝓛𝓵, 𝓜𝓶, 𝓝𝓷, 𝓞𝓸, 𝓟𝓹, 𝓠𝓺, 𝓡𝓻, 𝓢𝓼, 𝓣𝓽, 𝓤𝓾, 𝓥𝓿, 𝓦𝔀, 𝓧𝔁, 𝓨𝔂, 𝓩𝔃|<kbd>C</kbd>|
|missing parts|Ⱶⱶ, ı, ȷ, Ɔɔ, Ꝛꝛ, ꭎ, ꭚ, ʔɁɂ|<kbd>0</kbd>|
|small caps|ᴀ, ʙ, ᴄ, ᴅ, ᴇ, ꜰ, ɢ, ʜ, Ɪɪ, ᴊ, ᴋ, ʟ, ᴍ, ɴ, ᴏ, ᴘ, ꞯ, Ʀʀ, ꜱ, ᴛ, ᴜ, ᴠ, ᴡ, ʏ, ᴢ|<kbd><span class="down">↓</span></kbd>|
|turned|Ɐɐ, Ǝǝ, Ⅎⅎ, ⅁ᵷ, Ɥɥ, ᴉ, Ʞʞ, Ꞁꞁ, Ɯɯ, ɹ, Ʇʇ, Ʌʌ, ʍ, ⅄ʎ|<kbd><span class="backspace">Backspace</span></kbd>|

## sequences (ligatures & digraphs)
In all the compose sequences indicated, the leading <kbd>⎄</kbd> is omitted.

|chars|details|sequence|reason|
|:-:|:-:|:-:|-|
|Ꜳ, ꜳ||<kbd>AA</kbd>, <kbd>aa</kbd>||
|Æ, æ|[AE](https://en.wikipedia.org/wiki/Æ)|<kbd>AE</kbd>, <kbd>ae</kbd>||
|Ꜵ, ꜵ||<kbd>AO</kbd>, <kbd>ao</kbd>||
|Ꜷ, ꜷ||<kbd>AU</kbd>, <kbd>au</kbd>||
|Ꜹ, ꜹ||<kbd>AV</kbd>, <kbd>av</kbd>||
|Ꜽ, ꜽ||<kbd>AY</kbd>, <kbd>ay</kbd>||
|ȸ|db|<kbd>db</kbd>||
|ʣ|dz (ligature)|<kbd>dz</kbd>||
|Ǳ, ǲ, ǳ|dz (digraph)|<kbd>D-Z</kbd>, <kbd>D-z</kbd>, <kbd>d-z</kbd>|to not collide with <kbd>dz</kbd>→`ǳ` (ligature)|
|🙲, 🙰||<kbd>Et</kbd>, <kbd>et</kbd>||
|ﬀ||<kbd>ff</kbd>||
|ﬁ||<kbd>fi</kbd>||
|ﬂ||<kbd>fl</kbd>||
|ʩ|feng (digraph)|<kbd>fn</kbd>||
|Ƕ, ƕ||<kbd>HV</kbd>, <kbd>hv</kbd>||
|ꭡ||<kbd>ie</kbd>||
|Ĳ, ĳ|ij (digraph)|<kbd>IJ</kbd>, <kbd>ij</kbd>||
|℔||<kbd>lb</kbd>||
|Ǉ, ǈ, ǉ|lj (digraph)|<kbd>LJ</kbd>, <kbd>Lj</kbd>, <kbd>lj</kbd>||
|Ỻ, ỻ||<kbd>lL</kbd>, <kbd>ll</kbd>||
|ʪ|ls (less)|<kbd>ls</kbd>||
|ʫ|lz|<kbd>lz</kbd>||
|Ǌ, ǋ, ǌ|nj (digraph)|<kbd>NJ</kbd>, <kbd>Nj</kbd>, <kbd>nj</kbd>||
|Œ, œ|[OE](https://en.wikipedia.org/wiki/Œ)|<kbd>OE</kbd>, <kbd>oe</kbd>||
|Ꝏ, ꝏ||<kbd>OO</kbd>, <kbd>oo</kbd>||
|Ȣ, ȣ|[OU](https://en.wikipedia.org/wiki/Ou_(ligature))|<kbd>OU</kbd>, <kbd>o-u</kbd>|to not collide with  <kbd>ou</kbd>→`ů`|
|ȹ|qp|<kbd>qp</kbd>||
|ﬆ||<kbd>st</kbd>||
|ʦ|ts (tess)|<kbd>ts</kbd>||
|ᵫ|ue|<kbd>u-e</kbd>|to not collide with  <kbd>ue</kbd>→`ĕ`|
|ꭐ|ui|<kbd>u-i</kbd>|to not collide with  <kbd>ui</kbd>→`ĭ`|
|ꭣ|uo|<kbd>u-o</kbd>|to not collide with  <kbd>uo</kbd>→`ŏ`|
|Ꝡ, ꝡ||<kbd>VY</kbd>, <kbd>vy</kbd>||

## sequences (ad hoc)
In all the compose sequences indicated, the leading <kbd>⎄</kbd> is omitted.

### latin

|chars|details|sequence|reason|
|:-:|:-:|:-:|-|
|Ðð|[Eth](https://en.wikipedia.org/wiki/Eth)|<kbd>DH</kbd>, <kbd>dh</kbd>|θ = `th` in IPA, so voiced ð = `dh`|
|ʤ|dezh ligature|<kbd>d3</kbd>|visual similarity to `d3`|
|Əə|[Schwa](https://en.wikipedia.org/wiki/Ə)|<kbd>EW</kbd>, <kbd>ew</kbd>|visual similarity to `e`; use `ew` instead of `ee`|
|Ꜧꜧ|[Heng](https://en.wikipedia.org/wiki/Heng_(letter))|<kbd>HN</kbd>, <kbd>hn</kbd>|from **h**e**n**g|
|ĸ|[Kra](https://en.wikipedia.org/wiki/Kra_(letter))|<kbd>kk</kbd>|visual similarity to `k`|
|ɮ|lezh ligature|<kbd>l3</kbd>|visual similarity to `l3`|
|Ŋŋ|[Eng](https://en.wikipedia.org/wiki/Eng_(letter))|<kbd>NG</kbd>, <kbd>ng</kbd>|`ng` in IPA|
|Ʃʃ|[Esh](https://en.wikipedia.org/wiki/Esh_(letter))|<kbd>SH</kbd>, <kbd>sh</kbd>|`sh` in IPA|
|ẞß|Eszett|<kbd>SS</kbd>, <kbd>ss</kbd>||
|Þþ|[Thorn](https://en.wikipedia.org/wiki/Thorn_(letter))|<kbd>TH</kbd>, <kbd>th</kbd>|`th` in Middle English|
|Ꜩ, ꜩ||<kbd>T3</kbd>, <kbd>t3</kbd>|visual similarity to `T3`, `t3`|
|ʨ|tc curl ligature|<kbd>t6</kbd>|visual similarity to `t6`|
|Ƿƿ|[Wynn](https://en.wikipedia.org/wiki/Wynn)|<kbd>WN</kbd>, <kbd>wn</kbd>|from **w**y**n**n|
|Ȝȝ|[Yogh](https://en.wikipedia.org/wiki/Yogh)|<kbd>Y3</kbd>, <kbd>y3</kbd>|from **y**ogh and visual similarity to `3`|
|Ʒʒ|[Ezh](https://en.wikipedia.org/wiki/Ezh)|<kbd>ZH</kbd>, <kbd>zh</kbd>|`zh` in IPA|

### punctuation

|chars|details|sequence|reason|
|:-:|:-:|:-:|-|
|·|[middle dot (interpunct)](https://en.wikipedia.org/wiki/Interpunct)|<kbd>.[SPACE]</kbd>|treat `.` as a "prefix" modifying the space|

## sequences (shortcut)
In all the compose sequences indicated, the leading <kbd>⎄</kbd> is omitted.

|char(s)|details|shortcut|systematic|reason|
|:-:|:-:|:-:|:-:|-|
|ď|d with caron|<kbd>d'</kbd>|<kbd>vd</kbd>|visual similarity to `d'`|
|Ľ, ľ|L with caron|<kbd>L'</kbd>, <kbd>l'</kbd>|<kbd>vL</kbd>, <kbd>vl</kbd>|visual similarity to `L'`, `l'`|
|ť|T with caron|<kbd>t'</kbd>|<kbd>vt</kbd>|visual similarity to `t'`|
|Ʒ, ʒ|[Ezh](https://en.wikipedia.org/wiki/Ezh)|<kbd>Z3</kbd>, <kbd>z3</kbd>|<kbd>ZH</kbd>, <kbd>zh</kbd>|from e**z**h and visual similarity to `3`|

## sequences (complex bases)
Both compose sequences using the complex base(s) and the expanded base(s) are included in mCompose. For example, to type `ǿ`, you can either

- type <kbd>⎄'ø</kbd> (if your keyboard layout has `ø`)
- type <kbd>⎄'⎄/o</kbd> (expand `ø` to <kbd>⎄/o</kbd>)


|group|char(s)|base|
|:-:|-|-|
|acute|Ǽǽ, Ǿǿ|Ææ, Øø|
|caron|Ǯǯ|Ʒʒ|
|dot above|ẛ|ſ|
|hook (palatal)|𝼕, 𝼖, 𝼔, ᶋ, 𝼘, 𝼒|ɹ, ɾ, ŋ, ʃ, ʒ, ʤ|
|hook (retroflex)|ᶑ, 𝼉, ɻ, ᶗ, ᶘ, ᶚ, ᶕ, ᶐ, ᶓ, 𝼚, ꭦ, 𝼙, 𝼅, ꭧ|ɗ, ƭ, ɹ, ɔ, ʃ, ʒ, ə, ɑ, ɛ, ɨ, ʣ, ʤ, ɮ, ʦ|
|hook to left|ʮ, ⱹ|ɥ, ɹ|
|hook to right|ᶑ, ɧ, ʛ|ɖ, ꜧ, ɢ|
|long|ɰ, ɺ|ɯ, ɹ|
|macron|[Ꝥꝥ](https://en.wikipedia.org/wiki/Thorn_with_stroke), Ǣǣ|Þþ, Ææ|
|macron below|[Ꝧꝧ](https://en.wikipedia.org/wiki/Thorn_with_stroke)|Þþ|
|math blackboard bold|ℾℽ, ℿℼ, ⅀|Γγ, Ππ, Σ|
|missing parts|ꭢ|œ|
|small caps|ⱻ, 𝼂, 𝼐, ꟺ, ᴚ, ᴃ, ᵻ, ᵾ, ᴌ, ᴆ, ᴐ, ᴣ, ᴁ, ɶ, ᴕ|ǝ, ᵷ, ʞ, ɯ, ɹ, ƀ, ɨ, ʉ, ł, ð, ɔ, ʒ, æ, œ, ȣ|
|slash|ꬿ, ẜ|ɔ, ſ|
|stroke|[ꬰ](https://en.wiktionary.org/wiki/ꬰ), [ᵼ](https://en.wiktionary.org/wiki/ᵼ), [ᵿ](https://en.wiktionary.org/wiki/ᵿ), ꭏ, ʡ, ẝ, Ꜻꜻ|ɑ, ɩ, ʊ, ꭎ, ʔ, ſ, Ꜹꜹ|
|tilde middle|ꭨ, ᵳ|ɹ, ɾ|
|turned|ɺ, ᴂ, ᴔ, ꭑ, Ɒɒ|ɼ, æ, œ, ꭐ, Ɑɑ|

## sequences (complex ligatures)
In all the compose sequences indicated, the leading <kbd>⎄</kbd> is omitted.

Complex characters in the sequence can (but need not) be expanded. For example, to type `ꭦ` you can either

- type <kbd>⎄dʐ</kbd> (if your keyboard layout has `ʐ`)
- type <kbd>⎄d⎄rz</kbd> (expand `ʐ` to <kbd>⎄rz</kbd>)

|chars|details|sequence|
|:-:|:-:|:-:|
|ꭦ|[dz with retroflex hook](https://en.wiktionary.org/wiki/ꭦ) ([FR](https://fr.wikipedia.org/wiki/ꭦ))|<kbd>dʐ</kbd>|
|𝼙|[dezh with retroflex hook](https://en.wiktionary.org/wiki/𝼙)|<kbd>dᶚ</kbd>|
|𝼅|[lezh with retroflex hook](https://en.wiktionary.org/wiki/𝼅) ([FR](https://fr.wikipedia.org/wiki/𝼅))|<kbd>ɭʒ</kbd>|
|ꭢ|[open OE](https://fr.wikipedia.org/wiki/ꭢ)|<kbd>ɔe</kbd>|
|Ꟗ, ꟗ|[Middle Scots S](https://en.wiktionary.org/wiki/ꟗ)|<kbd>ſS</kbd>, <kbd>ſs</kbd>|
|ﬅ|[Long S T](https://en.wiktionary.org/wiki/ﬅ)|<kbd>ſt</kbd>|
|ꭧ|[ts with retroflex hook](https://en.wiktionary.org/wiki/ꭧ) ([FR](https://fr.wikipedia.org/wiki/ꭧ))|<kbd>tʂ</kbd>|
|ʧ|[tesh](https://en.wiktionary.org/wiki/ʧ) ([FR](https://fr.wikipedia.org/wiki/ʧ))|<kbd>tʃ</kbd>|
|𝼜|[tesh with retroflex hook](https://en.wiktionary.org/wiki/𝼜)|<kbd>tᶘ</kbd>|
|𝼗|[tesh with palatal hook](https://en.wiktionary.org/wiki/𝼗)|<kbd>tᶋ</kbd>|