# Civic Leadership Assessment Specification

## Specification sections

1. Design Intent

2. Data Format
  - 2.1 Timestamp
  - 2.2 Overall Rating
  - 2.3 Actor Ranking
  - 2.4 Feedback
  - 2.5 Additional data

3. Implementation Suggestions

## 1. Design intent

Continuous survey data focused on local and regional civic affairs is valuable.

Engaging professional pollsters is too expensive for most civic organizations. Online tools are a cost-effective approach to tracking a community's "pulse" on civic topics. However, managing online communities for surveying can be time-consuming and require more resources than many community groups have available. Many of these groups would benefit from being able to conduct quick surveys with available free online tools (e.g. Google Forms, SurveyMonkey, etc.) without setting up identity management or database systems. This allows for inexpensive data-gathering and portability of data for on-going analysis.

This specification proposes a light data format for CSV files.  These CSV files contain the responses persisted by free survey tools. By creating a standard format, additional software application can be built to provide functionality that ensures data quality and automates visualization of the response results.

The format assumes that short, direct surveys increase completion rate. Additionally, the format opines that at least one longitudinal chart that tracks performance is a non-negotiable requirement to a quality survey project.

## 2. Data format

#### 2.1 Timestamp

The first column in a CLAS-compliant CSV must be a timestamp. It must follow the ISO 8601 representation format. This field can not be null.

#### 2.2 Overall Rating

The second column must be a non-zero, positive integer that reflects a rating on the organization or initiative that is the *subject* of the survey (e.g. an NGO, a public department, an elected body). The format is agnostic on the specific unit of the rating; however, it only requires and recommends one unit. This field may be null; a null value must be interpreted as a skipped answer.

#### 2.3 Actor Ranking

The third column in a CLAS-compliant CSV must be a string. An empty string is an acceptable value. This string is typically the name of a "leader" (e.g. a City Council member) or "initiative" or sub-organization of the main subject. These should be *the* most important actors in the organization or initiative that is the *subject* of the survey; they are who is most directly accountable for the overall rating from 2.2 above. The survey question for the column must be a request for a ranking, such as "Who is the most effective leader?". This field can be null; a null value must be interpreted as a skipped answer.

#### 2.4 Feedback

The fourth column in a CLAS-compliant CSV must be a string.  This is an open-ended request for feedback relevant to the survey subject. This field can be null; a null value must be interpreted as empty feedback.

#### 2.5 Additional data

A CLAS-compliant CSV may have additional columns of data. There are no requirements for additional fields.

## 3. Implementation suggestions

These are not requirements but should be considered as "best practice" by applications working with the specification's data format.

**First Row**. The first row should include the column names. If possible, column names should use an 'underscore' format and be all lower-case characters.

**Adapters**. CSVs may have the required columns but in the wrong order; your application should consider creating a 'transformation' step; these should be referred to as 'adapter' functions/classes, etc.
