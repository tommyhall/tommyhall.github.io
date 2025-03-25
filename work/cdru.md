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
  <div class="col-10 offset-1 col-sm-10 offset-sm-1 col-md-8 offset-md-2 col-lg-6 offset-lg-3">
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
  <div class="col-10 offset-1 col-sm-10 offset-sm-1 col-md-8 offset-md-2 col-lg-6 offset-lg-3">
    <h2>Team &amp; Role</h2>
    <p>I wore a number of hats on this project&mdash;software development, UX design, user research, and telemetry design & data analysis&mdash;helping take the system from early concepts through to a working product. I was responsible for designing the interaction model, running user testing with child participants, and building the telemetry system to track and analyze performance data.</p>
    <p>I worked alongside a small team: another developer/researcher, research assistants from the CDRU, the pediatric psychologists leading the lab, and a few other developers and artists from time to time.</p>
  </div>
</div>

<div class="row case-study justify-content-center">
  <div class="col-10 offset-1 col-sm-10 offset-sm-1 col-md-8 offset-md-2 col-lg-6 offset-lg-3">
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
    <p>We did some usability testing and iterated on each module before moving on to the next.</p>
    <p>Along the way, we also built support tools to streamline content creation. One was a cutscene builder&mdash;an application that allowed the psychologists to place cars, camera movements, and an avatar on a 2D canvas, then translating it into an in-game sequence that we could play for a user. This was the basis of the feedback that participants would see.</p>
  </div>
</div>

<div class="row case-study justify-content-center">
  <div class="col-10 offset-1 col-sm-10 offset-sm-1 col-md-8 offset-md-2 col-lg-6 offset-lg-3">
    <h2>Understanding the Problem</h2>
    <p>To help us understand the problem, we performed stakeholder interviews, then defined user groups and use cases.</p>
    <h4>Stakeholder Interviews</h4>
    <p>We interviewed the researchers, who were domain experts in pediatric psychology. We helped them refine the project goals, and to define research measures to be captured by the system. We worked with them throughout the project to ensure that the training game aligned with their research goals.</p>
    <h4>User Groups</h4>
    <p>The research subjects (participants), children ages 6-9, were the main users of the system. They needed to be able to look and walk around virtual environments using an Xbox controller. The system needed to be engaging in order to maintain the attention of the children so that they could complete the training comfortably, and in a reasonable amount of time.</p>
    <p>The other primary users of the system were research assistants at the CDRU. They needed to be able to set up new participants quickly and easily, as they had only limited time with each child. They also needed to be able to recover from errors in the event of a technical failure, or if the participant needed to take a break, and resume from where they left off.</p>
  </div>
</div>

<div class="row case-study justify-content-center">
  <div class="col-10 offset-1 col-sm-10 offset-sm-1 col-md-8 offset-md-2 col-lg-6 offset-lg-3">
    <h2>Building the MVP</h2>
    <p>We knew that the system needed to support the following:</p>
    <ul>
      <li>Multiple environments with different levels of visibility for oncoming traffic (e.g. a curve in the road, parked cars, etc.).</li>
      <li>The ability to detect when the participants engaged in dangerous behaviour (failing to look both ways, entering the street too close to an oncoming car, etc.), and provide immediate feedback on their actions.</li>
      <li>The ability to assess when participants had achieved competence with a training concept, and advance them to the next concept.</li>
    </ul>
    <p>We sketched out each of the possible scenarios and environments, and created flow diagrams to illustrate how participants would flow between the training stages.</p>
    <p>Given the complex nature of the immediate feedback and system flow, a working prototype was required to test participants. The original vision of the system was a desktop application, controlled with an Xbox controller, with three widescreen monitors to provide a wider field of view. We worked with the researchers to define which features were most essential, and built a minimum viable product (MVP) to test those features with users.</p>
    <figure class="figure">
      <img class="img-responsive" src="{{ site.baseurl }}/images/portfolio/case_studies/intern.jpg" alt="flow diagram" />
      <figcaption class="figure-caption">An intern helps to build the prototype.</figcaption>
    </figure>
  </div>
</div>

<div class="row case-study justify-content-center">
  <div class="col-10 offset-1 col-sm-10 offset-sm-1 col-md-8 offset-md-2 col-lg-6 offset-lg-3">
    <h2>The Process</h2>
    <p>After we built the MVP, we started the process of testing with users and iterating the prototype. After each round of user testing (generally 3-5 children), we would identify the most common issues and brainstorm solutions for them. We’d present these to the researchers, and collaboratively decide on the best course of action. We would then integrate the solutions into the system, and perform more user testing.</p>
    <figure class="figure">
      <img class="img-responsive" src="{{ site.baseurl }}/images/portfolio/case_studies/designthinking.jpeg" alt="Design Thinking diagram" />
    </figure>
  </div>
</div>

<div class="row case-study justify-content-center">
  <div class="col-10 offset-1 col-sm-10 offset-sm-1 col-md-8 offset-md-2 col-lg-6 offset-lg-3">
    <h2>Results</h2>
    <p>User testing helped us to identify a number of usability problems with the system. Some of the major problems and our solutions are summarized in the table below, along with the results that our solutions achieved.</p>
  </div>
</div>

<div class="row case-study justify-content-center">
  <div class="col-12">
    <table class="table table-responsive table-bordered table-striped">
      <thead>
        <th><strong>Problem</strong></th>
        <th><strong>Our solution</strong></th>
        <th><strong>Result</strong></th>
      </thead>
      <tbody>
        <tr>
          <td>Participants found the training tasks too difficult and were often unable to complete them.</td>
          <td>We broke the training stages down into smaller, more easily understood sections, allowing them to focus on one concept at a time.</td>
          <td>Significant improvement in training completion rates.</td>
        </tr>
        <tr>
          <td>Participants  weren’t engaged with the system, and were losing interest before completing the training tasks.</td>
          <td>We changed from using a 3-screen setup to using an Oculus Rift (VR headset) to increase immersion. We added animations, updated the scoring system, and streamlined the flow between training stages.</td>
          <td>The amount of time it took to complete the training session was reduced, participants were far more engaged, and completion rates improved.</td>
        </tr>
        <tr>
          <td>Participants had trouble navigating the virtual world using the controller.</td>
          <td>We tested different control schemes until kids better understood how to navigate the world, and created an interactive tutorial to establish a baseline for control competence.</td>
          <td>Reduced frustration in the participants. Significant reduction in the number of control-related errors made while using the system.</td>
        </tr>
        <tr>
          <td>Participants didn’t understand some of the training instructions and would repeatedly make the same mistake.</td>
          <td>We iteratively re-worked the problematic training scripts, testing with users until the comprehension rate increased.</td>
          <td>Higher comprehension of training videos, fewer repeated mistakes.</td>
        </tr>
        <tr>
          <td>Participants experienced motion sickness when using the Oculus Rift headset.</td>
          <td>We changed the way the system displayed replays based on VR motion sickness research.</td>
          <td>Almost no participants reported motion sickness.</td>
        </tr>
      </tbody>
    </table>
  </div>
</div>

<div class="row case-study justify-content-center">
  <div class="col-10 offset-1 col-sm-10 offset-sm-1 col-md-8 offset-md-2 col-lg-6 offset-lg-3">
    <p>One problem area that our user testing revealed was user engagement. The users were in the age range of 6 to 9, and were frequently losing interest in the training, which meant that their performance wasn't improving much. We ended up making a number of tweaks to remedy this, including:</p>
    <ul>
      <li>Making the instructions shorter and straight to the point</li>
      <li>Adjusting the replay camera angles to make the feedback more clear</li>
      <li>Adding a policeman character to deliver any audio instructions</li>
    </ul>
    <p>We also updated the scoring system to give more rewards for good performance, and make it easier for the participants to demonstrate mastery and move on to the next lesson. Overall, these changes had a marked impact on user engagement.</p>
    <figure class="figure">
      <img class="img-responsive" src="{{ site.baseurl }}/images/portfolio/case_studies/police.jpg" alt="policeman character" />
      <figcaption class="figure-caption">We added a policeman character to deliver dialog.</figcaption>
    </figure>
    <figure class="figure">
      <img class="img-responsive" src="{{ site.baseurl }}/images/portfolio/case_studies/training3.jpg" alt="a feedback video from the training system" />
      <figcaption class="figure-caption">A feedback video from the training system.</figcaption>
    </figure>
    <p>The CDRU is currently collecting data using the training system, and early results are promising. The project was featured on CityNews in Toronto (1:25 onwards in the video below shows some of the training system in action).</p>
  </div>
</div>

<div class="row case-study justify-content-center">
  <div class="col-10 offset-1 col-sm-10 offset-sm-1 col-md-8 offset-md-2 col-lg-6 offset-lg-3">
    <div class="embed-responsive embed-responsive-16by9">
    <object class="embed-responsive-item" id="flashObj" classid="clsid:D27CDB6E-AE6D-11cf-96B8-444553540000" codebase="https://download.macromedia.com/pub/shockwave/cabs/flash/swflash.cab#version=9,0,47,0"><param name="movie" value="https://c.brightcove.com/services/viewer/federated_f9?isVid=1" /><param name="bgcolor" value="#FFFFFF" /><param name="flashVars" value="videoId=5194439063001&playerID=655898905001&playerKey=AQ~~,AAAAii5Rh_E~,CtyoY0YlBsbcIexFHrivx99PNEri0ZG2&domain=embed&dynamicStreaming=true" /><param name="base" value="https://admin.brightcove.com" /><param name="seamlesstabbing" value="false" /><param name="allowFullScreen" value="true" /><param name="swLiveConnect" value="true" /><param name="allowScriptAccess" value="always" /><embed src="https://c.brightcove.com/services/viewer/federated_f9?isVid=1" bgcolor="#FFFFFF" flashVars="videoId=5194439063001&playerID=655898905001&playerKey=AQ~~,AAAAii5Rh_E~,CtyoY0YlBsbcIexFHrivx99PNEri0ZG2&domain=embed&dynamicStreaming=true" base="http://admin.brightcove.com" name="flashObj" width="640" height="446" seamlesstabbing="false" type="application/x-shockwave-flash" allowFullScreen="true" swLiveConnect="true" allowScriptAccess="always" pluginspage="https://www.macromedia.com/shockwave/download/index.cgi?P1_Prod_Version=ShockwaveFlash"></embed></object>
    </div>
  </div>
</div>

<div class="row case-study justify-content-center">
  <div class="col-10 offset-1 col-sm-10 offset-sm-1 col-md-8 offset-md-2 col-lg-6 offset-lg-3">
    <p>In the end, we created a system that has shown promise in improving child safety when crossing the street, using an engaging VR interface, and with lessons that are clear and understandable for the target users. I also learned a lot about pedestrian safety, and can't help but think about this project any time I'm about to step into the street!</p>
  </div>
</div>
