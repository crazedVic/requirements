Get Survey Config: 

https://beta.preterra.com/api/afar/surveys/{CODE}

Response:
```
{
    "status": "success",
    "message": "Successfully retrieved config for customer FD255",
    "data": {
        "id": 58,
        "team_id": 55,
        "app": "Trace",
        "code": "FD255",
        "name": "Fluik Entertainment Inc",
        "filename": "fd255.json",
        "email_positive": "victor@fluik.com",
        "email_negative": "victor@fluik.com",
        "email_summary": "victor@fluik.com",
        "contact_name": "Victor Fluik",
        "contact_number": "(780) 707-7393",
        "required": [
            "phone",
            "full_name",
            "first",
            "last",
            "child",
            "email"
        ],
        "report_fields": [
            "full_name"
        ],
        "theme_color": "0xFF2366CC",
        "logo_url": "https://s3.amazonaws.com/execrentals-east/Trace/default.png",
        "languages": [
            "en"
        ],
        "sms_verify": 1,
        "enabled": 1,
        "meta_contact": {
            "isoCode": "CA",
            "dialCode": "",
            "phone_number": "(780) 707-7393"
        },
        "questions": [
            "Do you have a fever greater than 38°C / 100.4°F ?",
            "Are you experiencing a new onset of (or exacerbation of chronic) cough?",
            "Do you have shortness of breath?",
            "Are you having difficulty breathing?",
            "Do you have a sore throat?",
            "Do you have a runny nose?",
            "Have you returned home from outside the country in the past 14 days?",
            "Do you live with or have had **close contact** (within 2 meters/6 feet) with a person with an influenza-like illness (ILI) who had travelled outside the country in the 14 days before the illness started, while:\\n  \t1) not wearing recommended PPE at work and/or  \t\\n2) not practicing social distancing as appropriate to the setting?",
            "Do you live with or have had **close contact** (within 2 meters/6 feet) with a person with an influenza-like illness (ILI) who had close contact with a lab-confirmed COVID-19 case, while: \\n \\n1) not wearing recommended PPE and/or \\n \\n2) not practicing social distancing as appropriate to the setting?",
            "Have you had **close contact** (within 2 meters/6 feet) with a confirmed or probable case of COVID-19, while: \\n \\n1) not wearing recommended PPE and/or \\n \\n2) not practicing social distancing?"
        ],
        "strings": {
            "intro": "The information collected in this screening questionnaire will be used and disclosed solely for the purpose of determining fitness for work during the COVID-19 pandemic in accordance with government guidelines to provide a safe environment for our staff, contractors and patients. Questions regarding the collection, use and disclosure of information contained in this form may be directed to info@domain.com or (555) 555-5555. \\n \\nWe require you to complete this online questionnaire to assist us in determining your fitness to enter the premises, and to provide your consent in having us test and record your temperature. \\n \\nWhile on the premises, please ensure you are following protocols for hand hygiene at all times, and remember to clean your keys, phone, computers and other personal items regularly. \\n \\nWe understand that you may have seasonal or environmental allergies. Symptoms related to these scenarios would not preclude you from work. Screening questions are meant to capture NEW symptoms, or a worsening of long-standing symptoms. ",
            "submit": "By clicking SUBMIT and submitting this questionnaire, you agree that all the information you have provided is true and accurate to the best of your knowledge.",
            "yes_response": "PLEASE NOTE:\\n\\n BASED ON YOUR SUBMITTED ANSWERS, YOU ARE NOT CLEARED TO ENTER THE PREMISES.\\n\\nPLEASE CONTACT US AT\\n(555) 555-5555.",
            "no_response": "PLEASE NOTE:\\n\\n BASED ON YOUR SUBMITTED ANSWERS, YOU ARE CLEARED TO CONTINUE.  PLEASE WAIT FOR US TO CALL YOU IN BY PHONE.",
            "title": "COVID-19 Patient Screening Questionnaire"
        },
        "valid_subs": true
    }
}
```

POST Twilio Request:

https://beta.preterra.com/api/twilio/request

Body:
```
{
    "phone_number": "+1555555555",
    "method": "sms_test",
    "app": "Trace"
}
```
Response:
```
{
    "status": "success",
    "message": "test call / sms sent",
    "data": {
        "status": "pending"
    }
}
```
POST Twilio Verify Request:

https://beta.preterra.com/api/twilio/verify

Body:
```
{
    "pin": "999999",
    "phone_number": "+1555555555",
    "app": "Trace"
}
```
Response:
```
{
    "status": "success",
    "message": "pin sent for verification",
    "data": true
}
```
POST submit survey:
https://beta.preterra.com/api/afar/results

Body:
```
{
  "id": 39,
  "type": "Staff",
  "full_name": "Victor Rubba",
  "first": "Victor",
  "last": "Rubba",
  "child": "Sandray",
  "email": "ed@ed.com",
  "phone": "+1 (412) 341-2341",
  "appointment_date": "",
  "time": "14:06:22",
  "no": [
    "Do you have a fever greater than 38°C / 100.4°F ?",
    "Are you experiencing a new onset of (or exacerbation of chronic) cough?",
    "Do you have shortness of breath?",
    "Are you having difficulty breathing?",
    "Do you have a sore throat?",
    "Do you have a runny nose?",
    "Have you returned home from outside the country in the past 14 days?",
    "Do you live with or have had **close contact** (within 2 meters/6 feet) with a person with an influenza-like illness (ILI) who had travelled outside the country in the 14 days before the illness started, while:\n  \t1) not wearing recommended PPE at work and/or  \t\n2) not practicing social distancing as appropriate to the setting?",
    "Do you live with or have had **close contact** (within 2 meters/6 feet) with a person with an influenza-like illness (ILI) who had close contact with a lab-confirmed COVID-19 case, while: \n \n1) not wearing recommended PPE and/or \n \n2) not practicing social distancing as appropriate to the setting?",
    "Have you had **close contact** (within 2 meters/6 feet) with a confirmed or probable case of COVID-19, while: \n \n1) not wearing recommended PPE and/or \n \n2) not practicing social distancing?",
    "Do you have a fever greater than 38°C / 100.4°F ?",
    "Are you experiencing a new onset of (or exacerbation of chronic) cough?",
    "Do you have shortness of breath?",
    "Are you having difficulty breathing?",
    "Do you have a sore throat?",
    "Do you have a runny nose?",
    "Have you returned home from outside the country in the past 14 days?",
    "Do you live with or have had **close contact** (within 2 meters/6 feet) with a person with an influenza-like illness (ILI) who had travelled outside the country in the 14 days before the illness started, while:\n  \t1) not wearing recommended PPE at work and/or  \t\n2) not practicing social distancing as appropriate to the setting?",
    "Do you live with or have had **close contact** (within 2 meters/6 feet) with a person with an influenza-like illness (ILI) who had close contact with a lab-confirmed COVID-19 case, while: \n \n1) not wearing recommended PPE and/or \n \n2) not practicing social distancing as appropriate to the setting?",
    "Have you had **close contact** (within 2 meters/6 feet) with a confirmed or probable case of COVID-19, while: \n \n1) not wearing recommended PPE and/or \n \n2) not practicing social distancing?",
    "Do you have a fever greater than 38°C / 100.4°F ?",
    "Are you experiencing a new onset of (or exacerbation of chronic) cough?",
    "Do you have shortness of breath?",
    "Are you having difficulty breathing?",
    "Do you have a sore throat?",
    "Do you have a runny nose?",
    "Have you returned home from outside the country in the past 14 days?",
    "Do you live with or have had **close contact** (within 2 meters/6 feet) with a person with an influenza-like illness (ILI) who had travelled outside the country in the 14 days before the illness started, while:\n  \t1) not wearing recommended PPE at work and/or  \t\n2) not practicing social distancing as appropriate to the setting?",
    "Do you live with or have had **close contact** (within 2 meters/6 feet) with a person with an influenza-like illness (ILI) who had close contact with a lab-confirmed COVID-19 case, while: \n \n1) not wearing recommended PPE and/or \n \n2) not practicing social distancing as appropriate to the setting?",
    "Have you had **close contact** (within 2 meters/6 feet) with a confirmed or probable case of COVID-19, while: \n \n1) not wearing recommended PPE and/or \n \n2) not practicing social distancing?",
    "Do you have a fever greater than 38°C / 100.4°F ?",
    "Are you experiencing a new onset of (or exacerbation of chronic) cough?",
    "Do you have shortness of breath?",
    "Are you having difficulty breathing?",
    "Do you have a sore throat?",
    "Do you have a runny nose?",
    "Have you returned home from outside the country in the past 14 days?",
    "Do you live with or have had **close contact** (within 2 meters/6 feet) with a person with an influenza-like illness (ILI) who had travelled outside the country in the 14 days before the illness started, while:\n  \t1) not wearing recommended PPE at work and/or  \t\n2) not practicing social distancing as appropriate to the setting?",
    "Do you live with or have had **close contact** (within 2 meters/6 feet) with a person with an influenza-like illness (ILI) who had close contact with a lab-confirmed COVID-19 case, while: \n \n1) not wearing recommended PPE and/or \n \n2) not practicing social distancing as appropriate to the setting?",
    "Have you had **close contact** (within 2 meters/6 feet) with a confirmed or probable case of COVID-19, while: \n \n1) not wearing recommended PPE and/or \n \n2) not practicing social distancing?"
  ],
  "yes": []
}
```

Response:
```
{
    "status": "success",
    "message": "Submission emailed successfully",
    "data": {
        "id": 39,
        "type": "Staff",
        "full_name": "Victor Rubba",
        "first": "Victor",
        "last": "Rubba",
        "child": "Sandray",
        "email": "ed@ed.com",
        "phone": "+1 (412) 341-2341",
        "appointment_date": "",
        "time": "14:06:22",
        "no": [
            "Do you have a fever greater than 38°C / 100.4°F ?",
            "Are you experiencing a new onset of (or exacerbation of chronic) cough?",
            "Do you have shortness of breath?",
            "Are you having difficulty breathing?",
            "Do you have a sore throat?",
            "Do you have a runny nose?",
            "Have you returned home from outside the country in the past 14 days?",
            "Do you live with or have had **close contact** (within 2 meters/6 feet) with a person with an influenza-like illness (ILI) who had travelled outside the country in the 14 days before the illness started, while:\n  \t1) not wearing recommended PPE at work and/or  \t\n2) not practicing social distancing as appropriate to the setting?",
            "Do you live with or have had **close contact** (within 2 meters/6 feet) with a person with an influenza-like illness (ILI) who had close contact with a lab-confirmed COVID-19 case, while: \n \n1) not wearing recommended PPE and/or \n \n2) not practicing social distancing as appropriate to the setting?",
            "Have you had **close contact** (within 2 meters/6 feet) with a confirmed or probable case of COVID-19, while: \n \n1) not wearing recommended PPE and/or \n \n2) not practicing social distancing?",
            "Do you have a fever greater than 38°C / 100.4°F ?",
            "Are you experiencing a new onset of (or exacerbation of chronic) cough?",
            "Do you have shortness of breath?",
            "Are you having difficulty breathing?",
            "Do you have a sore throat?",
            "Do you have a runny nose?",
            "Have you returned home from outside the country in the past 14 days?",
            "Do you live with or have had **close contact** (within 2 meters/6 feet) with a person with an influenza-like illness (ILI) who had travelled outside the country in the 14 days before the illness started, while:\n  \t1) not wearing recommended PPE at work and/or  \t\n2) not practicing social distancing as appropriate to the setting?",
            "Do you live with or have had **close contact** (within 2 meters/6 feet) with a person with an influenza-like illness (ILI) who had close contact with a lab-confirmed COVID-19 case, while: \n \n1) not wearing recommended PPE and/or \n \n2) not practicing social distancing as appropriate to the setting?",
            "Have you had **close contact** (within 2 meters/6 feet) with a confirmed or probable case of COVID-19, while: \n \n1) not wearing recommended PPE and/or \n \n2) not practicing social distancing?",
            "Do you have a fever greater than 38°C / 100.4°F ?",
            "Are you experiencing a new onset of (or exacerbation of chronic) cough?",
            "Do you have shortness of breath?",
            "Are you having difficulty breathing?",
            "Do you have a sore throat?",
            "Do you have a runny nose?",
            "Have you returned home from outside the country in the past 14 days?",
            "Do you live with or have had **close contact** (within 2 meters/6 feet) with a person with an influenza-like illness (ILI) who had travelled outside the country in the 14 days before the illness started, while:\n  \t1) not wearing recommended PPE at work and/or  \t\n2) not practicing social distancing as appropriate to the setting?",
            "Do you live with or have had **close contact** (within 2 meters/6 feet) with a person with an influenza-like illness (ILI) who had close contact with a lab-confirmed COVID-19 case, while: \n \n1) not wearing recommended PPE and/or \n \n2) not practicing social distancing as appropriate to the setting?",
            "Have you had **close contact** (within 2 meters/6 feet) with a confirmed or probable case of COVID-19, while: \n \n1) not wearing recommended PPE and/or \n \n2) not practicing social distancing?",
            "Do you have a fever greater than 38°C / 100.4°F ?",
            "Are you experiencing a new onset of (or exacerbation of chronic) cough?",
            "Do you have shortness of breath?",
            "Are you having difficulty breathing?",
            "Do you have a sore throat?",
            "Do you have a runny nose?",
            "Have you returned home from outside the country in the past 14 days?",
            "Do you live with or have had **close contact** (within 2 meters/6 feet) with a person with an influenza-like illness (ILI) who had travelled outside the country in the 14 days before the illness started, while:\n  \t1) not wearing recommended PPE at work and/or  \t\n2) not practicing social distancing as appropriate to the setting?",
            "Do you live with or have had **close contact** (within 2 meters/6 feet) with a person with an influenza-like illness (ILI) who had close contact with a lab-confirmed COVID-19 case, while: \n \n1) not wearing recommended PPE and/or \n \n2) not practicing social distancing as appropriate to the setting?",
            "Have you had **close contact** (within 2 meters/6 feet) with a confirmed or probable case of COVID-19, while: \n \n1) not wearing recommended PPE and/or \n \n2) not practicing social distancing?"
        ],
        "yes": []
    }
}
```
