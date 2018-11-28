---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: page
---





<section class="content">

<p>Encapsulate a request as an object, thereby letting users parameterize clients
with different requests, queue or log requests, and support undoable
operations.</p>

<blockquote>
<p>Encapsulate a request as an object, thereby letting users parameterize clients
with different requests, queue or log requests, and support undoable
operations.</p>
</blockquote>

<p>Then, the rest of that sentence is just a list of stuff you could maybe possibly
use the pattern for. Not very illuminating unless your use case happens to be in
that list. <em>My</em> pithy tagline for the Command pattern is:</p>
<p><strong>A command is a <em><span name="latin">reified</span> method call</em>.</strong></p>
<aside name="latin"><p>Encapsulate a request as an object, thereby letting users parameterize clients
with different requests, queue or log requests, and support undoable
operations.</p>
</aside>

<h1>Command</h1>
<!--<h1 class="book"><a href="/">Game Programming Patterns</a><span class="section"><a href="design-patterns-revisited.html">Design Patterns Revisited</a></span></h1>-->
<p>Command is one of my favorite patterns. Most large programs I write, games or
otherwise, end up using it somewhere. When I&#8217;ve used it in the right place, it&#8217;s
neatly untangled some really gnarly code. For such a swell pattern, the Gang of
Four has a predictably abstruse description:</p>

<blockquote>
<p>Encapsulate a request as an object, thereby letting users parameterize clients
with different requests, queue or log requests, and support undoable
operations.</p>
</blockquote>

<h3>Roles</h3>

<p>Command is one of my favorite patterns. Most large programs I write, games or
otherwise, end up using it somewhere. When I&#8217;ve used it in the right place, it&#8217;s
neatly untangled some really gnarly code. For such a swell pattern, the Gang of
Four has a predictably abstruse description:</p>
		
<ul>
<li><code>gate_1: Gate</code></li>
<li><code>lights_1: Lights</code></li>
<li><code>card_1: Card Reader</code></li>
<li><code>w_1: Weight</code></li>
<li><code>c: Computer</code></li>
<li><code>p: Payment</code></li>
<li><code>gate_2: Gate</code></li>
<li><code>lights_2: Lights</code></li>
<li><code>card_2: Card Reader</code></li>
<li><code>w_2: Weight</code></li>
</ul>

<h3>Favorite List</h3>
<ul>
<li><strong>F1 (REQUIREMENTS INSTABILITY)</strong> refers to the effect that unstable requirements have on up-front planning. Being able to respond to changing requirements is one of the underlying values of the Agile Manifesto and is central to our conceptual definition of agility.</li>
<li><strong>F2 (TECHNICAL RISK)</strong> describes the effect that exposure to potentially negative outcome has on a team’s up-front effort. Risk is caused by complex architecture. </li>
<li><strong>F3 (EARLY VALUE)</strong> refers to a customer’s need to gain value from a system or product being built (rather than simply provide feedback) before all functionality has been implemented, perhaps in the form of a minimum viable product.</li>
<li><strong>F4 (TEAM CULTURE)</strong> describes the effect that a team’s culture has on its agility and the effort it puts into up-front planning. A culture that is people-focused and collaborative is a very important factor in a team’s ability to communicate.</li>
<li><strong>F5 (CUSTOMER AGILITY)</strong> describes the culture of the customer’s organisation and the huge impact that it has on the amount of up-front architecture design a team does. A customer must have an agile culture that is similar to the team’s culture, whether the team is in-house or an ISV (independent software vendor), for the team to be truly agile. A highly-agile team will not fit in well with a heavyweight process-oriented organisation that prefers planning and formal communication.</li>
<li><strong>F6 (EXPERIENCE)</strong> describes the impact that an experienced architect’s tacit knowledge and implicit decision-making ability has on the time that an agile team spends on up-front design. Experienced architects have breadth of knowledge; they are more likely to be aware of suitable options for implementing a solution and better understand what will work and what will not.</li>
</ul>


<h1>Learning Goals</h1>
		
<table class="table">
		<span name="hint"></span>
		<aside name="hiny"><p>Come back here regularly and check if you reach these goals. If not, <a href="">tell us</a>!</p>
		</aside>
<tbody><tr>
<td>Learning Goal</td>
<td>Comment</td>
</tr>
<tr>
<td><strong>5.</strong> Capture user requirements and synthesize relevant use cases at a proper level of detail.
</td>
<td>
This is an underestimated skill. The resulting use cases are often written in text and don’t look spectacular. But formulating bad use cases is the earliest phase in a project where things can go wrong.
</td>
</tr>
<tr>
<td><strong>6.</strong> Write project deliverables that describe system requirements, properties and solutions.
</td>
<td>
Producing the right documents, emphasizing relevant questions, reasonable precision level. Can uncover project problems early or even before they arise. Again, learn to ask the right questions.
</td>
</tr>
<tr>
<td><strong>7.</strong> Plan and coordinate the development of larger software products (consisting of more than one single application) within a team of developers.
</td>
<td>
To coordinate a project, you need to know a lot about the architecture of a system, but also the process how to build it and potential pitfalls.
</td>
</tr>
<tr>
<td><strong>8.</strong> Apply agile development methods and reflect about their usage within the context of a project.
</td>
<td>
Selecting and reflecting over development methods: How much should you plan ahead? Should you use an agile method? Read an article on development methods, and understanding it based on own experience.
</td>
</tr>
<tr>
<td><strong>9.</strong> Make proper design choices for the system architecture and document them accordingly.
</td>
<td>
Learn how to reason about different alternatives together with others. This can happen at a whiteboard or through a document. No matter how, good visualizations are helpful in this task.
</td>
</tr>
</tbody></table>

</section>