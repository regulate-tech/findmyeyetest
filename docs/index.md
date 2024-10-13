# FindMyEyeTest - an [NHSHackDay](https://nhshackday.com/) Project

## The Problem

Millions of people in the UK visit their local opticians each year for a free eye test.

'Free' in this case means that the NHS pays the optician just over £20 for carrying out the test.

The eligibility criteria and exact payments vary across the four nations of the UK and are set out in regulations.

Opticians offer the tests under the terms of the General Ophthalmic Services contract which is negotiated periodically between their representative bodies and the four governments.

People getting an eye test usually leave the opticians with a card or paper showing their prescription.

Opticians are required to provide this under the terms of a Government regulation from 1989 with the does-what-it-says-on-the-tin title of [The Sight Testing (Examination and Prescription) Regulations 1989](https://www.legislation.gov.uk/uksi/1989/1176/regulation/5/made)

It is hard for people to keep track of this printed document over time and many will not have it when they next visit an optician, for example because they have broken their glasses.

This has several negative effects -

- Simple frustration and time-wasting for the service recipient and optician as they try to track this down.
- Risk of inaccuracy in records if they have to be re-entered manually from a paper document.
- No ability for the individual to see their changing prescriptions over time.
- Additional costs for the NHS or individual if they have to re-test following loss.

## The Solution

There are many standards and products in use in 2024 for storing personal data similar to optical prescription records on a personal device.

Our solution takes the output from the optician, converts into a standards-based machine-usable format and shows how this can be displayed in a common personal device data store, the Google Wallet.

This model can be improved on the input side by having opticians provide prescriptions in a QR code format, and on the output side by adding other types of storage such as the Apple Pass and NHS App.

### The Technology

#### STEP 1 - Define the Optical Prescription Data Structure

There is a body defining global health information standards called Fast Healthcare Interoperability Standards (FHIR) which [the NHS is committed to using](https://digital.nhs.uk/services/fhir-apis).

We built on their [existing standard for a vision prescription](https://build.fhir.org/visionprescription.html).

#### STEP 2 - Extract the prescription data from a text printout

We hope this will be a temporary requirement as opticians will move to printing out QR codes containing structured data.

We used two methods - the Tesseract library and asking Gemini to process an image.

#### STEP 4 - Display the structured data in a personal wallet.

We worked through the process for displaying data in a Google Wallet using the provided APIs.

### Data Protection

Opticians will continue to have a copy of the prescriptions of all their customers.

Our model retains the control of the data in the hands of the recipient of the eye test as they decide whether to store their prescription in their wallet.

If the system were extended to an Optical Record in the NHS App, this would create some additional data protection considerations that would be an important part of the design process.

## The Future

We could make very rapid progress if the UK optician community were to do the following -

agree on the structured data standard for optical prescriptions /(FIHR has done the work so no reason to delay/)
tweak their systems to print a QR code alongside the text prescription /(simple and cheap using common, free libraries/).

Once recipients of eye tests have their prescriptions in an easily readable standards-based format then this opens up a lot of possibilities for how they can be used for their benefit.

- Opticians can use QR code readers to input a new client's prescription immediately making that transaction more efficient.
- Primary and secondary care services can similarly get immediate access to patient data, with their consent, in consultations where this is relevant.
- The NHS App could offer an Optical Record section as a new value-added feature that will help keep their service useful and relevant to people.

The simplest and quickest solution would be for the new approach to be adopted voluntarily, but the Government could also mandate this by updating the regulations so as to require QR code output as part of their contract with opticians.





