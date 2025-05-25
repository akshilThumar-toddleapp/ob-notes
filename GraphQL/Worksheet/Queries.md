# Worksheet GraphQL Queries

#graphql #query #worksheet-module

## Overview

- **File Path**: `src/AppComponents/Worksheet/modules/WorksheetQueries.js`
- **Purpose**: Contains GraphQL queries used throughout the Worksheet module
- **Last Updated**: May 2025

## Key Queries

### getAssessmentQuestionsQuery

Fetches questions for a specific worksheet assessment.

```graphql
query getAssessmentQuestions($id: ID!, $submissionId: ID) {
  node(id: $id, type: ORG_RESOURCE) {
    id
    ... on OrganizationResource {
      id
      sections {
        id
        title
        questions {
          ...questionItem
        }
      }
    }
  }
}
```

### getStudentAssignmentQuestionSubmissionsQuery

Retrieves a student's submitted answers for a worksheet.

### getSchoolQuestionLibraryFeedQuery

Fetches questions from the school's question library.

### getToddleQuestionLibraryFeedQuery

Retrieves questions from the Toddle platform question library.

## Usage Patterns

Queries in the Worksheet module typically follow these patterns:

1. Fetch worksheet structure and questions
2. Retrieve student submissions
3. Get question libraries for adding questions
4. Fetch media attachments and resources

## Dependencies

- [[WorksheetFragments]] - GraphQL fragments used in queries
- [[questionItem]] - Core fragment for question data
- [[attachmentItem]] - Fragment for media attachments

## Related Files

- [[WorksheetMutations]] - GraphQL mutations for the module
- [[WorksheetUtils]] - Helper functions for query variables

## Tags

#graphql #query #worksheet #data-fetching
