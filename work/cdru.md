---
layout: default
description: A description of the work performed for the Child Development Research Unit, including user interviews, minimum viable product, prototyping, usability testing.
---

<div class="row case-study justify-content-center">
  <div class="col-12 col-sm-8 offset-sm-2">
    <h1>From VR to real-world safety: Helping kids learn to cross the street</h1>
  </div>
</div>

<div class="row case-study justify-content-center">
  <div class="col-10 offset-1 col-sm-10 offset-sm-1 col-md-8 offset-md-2 col-lg-8 offset-lg-2">
    <h2>The Project</h2>
    <p>The Child Development Research Unit (CDRU) at the University of Guelph studies developmental issues related to child health. I'd worked with them before&mdash;building VR simulations to study child pedestrian behaviour&mdash;so when they set out to create a VR training game to help teach children (ages 6-9) how to cross the street safely, I joined a small team to help make it happen.</p>
    <p>The goal was to build a finished system that could:</p>
    <ul>
      <li>Train kids in realistic suburban environments</li>
      <li>Track their performance and learning</li>
      <li>Support academic research on pedestrian safety</li>
      <li>Eventually be rolled out in classrooms</li>
    </ul>
    <p>And the system also needed to be:</p>
    <ul>
      <li>Engaging enough to keep kids focused</li>
      <li>Simple enough to navigate with an Xbox controller</li>
      <li>Flexible enough for researchers to manage study participants, collect data, and recover from interruptions or technical issues</li>
    </ul>
    <p>The project spanned about two years in total.</p>
  </div>
</div>

<div class="row case-study justify-content-center">
  <div class="col-10 offset-1 col-sm-10 offset-sm-1 col-md-8 offset-md-2 col-lg-8 offset-lg-2">
    <h2>Team &amp; Role</h2>
    <p>I wore a number of hats on this project&mdash;software development, UX design, user research, and telemetry design & data analysis&mdash;helping take the system from early concepts through to a working product. I was responsible for designing the interaction model, running user testing with child participants, and building the telemetry system to track and analyze performance data.</p>
    <p>I worked alongside a small team: another developer/researcher, research assistants from the CDRU, the pediatric psychologists leading the lab, and a few other developers and artists from time to time.</p>
  </div>
</div>

<div class="row case-study justify-content-center">
  <div class="col-10 offset-1 col-sm-10 offset-sm-1 col-md-8 offset-md-2 col-lg-8 offset-lg-2">
    <h2>Development</h2>
    <p>We developed the system in Python using the Vizard engine, building it from the ground up in collaboration with the pediatric psychologists.</p>
    <p>Working with them, we sketched out key scenarios and environments participants would encounter, creating flow diagrams to map out how training stages would progress. We worked together to prioritize essential features.</p>
    <figure class="figure">
      <img class="img-responsive" src="{{ site.baseurl }}/images/portfolio/case_studies/flowdiagram.PNG" alt="flow diagram" />
      <figcaption class="figure-caption">A flow diagram for for the states and stages of the training system.</figcaption>
    </figure>
    <p>The system needed to support:</p>
    <ul>
      <li>Multiple environments simulating unsafe pedestrian conditions (e.g., curves in the road, parked cars, and other visual occlusions)</li>
      <li>Real-time detection of unsafe behaviour (e.g., not looking both ways, stepping into traffic too late)</li>
      <li>Timely, relevant feedback to help participants understand and correct their mistakes</li>
      <li>Assessment of skill progression, so participants could advance once they were competent with a concept</li>
    </ul>
    <p>Given the complexity of the real-time feedback system, we knew we needed to test early with a functional prototype.</p>
    <p>We broke development into modules, starting with a basic environment where cars would pass and the user could walk around. From there, we layered on functionality, testing internally at each step before rolling out our first training module with real-time feedback.</p>
    <figure class="figure">
      <img class="img-responsive" src="{{ site.baseurl }}/images/portfolio/case_studies/intern.jpg" alt="flow diagram" />
      <figcaption class="figure-caption">An intern helps to build the prototype.</figcaption>
    </figure>
    <p>We did some usability testing and iterated on each module before moving on to the next.</p>
    <p>Along the way, we also built support tools to streamline content creation. One was a cutscene builder&mdash;an application that allowed the psychologists to place cars, camera movements, and an avatar on a 2D canvas, then translating it into an in-game sequence that we could play for a user. This was the basis of the feedback that participants would see.</p>
    <figure class="figure">
      <img class="img-responsive" src="{{ site.baseurl }}/images/portfolio/case_studies/training3.jpg" alt="a feedback video from the training system" />
      <figcaption class="figure-caption">A feedback video from the training system.</figcaption>
    </figure>
  </div>
</div>

<div class="row case-study justify-content-center">
  <div class="col-10 offset-1 col-sm-10 offset-sm-1 col-md-8 offset-md-2 col-lg-8 offset-lg-2">
    <h2>Usability Testing &amp; Iteration</h2>
    <p>Once we had a few training modules ready, we began user testing with children aged 6-9&mdash;our target audience. The CDRU had an existing panel of child participants, which made recruitment easier.</p>
    <p>After each round of usability testing, we identified the most common and significant issues, brainstormed solutions, and worked with the psychologists to determine the best course of action. I then worked with the other developers to implement changes before running another round of testing.</p>
    <p>Through this process, we solved a number of key usability challenges, detailed below.</p>
    <h4>Task Complexity</h4>
    <p>Some training tasks were too complex for the age group, and many participants struggled to understand or complete them.</p>
    <p><strong>Solution:</strong></p>
    <ul>
      <li>We broke training into smaller, more focused sections, each teaching only one concept at a time.</li>
      <li>We adjusted replay camera angles to make each action clearer.</li>
      <li>We simplified training scripts, including language adjustments. For example: Some children had trouble differentiating “left” and “right”, so we found alternative ways to guide them.</li>
    </ul>
    <p><strong>Impact:</strong></p>
    <p>Our changes significantly improved training completion rates.</p>
    <h4>Engagement</h4>
    <p>Some children lost interest before completing the training, reducing its effectiveness.</p>
    <p><strong>Solution:</strong></p>
    <ul>
      <li>We added animations to the instructions and feedback, featuring a cartoon police officer.</li>
      <li>We introduced a star rating system with bonuses for strong performance.</li>
      <li>We shortened instructions and streamlined transitions between training stages.</li>
    </ul>
    <figure class="figure">
      <img class="img-responsive" src="{{ site.baseurl }}/images/portfolio/case_studies/police.jpg" alt="policeman character" />
      <figcaption class="figure-caption">We added a policeman character to deliver dialog.</figcaption>
    </figure>
    <p><strong>Impact:</strong></p>
    <ul>
      <li>Time needed to complete the training was reduced.</li>
      <li>Engagement improved significantly.</li>
      <li>Completion rates further increased.</li>
    </ul>
    <h4>Controls</h4>
    <p>Some participants found the controls confusing or difficult to use, particularly in combination with the VR headset.</p>
    <p><strong>Solution:</strong></p>
    <ul>
      <li>We tested different control schemes to find one that felt more intuitive.</li>
      <li>We created an interactive tutorial to establish a baseline for control competence before training began.</li>
    </ul>
    <p><strong>Impact:</strong></p>
    <p>This substantially reduced control-related errors and frustration.</p>
    <h4>Motion Sickness</h4>
    <p>VR can cause motion sickness in some people. This was a major blocker for any participants impacted. Our system initially had two major triggers:</p>
    <ol>
      <li>Technical performance issues - Low frame rates and input lag can increase nausea.</li>
      <li>Sensory conflict in replays - The feedback system required showing participants replays and instructions with dynamic camera movements while they were sitting still, which could create sensory conflict.</li>
    </ol>
    <p><strong>Solution:</strong></p>
    <ul>
      <li>We improved performance efficiency to maintain a higher frame rate, including new 3D models and lighting.</li>
      <li>We redesigned how the replays worked. Instead of shifting the participant’s view, we gently reset them to a starting position and placed a large projected screen in front of them in the virtual world, much like a movie theatre. Replays played on this screen instead, avoiding camera movement issues.</li>
    </ul>
    <p><strong>Impact:</strong></p>
    <ul>
      <li>Motion sickness was dramatically reduced.</li>
      <li>Training completion increased to nearly 100%.</li>
    </ul>
    <p>(One new issue we ran into after implementing the movie screen solution was that some participants ignored it, missing important instructions. This was largely solved by improving feedback and engagement, as described earlier.)</p>
  </div>
</div>

<div class="row case-study justify-content-center">
  <div class="col-10 offset-1 col-sm-10 offset-sm-1 col-md-8 offset-md-2 col-lg-8 offset-lg-2">
    <h2>Telemetry &amp; Behavioural Metrics</h2>
    <p>A key part of the system was telemetry data&mdash;this was how we could quantify user behaviour and prove whether the training interventions were effective.</p>
    <p>To define what needed tracking, I worked closely with the pediatric psychologists leading the study. They had high-level research questions, like:</p>
    <ul>
      <li>How fast were the participants moving?</li>
      <li>Was it a safe road entry?</li>
      <li>Did they check for oncoming traffic before stepping into the road?</li>
      <li>Did they pay attention to traffic while crossing?</li>
    </ul>
    <p>My job was to translate these behavioural questions into concrete, measurable metrics that we could track in the program.</p>
    <h4>Raw data &rarr; Meaningful insights</h4>
    <p>We had access to the following spatial data:</p>
    <ul>
      <li>Participant location and viewing angle</li>
      <li>Car positions (moving and parked)</li>
      <li>Road boundaries and locations of visual obstructions</li>
    </ul>
    <p>We had all of this at a 60Hz sampling rate.</p>
    <p>This gave us raw data, but we needed to extract meaning from it. For example, defining “paying attention to traffic” required translating head orientation and timing data into a clear behavioural measure.</p>
    <p>Once each metric was defined, I:</p>
    <ul>
      <li>Implemented it in code and tested its accuracy.</li>
      <li>Documented it&mdash;how it was calculated, expected output formats, and how it should be interpreted.</li>
      <li>Created visualizations to help the psychologists interpret the data, when appropriate.</li>
    </ul>
    <p>One tricky problem was that since frame rate and update delays while the program was running could cause small spikes in velocity measurements, so I also applied signal processing techniques, such as Savitzky-Golay filtering, to smooth the data somewhat and ensure reliable insights.</p>
  </div>
</div>

<div class="row case-study justify-content-center p-b-30">
  <div class="col-10 offset-1 col-sm-10 offset-sm-1 col-md-8 offset-md-2 col-lg-8 offset-lg-2">
    <h2>Outcome &amp; Impact</h2>
    <p>The system, later officially called <em>Safe Peds</em>, proved to be highly effective in teaching safe pedestrian behaviours to children. Testing showed marked improvements in how children assessed traffic, checked for danger, and crossed streets safely after training.</p>
    <p>The impact extended beyond the lab:</p>
    <ul>
      <li>The project’s findings were published in major academic journals, including the Journal of Pediatric Psychology.</li>
      <li>The research contributed to multiple PhD dissertations and was presented at international conferences.</li>
      <li>The project was covered by national news outlets, including The Toronto Star and CityNews.</li>
      <li>The system has since been rolled out in schools across Ontario, where it continues to be used as a training tool for pedestrian safety education.</li>
    </ul>
    <p>This was a project that had a real-world impact, using VR and behavioural research to help make streets safer for kids. I can't help but think about it any time I step into the street.</p>
  </div>
</div>
