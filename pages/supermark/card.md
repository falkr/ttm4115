



---
type: nav
prev: ["All extensions", "extensions.html"]
---





# Extension card

Cards provide links with additional elements like text or arrows.
<table class="table"></table>
<table class="table"></table>




<table class="table"><tbody><td>Python type</td><td>CardGroup</td>
<tr></tr>
<td>type</td><td>cards</td>
<tr></tr>
<td>Language</td><td><a href="#">YAML</a></td>
<tr></tr>
<td>Required fields</td><td></td>
<tr></tr>
<td>Optional fields</td><td>columns</td>
<tr></tr>
<td>Post-Yaml Section</td><td>no</td>
<tr></tr></tbody></table>




<table class="table"><tbody><td>Python type</td><td>Card</td>
<tr></tr>
<td>type</td><td>card/text, card/arrow, card/person, card</td>
<tr></tr>
<td>Language</td><td><a href="#">YAML</a></td>
<tr></tr>
<td>Required fields</td><td></td>
<tr></tr>
<td>Optional fields</td><td>link, title, kind, name, detail, image, email, text, link_title</td>
<tr></tr>
<td>Post-Yaml Section</td><td>optional</td>
<tr></tr></tbody></table>






# Example 1

---
type: card/text
title: Dine studentrepresentanter
text: Som student har du en del tillitsvalgte, representanter og andre kontaktpunkter.
link: studentrepresentanter.html
link_title: Finn dine studentrepresentanter
---






## Source Code

```yaml
---
type: card/text
title: Dine studentrepresentanter
text: Som student har du en del tillitsvalgte, representanter og andre kontaktpunkter.
link: studentrepresentanter.html
link_title: Finn dine studentrepresentanter
---
```






# Example 2

---
type: cards
columns: 1
---


---
type: card
title: Finn rett person å snakke med
---
Avhengig av hva det gjelder, har du ulike muligheter for å kontakte noen:
*   Hvis det gjelder et konkret **emne**, ta gjerne kontakt med faglæreren direkte, eller ta det opp med referansegruppen. Om det ikke finnes referansegruppe, ta kontakt med din [klassetillitsvalgt (KTV)](studentrepresentanter.html).
*   Hvis det gjelder undervisning eller det sosiale i hele **årstrinnet**, ta kontakt med din [klassetillitsvalgt (KTV)](studentrepresentanter.html), [studentkontakter](studentrepresentanter.html), eller [din kullkoordinator](kullkoordinator-studenter.html). Du kan også ta kontakt med din studieprogramleder.
*   Hvis du trenger **personlig hjelp eller veiledning**, ta kontakt med din studieveileder. De kan også formidle alle andre hjelpetilbud.
*   Bruk [Si fra!](https://i.ntnu.no/sifra-ansatt) for å varsle om **uønskede hendelser** og **ting som ikke fungerer**.
*   Hvis du ellers lurer på noe, [send oss en e-post](mailto:kontakt@iik.ntnu.no).






## Source Code

```yaml
---
type: cards
columns: 1
---


---
type: card
title: Finn rett person å snakke med
---
Avhengig av hva det gjelder, har du ulike muligheter for å kontakte noen:
*   Hvis det gjelder et konkret **emne**, ta gjerne kontakt med faglæreren direkte, eller ta det opp med referansegruppen. Om det ikke finnes referansegruppe, ta kontakt med din [klassetillitsvalgt (KTV)](studentrepresentanter.html).
*   Hvis det gjelder undervisning eller det sosiale i hele **årstrinnet**, ta kontakt med din [klassetillitsvalgt (KTV)](studentrepresentanter.html), [studentkontakter](studentrepresentanter.html), eller [din kullkoordinator](kullkoordinator-studenter.html). Du kan også ta kontakt med din studieprogramleder.
*   Hvis du trenger **personlig hjelp eller veiledning**, ta kontakt med din studieveileder. De kan også formidle alle andre hjelpetilbud.
*   Bruk [Si fra!](https://i.ntnu.no/sifra-ansatt) for å varsle om **uønskede hendelser** og **ting som ikke fungerer**.
*   Hvis du ellers lurer på noe, [send oss en e-post](mailto:kontakt@iik.ntnu.no).
```






# Example 3

---
type: card/person
name: Firstname Surname
email: email@ntnu.no
detail: Course teacher
image: "_placeholder 200 x 200"
---






## Source Code

```yaml
---
type: card/person
name: Firstname Surname
email: email@ntnu.no
detail: Course teacher
image: "_placeholder 200 x 200"
---
```






# Example 4

---
type: card/arrow
title: For studenter
link: student.html
---






## Source Code

```yaml
---
type: card/arrow
title: For studenter
link: student.html
---
```






# Example 5

---
type: card/text
title: IIK Snacks and Science
text: Seminar om forskning for studenter ved IIK.
link: snacks.html
---






## Source Code

```yaml
---
type: card/text
title: IIK Snacks and Science
text: Seminar om forskning for studenter ved IIK.
link: snacks.html
---
```






# Example 6

---
type: cards
columns: 4
---


---
type: card/text
title: Teknostart Dag 1
text: Tirsdag
link: day1.html
---

---
type: card/text
title: Teknostart Dag 2
text: Tirsdag
link: day1.html
---

---
type: card/text
title: Teknostart Dag 3
text: Tirsdag
link: day1.html
---

---
type: card/text
title: Teknostart Dag 4
text: Tirsdag
link: day1.html
---






## Source Code

```yaml
---
type: cards
columns: 4
---


---
type: card/text
title: Teknostart Dag 1
text: Tirsdag
link: day1.html
---

---
type: card/text
title: Teknostart Dag 2
text: Tirsdag
link: day1.html
---

---
type: card/text
title: Teknostart Dag 3
text: Tirsdag
link: day1.html
---

---
type: card/text
title: Teknostart Dag 4
text: Tirsdag
link: day1.html
---
```



