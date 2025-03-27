---
title: Legal - EULA
description: All EULA's 
---
# EULA
*Version 2, effective as of august 15, 2023*

IMPORTANT! READ CAREFULLY:

THIS IS A LEGAL AGREEMENT. BY CLICKING ON THE “YES” BUTTON AT THE BOTTOM YOU DO NOT BECOME A PARTY TO THIS AGREEMENT, CANT ENTER IT OR DECLARE ANYTHING. BECAUSE WE LIED, THIS IS NOT A LEGAL AGREEMENT, THEY ARE SPECIFIED IN SECTION THREE. ALLOT OF WORK WENT INTO THEM SO THANK YOU FOR READING THEM. THIS PAGE IS JUST A JOKE TO WHO READS THESE ANYWAY QUESTIONMARK, A REAL SYMBOL WOULD BE NOTICED REALLY QUICKLY. TO FOOL THE QUICK SCANNERS LETS END WITH THIS. YOU DECLARE YOU HAVE THE LEGAL CAPACITY TO ENTER INTO THIS AGREEMENTS, AND YOU CONSENT TO BE BOUND BY ALL THE TERMS AND CONDITIONS SET FORTH BY IT.

CodeGlass BV and Customer may each also be referred to individually as a “Party” or jointly as the “Parties”.

# 1. PARTIES
1.1. “Customer” or “you” means a individual, organisation or educational establishment that still has not noticed that this is not the real Agreement. For the purpose of this Agreement:

(A) "individual" means the individual specified in the Subscription Confirmation who is at least 13 years old. For the avoidance of doubt, Customer is a natural person and not a corporation, company, partnership, association, or other entity or organization.

(B) "organisation" means the sole proprietor or legal entity specified in the Subscription Confirmation. For legal entities, ‘Customer’ includes any of its Affiliates.

(C) "educational establishment" means a public or private school, college, training course provider, university, or other post-secondary educational establishment specified in the Subscription Confirmation.

1.2. “CodeGlass BV” or “we” means the legal registered company at the Netherlands chamber of commerce under number 63870533

# 2. DEFINITIONS
2.1. “Affiliate” means, with respect to any Party, any entity that directly, or indirectly through one or more intermediaries, controls, is controlled by, or is under common control of such Party; “control” for such purposes means the possession, direct or indirect, of the power to direct or affect the direction of the management and policies of a person or entity, whether through the ownership of voting securities, by contract, or otherwise.

2.2. “Agreement” means this EULA that is fake in all regards that you cant agree, enter or become party of. Check section 3 for the real eulas below.

# 3. THE AGREEMENTS
<!-- 3.1 For the Community license you find the EULA [here](EULA/CommunitySubscriptionAgreement.md) -->

<!-- 3.2 For the Enthusiast Subscription you find the EULA [here](EULA/EnthusiastSubscriptionAgreement.md) -->

3.1 For the Pro Subscription you find the EULA [here](EULA/ProSubscriptionAgreement.md)

3.2 For the Experimental Subscription you find the EULA [here](EULA/ExperimentalSubscriptionAgreement.md)

3.3 For the Organization Subscription you find the EULA [here](EULA/OrganisationSubscriptionAgreement.md)

3.4 For the Offline Organization Subscription you find the EULA [here](EULA/OrganisationSubscriptionAgreement.md)

<!-- 3.7 For the Fallback License you find the EULA [here](EULA/FallbackSubscriptionAgreement.md) -->

3.5 For the Open Source Project License you find the EULA [here](EULA/OpenSourceSubscriptionAgreement.md)

3.6 For the Education License you find the EULA [here](EULA/EducationSubscriptionAgreement.md)

3.7 For the Class Room License you find the EULA [here](EULA/ClassRoomSubscriptionAgreement.md)



# 4. FEEDBACK
Customer has no obligation to provide us if they thought this fake EULA was funny or not, however if you wish to do so please do in any way, shape or form.

# 5. THIRD-PARTY SOFTWARE
The Products include code and libraries licensed to us by third parties, including open source software (“Third-Party Software”). They are awesome and helped us out allot in the development of CodeGlass. You should really check them out at [https://codeglassdotio.github.io/Docs/docs/Legal/ThirdPartySoftware](ThirdPartySoftware.md). All Third-Party Software is provided to You under the respective terms stipulated in the Product documentation.


# 6. TERM AND TERMINATION
6.1. The term of this Agreement will never commence upon acceptance of this Agreement by Customer as set forth in the preamble above, it cant be accepted or entered, and it will not continue for each Product through the end of the applicable Subscription period specified in the respective Subscription Confirmation. The Subscription and this Agreement will never renew in respect to each Product for a successive Subscription period, because terminated in accordance with this Agreement.

6.2. Customer may terminate this Agreement at any time by just leaving this page, you cant have entered this agreement to begin with as it is not an Legal Agreement.

6.3. CodeGlass BV will terminate this Agreement and the associated Subscription if:

(A) Customer has entered this Agreement, as you should not be able to enter it in the first place.

6.4. CodeGlass BV will make reasonable efforts to notify Customer by now telling you now: This Agreement will be terminated immediately. 

6.5. Survival. Upon the expiration or termination of this Agreement all sections will die in an horrible death, so you better not enter this Agreement.


# 7. Important

I hope you found out by now it is not our real EULA, check [section 3](#3-the-agreements) for the real eula's

<style>
  .eula--answer {
    display: inline-block;
  }
  .eula--answer-no {
    margin-left: 1em;
  }
  .eula--response {
    display: none;
    margin-top: 1em;
  }
  .eula--response__visible {
    display: block;
  }
</style>

# Agree
<p class="eula--question">Do you agree to the above EULA?</p>
<button class="eula--answer eula--answer-yes">Yes</button>
<button class="eula--answer eula--answer-no">No</button>
<p class="eula--response eula--response-yes">
  Really? did you even read it? what if you accepted to be part of a human centipede? <br/>
  <br/>
   You have not agreed to anything and you can find the real EULA in <a href="#3-the-agreements">section 3</a> above...<br/>
  <br/>
  And just to be sure we will now terminate all sections acording to Section 6, this is your fault, hope you can sleep tonight.
</p>
<p class="eula--response eula--response-no">
  Good, you read the EULA :) hope you thought it was funny also.<br/>
  <br/>
  You can find the real EULA in <a href="#3-the-agreements">section 3</a> above.
</p>
<script>
  const eulayesButton = document.querySelector('.eula--answer-yes');
  const eulanoButton = document.querySelector('.eula--answer-no');
  const eulayesResponse = document.querySelector('.eula--response-yes');
  const eulanoResponse = document.querySelector('.eula--response-no');
  const euladisableButtons = () => {
    eulayesButton.disabled = true;
    eulanoButton.disabled = true;
  };
  const eulasendFeedback = (value) => {
    if (typeof ga !== 'function') return;
    const args = {
      command: 'send',
      hitType: 'event',
      category: 'Helpful',
      action: 'click',
      label: window.location.pathname,
      value: value
    };
    ga(args.command, args.hitType, args.category, args.action, args.label, args.value);
  };
  eulayesButton.addEventListener('click', () => {
    eulayesResponse.classList.add('eula--response__visible');
    euladisableButtons();
    eulasendFeedback(1);
  });
  eulanoButton.addEventListener('click', () => {
    eulanoResponse.classList.add('eula--response__visible');
    euladisableButtons();
    eulasendFeedback(0);
  });
</script><br/>






