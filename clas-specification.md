# Civic Leadership Assessment Specification

## Specification sections

1. Design Intent

2. Data Format

2.1 Timestamp
2.2 Overall Rating
2.3 Leader Ranking
2.4 Feedback
2.5 Additional data

3. Implementation Suggestions

## 1. Design intent

Continuous survey data in local and regional civic affairs is valuable. However, engaging professional pollsters can be to expensive for most civic organizations. On the other hand, managing online communities for surveying can be time-consuming.  As a result, many groups would benefit from being able to conduct quick surveys with available free online tools (e.g. Google Forms, SurveyMonkey, etc.) without setting up identity management or database systems. This allows for inexpensive data-gathering and portability of data for on-going analysis.

This specification proposes a light data format for CSV files.  These CSV files are the direct result of free survey tools or a simple transformation of said results. proved around which applications can be built. Tools can target functionality such as data quality and reporting.

The format assumes that fewer, direct questions increase completion rate. Additionally, the format has the opinion that at least one longitudinal chart that tracks performance is a non-negotiable requirement to a quality survey project. The specification sees human leaders are key actors in civic affairs. Open-ended feedback is valuable for gathering  To summarize, the data format opines that a focused set of time series data points about leadership performance coupled

## 2. Data Format

#### 2.1 Timestamp

The first column in a CLAS-compliant CSV must be a timestamp. It must follow the ISO 8601 representation format. This field can not be null.

#### 2.2 Overall Rating

The second column must be a number that reflects a rating on the subject of the survey (e.g. an NGO, a public department, an elected body). The format is agnostic on the specific unit of the rating; however, it only requires and recommends one unit. This field may be null; a null value must be interpreted as a skipped answer.

#### 2.3 Actor Ranking

The third column in a CLAS-compliant CSV must be a string. An empty string is an acceptable value. This string is typically the name of a "leader" (e.g. a City Council member) or "initiative" or sub-organization of the main subject. These should be *the* most important actors in the subject; they are who is most directly accountable for the overall rating from 2.3 above. The survey question for the column must be a request for a ranking, such as "Who is the most effective leader?". This field can be null; a null value must be interpreted as a skipped answer.

#### 2.4 Feedback

The fourth column in a CLAS-compliant CSV must be a string.  This is an open-ended request for feedback relevant to the survey subject. This field can be null; a null value must be interpreted as empty feedback.

#### 2.5 Additional Data

A CLAS-compliant CSV may have additional columns of data. There are no requirements for additional fields.


