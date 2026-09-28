# LLMPulse

REST API client for LLM Pulse AI visibility analytics.

For more information, please visit [https://llmpulse.ai](https://llmpulse.ai).

## Installation & Usage

### Requirements

PHP 8.1 and later.

### Composer

To install the bindings via [Composer](https://getcomposer.org/), add the following to `composer.json`:

```json
{
  "repositories": [
    {
      "type": "vcs",
      "url": "https://github.com/LLM-Pulse/llmpulse-php.git"
    }
  ],
  "require": {
    "LLM-Pulse/llmpulse-php": "*@dev"
  }
}
```

Then run `composer install`

### Manual Installation

Download the files and include `autoload.php`:

```php
<?php
require_once('/path/to/LLMPulse/vendor/autoload.php');
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\AIAgentTrafficApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$range = 56; // int | Number of days to look back (alternative to from/to)
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
$bot = 'bot_example'; // string | Filter by bot slug (e.g. gptbot, claudebot, perplexitybot)
$company = 'company_example'; // string | Filter by company (e.g. openai, anthropic, google)
$group_by = 'bot'; // string
$granularity = 'granularity_example'; // string

try {
    $result = $apiInstance->getAgentTraffic($project_id, $range, $from, $to, $bot, $company, $group_by, $granularity);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AIAgentTrafficApi->getAgentTraffic: ', $e->getMessage(), PHP_EOL;
}

```

## API Endpoints

All URIs are relative to *https://api.llmpulse.ai/api/v1*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AIAgentTrafficApi* | [**getAgentTraffic**](docs/Api/AIAgentTrafficApi.md#getagenttraffic) | **GET** /metrics/agent_traffic | AI bot crawler traffic (Scale plan or above, Beta)
*AIAgentTrafficApi* | [**getAiTraffic**](docs/Api/AIAgentTrafficApi.md#getaitraffic) | **GET** /metrics/ai_traffic | AI referral traffic (Scale plan or above)
*AIAgentTrafficApi* | [**listAgentBots**](docs/Api/AIAgentTrafficApi.md#listagentbots) | **GET** /dimensions/agent_bots | AI bot catalog (Scale plan or above)
*AIModelInsightsApi* | [**getAiModelInsightsSummary**](docs/Api/AIModelInsightsApi.md#getaimodelinsightssummary) | **GET** /reports/ai_model_insights/summary | AI Model Insights summary
*AIModelInsightsApi* | [**getAiModelPositionDistribution**](docs/Api/AIModelInsightsApi.md#getaimodelpositiondistribution) | **GET** /reports/ai_model_insights/position_distribution | Position distribution comparison
*AIModelInsightsApi* | [**getAiOverviewResults**](docs/Api/AIModelInsightsApi.md#getaioverviewresults) | **GET** /reports/ai_model_insights/ai_overview_results | Google AI Overview result availability
*AccountApi* | [**getAccount**](docs/Api/AccountApi.md#getaccount) | **GET** /account | Account plan, quota usage and rate limits
*AnnotationsApi* | [**createAnnotation**](docs/Api/AnnotationsApi.md#createannotation) | **POST** /annotations | Create a timeline annotation
*AnnotationsApi* | [**deleteAnnotation**](docs/Api/AnnotationsApi.md#deleteannotation) | **DELETE** /annotations/{id} | Delete a timeline annotation
*AnnotationsApi* | [**listAnnotations**](docs/Api/AnnotationsApi.md#listannotations) | **GET** /annotations | List timeline annotations
*AnnotationsApi* | [**updateAnnotation**](docs/Api/AnnotationsApi.md#updateannotation) | **PATCH** /annotations/{id} | Update a timeline annotation
*AnswersApi* | [**getAnswer**](docs/Api/AnswersApi.md#getanswer) | **GET** /answers/{id} | Get one AI response
*AnswersApi* | [**listAnswers**](docs/Api/AnswersApi.md#listanswers) | **GET** /answers | List AI responses
*CollectionsTagsApi* | [**assignPromptTags**](docs/Api/CollectionsTagsApi.md#assignprompttags) | **POST** /prompts/assign_tags | Bulk-attach tags to prompts
*CollectionsTagsApi* | [**createCollection**](docs/Api/CollectionsTagsApi.md#createcollection) | **POST** /collections | Create a tag
*CollectionsTagsApi* | [**deleteCollection**](docs/Api/CollectionsTagsApi.md#deletecollection) | **DELETE** /collections/{id} | Delete a tag
*CollectionsTagsApi* | [**listCollections**](docs/Api/CollectionsTagsApi.md#listcollections) | **GET** /dimensions/collections | List tags/collections
*CollectionsTagsApi* | [**listTags**](docs/Api/CollectionsTagsApi.md#listtags) | **GET** /dimensions/tags | List tags (alias for /collections)
*CollectionsTagsApi* | [**updateCollection**](docs/Api/CollectionsTagsApi.md#updatecollection) | **PATCH** /collections/{id} | Update a tag
*CompetitorsApi* | [**createCompetitor**](docs/Api/CompetitorsApi.md#createcompetitor) | **POST** /competitors | Add a competitor
*CompetitorsApi* | [**deleteCompetitor**](docs/Api/CompetitorsApi.md#deletecompetitor) | **DELETE** /competitors/{id} | Delete a competitor
*CompetitorsApi* | [**getCompetitorDetails**](docs/Api/CompetitorsApi.md#getcompetitordetails) | **GET** /dimensions/competitors/{id} | Competitor details
*CompetitorsApi* | [**listCompetitors**](docs/Api/CompetitorsApi.md#listcompetitors) | **GET** /dimensions/competitors | List competitors
*CompetitorsApi* | [**updateCompetitor**](docs/Api/CompetitorsApi.md#updatecompetitor) | **PATCH** /competitors/{id} | Update a competitor
*GEOWriterApi* | [**createIntelligenceTask**](docs/Api/GEOWriterApi.md#createintelligencetask) | **POST** /intelligence_tasks | Create a GEO Writer task
*GEOWriterApi* | [**getIntelligenceTask**](docs/Api/GEOWriterApi.md#getintelligencetask) | **GET** /intelligence_tasks/{id} | Get a GEO Writer task
*GEOWriterApi* | [**listIntelligenceTasks**](docs/Api/GEOWriterApi.md#listintelligencetasks) | **GET** /intelligence_tasks | List GEO Writer tasks
*GEOWriterApi* | [**revertIntelligenceTaskContent**](docs/Api/GEOWriterApi.md#revertintelligencetaskcontent) | **POST** /intelligence_tasks/{id}/revert | Revert GEO Writer task content
*GEOWriterApi* | [**updateIntelligenceTaskContent**](docs/Api/GEOWriterApi.md#updateintelligencetaskcontent) | **PATCH** /intelligence_tasks/{id} | Edit GEO Writer task content
*HealthApi* | [**ping**](docs/Api/HealthApi.md#ping) | **GET** /ping | Health check
*MentionsCitationsApi* | [**listAllCitations**](docs/Api/MentionsCitationsApi.md#listallcitations) | **GET** /dimensions/all_citations | List all citations (brand + competitor)
*MentionsCitationsApi* | [**listAllMentions**](docs/Api/MentionsCitationsApi.md#listallmentions) | **GET** /dimensions/all_mentions | List all mentions (brand + competitor)
*MentionsCitationsApi* | [**listCitations**](docs/Api/MentionsCitationsApi.md#listcitations) | **GET** /dimensions/citations | List brand citations
*MentionsCitationsApi* | [**listCompetitorCitations**](docs/Api/MentionsCitationsApi.md#listcompetitorcitations) | **GET** /dimensions/competitor_citations | List competitor citations
*MentionsCitationsApi* | [**listCompetitorMentions**](docs/Api/MentionsCitationsApi.md#listcompetitormentions) | **GET** /dimensions/competitor_mentions | List competitor mentions
*MentionsCitationsApi* | [**listMentions**](docs/Api/MentionsCitationsApi.md#listmentions) | **GET** /dimensions/mentions | List brand mentions
*MetricsApi* | [**getPromptSummary**](docs/Api/MetricsApi.md#getpromptsummary) | **GET** /metrics/prompt_summary | Per-prompt metrics summary
*MetricsApi* | [**getShareOfVoice**](docs/Api/MetricsApi.md#getshareofvoice) | **GET** /metrics/sov | Share of Voice
*MetricsApi* | [**getSummary**](docs/Api/MetricsApi.md#getsummary) | **GET** /metrics/summary | Aggregated metrics summary
*MetricsApi* | [**getTimeseries**](docs/Api/MetricsApi.md#gettimeseries) | **GET** /metrics/timeseries | Time-series metrics
*MetricsApi* | [**getTopSources**](docs/Api/MetricsApi.md#gettopsources) | **GET** /metrics/top_sources | Top cited sources
*OwnedMediaCommunitiesApi* | [**listOwnedMedia**](docs/Api/OwnedMediaCommunitiesApi.md#listownedmedia) | **GET** /dimensions/owned_media | List owned-media citations
*OwnedMediaCommunitiesApi* | [**listRedditCitations**](docs/Api/OwnedMediaCommunitiesApi.md#listredditcitations) | **GET** /dimensions/reddit | List cited Reddit content
*ProjectsApi* | [**createProject**](docs/Api/ProjectsApi.md#createproject) | **POST** /projects | Create a project (fast mode)
*ProjectsApi* | [**createProjectDraft**](docs/Api/ProjectsApi.md#createprojectdraft) | **POST** /project_drafts | Start a project draft (wizard step 1)
*ProjectsApi* | [**finalizeProjectDraft**](docs/Api/ProjectsApi.md#finalizeprojectdraft) | **POST** /project_drafts/{id}/finalize | Finalize a draft into a real project
*ProjectsApi* | [**getProjectDetails**](docs/Api/ProjectsApi.md#getprojectdetails) | **GET** /dimensions/projects/{id} | Project details
*ProjectsApi* | [**getProjectDraft**](docs/Api/ProjectsApi.md#getprojectdraft) | **GET** /project_drafts/{id} | Read a project draft
*ProjectsApi* | [**listLocales**](docs/Api/ProjectsApi.md#listlocales) | **GET** /dimensions/locales | List locales with data
*ProjectsApi* | [**listModels**](docs/Api/ProjectsApi.md#listmodels) | **GET** /dimensions/models | List models with data
*ProjectsApi* | [**listProjects**](docs/Api/ProjectsApi.md#listprojects) | **GET** /dimensions/projects | List projects
*ProjectsApi* | [**updateProject**](docs/Api/ProjectsApi.md#updateproject) | **PATCH** /projects/{id} | Update a project profile (Brand Book)
*ProjectsApi* | [**updateProjectDraft**](docs/Api/ProjectsApi.md#updateprojectdraft) | **PATCH** /project_drafts/{id} | Submit a wizard step
*PromptsApi* | [**createPrompts**](docs/Api/PromptsApi.md#createprompts) | **POST** /prompts | Bulk-create prompts
*PromptsApi* | [**deletePrompt**](docs/Api/PromptsApi.md#deleteprompt) | **DELETE** /prompts/{id} | Delete a prompt
*PromptsApi* | [**listPromptExecutions**](docs/Api/PromptsApi.md#listpromptexecutions) | **GET** /dimensions/prompt_executions | List prompt executions
*PromptsApi* | [**listPrompts**](docs/Api/PromptsApi.md#listprompts) | **GET** /dimensions/prompts | List prompts
*PromptsApi* | [**listQueryFanOuts**](docs/Api/PromptsApi.md#listqueryfanouts) | **GET** /dimensions/query_fan_outs | List query fan-out
*RecommendationsApi* | [**getRecommendation**](docs/Api/RecommendationsApi.md#getrecommendation) | **GET** /recommendations/{id} | Get recommendation run with items
*RecommendationsApi* | [**launchRecommendations**](docs/Api/RecommendationsApi.md#launchrecommendations) | **POST** /recommendations | Launch a recommendations generation
*RecommendationsApi* | [**listRecommendations**](docs/Api/RecommendationsApi.md#listrecommendations) | **GET** /recommendations | List recommendation runs
*ReputationStudiesApi* | [**getReputationReport**](docs/Api/ReputationStudiesApi.md#getreputationreport) | **GET** /reputation/reports/{id} | Get reputation report scores
*ReputationStudiesApi* | [**getStudy**](docs/Api/ReputationStudiesApi.md#getstudy) | **GET** /studies/{id} | Get a custom AI study
*ReputationStudiesApi* | [**getStudyReport**](docs/Api/ReputationStudiesApi.md#getstudyreport) | **GET** /studies/{id}/reports/{report_id} | Get custom study report scores
*ReputationStudiesApi* | [**listReputationReports**](docs/Api/ReputationStudiesApi.md#listreputationreports) | **GET** /reputation/reports | List reputation reports
*ReputationStudiesApi* | [**listStudies**](docs/Api/ReputationStudiesApi.md#liststudies) | **GET** /studies | List custom AI studies
*SearchConsoleApi* | [**getSearchConsolePages**](docs/Api/SearchConsoleApi.md#getsearchconsolepages) | **GET** /search_console/pages | Top Search Console pages (Growth+)
*SearchConsoleApi* | [**getSearchConsoleQueries**](docs/Api/SearchConsoleApi.md#getsearchconsolequeries) | **GET** /search_console/queries | Top Search Console queries (Growth+)
*SearchConsoleApi* | [**getSearchConsoleSummary**](docs/Api/SearchConsoleApi.md#getsearchconsolesummary) | **GET** /search_console/summary | Search Console summary (Growth+)
*SearchConsoleApi* | [**getSearchConsoleTimeseries**](docs/Api/SearchConsoleApi.md#getsearchconsoletimeseries) | **GET** /search_console/timeseries | Search Console time series (Growth+)
*SentimentsApi* | [**listSentimentCategories**](docs/Api/SentimentsApi.md#listsentimentcategories) | **GET** /dimensions/sentiments | List sentiment categories
*SentimentsApi* | [**listSentimentRecords**](docs/Api/SentimentsApi.md#listsentimentrecords) | **GET** /sentiments | List sentiment records
*ShoppingAdsApi* | [**listAds**](docs/Api/ShoppingAdsApi.md#listads) | **GET** /dimensions/ads | List AI ad placements
*ShoppingAdsApi* | [**listShopping**](docs/Api/ShoppingAdsApi.md#listshopping) | **GET** /dimensions/shopping | List shopping results
*SourcesCitationIntelligenceApi* | [**getCitedUrlContent**](docs/Api/SourcesCitationIntelligenceApi.md#getcitedurlcontent) | **GET** /citation_intelligence/urls/{url_sha256}/content | Cited URL cached content
*SourcesCitationIntelligenceApi* | [**getCitedUrlDetail**](docs/Api/SourcesCitationIntelligenceApi.md#getcitedurldetail) | **GET** /citation_intelligence/urls/{url_sha256} | Cited URL detail
*SourcesCitationIntelligenceApi* | [**getMentionsByCitingDomain**](docs/Api/SourcesCitationIntelligenceApi.md#getmentionsbycitingdomain) | **GET** /citation_intelligence/mentions_by_domain | Mention share by citing domain
*SourcesCitationIntelligenceApi* | [**listCitationGroups**](docs/Api/SourcesCitationIntelligenceApi.md#listcitationgroups) | **GET** /citation_intelligence/groups | Grouped citation intelligence
*SourcesCitationIntelligenceApi* | [**listCitedUrlOccurrences**](docs/Api/SourcesCitationIntelligenceApi.md#listcitedurloccurrences) | **GET** /citation_intelligence/urls/{url_sha256}/occurrences | Cited URL occurrences
*SourcesCitationIntelligenceApi* | [**listSources**](docs/Api/SourcesCitationIntelligenceApi.md#listsources) | **GET** /dimensions/sources | List source URLs
*TechnicalGEOReportsApi* | [**createTechnicalGeoReports**](docs/Api/TechnicalGEOReportsApi.md#createtechnicalgeoreports) | **POST** /technical_geo_reports | Run technical GEO analysis
*TechnicalGEOReportsApi* | [**getTechnicalGeoReport**](docs/Api/TechnicalGEOReportsApi.md#gettechnicalgeoreport) | **GET** /technical_geo_reports/{id} | Get a technical GEO report
*TechnicalGEOReportsApi* | [**listTechnicalGeoReports**](docs/Api/TechnicalGEOReportsApi.md#listtechnicalgeoreports) | **GET** /technical_geo_reports | List technical GEO reports
*WebhooksApi* | [**createWebhook**](docs/Api/WebhooksApi.md#createwebhook) | **POST** /webhooks | Create a webhook subscription
*WebhooksApi* | [**deleteWebhook**](docs/Api/WebhooksApi.md#deletewebhook) | **DELETE** /webhooks/{id} | Delete a webhook subscription
*WebhooksApi* | [**listWebhooks**](docs/Api/WebhooksApi.md#listwebhooks) | **GET** /webhooks | List webhook subscriptions
*WebhooksApi* | [**sampleWebhookPayloads**](docs/Api/WebhooksApi.md#samplewebhookpayloads) | **GET** /webhooks/sample/{event_type} | Sample event payloads

## Models

- [AccountCapacity](docs/Model/AccountCapacity.md)
- [AccountQuota](docs/Model/AccountQuota.md)
- [Actor](docs/Model/Actor.md)
- [AgentBot](docs/Model/AgentBot.md)
- [AgentBotsResponse](docs/Model/AgentBotsResponse.md)
- [AgentTrafficResponse](docs/Model/AgentTrafficResponse.md)
- [AnswerDetails](docs/Model/AnswerDetails.md)
- [AnswerDetailsLocale](docs/Model/AnswerDetailsLocale.md)
- [ApiError](docs/Model/ApiError.md)
- [ApiErrorError](docs/Model/ApiErrorError.md)
- [AssignPromptTagsRequest](docs/Model/AssignPromptTagsRequest.md)
- [Competitor](docs/Model/Competitor.md)
- [CompetitorDetails](docs/Model/CompetitorDetails.md)
- [CreateAnnotationRequest](docs/Model/CreateAnnotationRequest.md)
- [CreateCollectionRequest](docs/Model/CreateCollectionRequest.md)
- [CreateCompetitorRequest](docs/Model/CreateCompetitorRequest.md)
- [CreateProjectDraftRequest](docs/Model/CreateProjectDraftRequest.md)
- [CreateTechnicalGeoReportsRequest](docs/Model/CreateTechnicalGeoReportsRequest.md)
- [CreateWebhook201Response](docs/Model/CreateWebhook201Response.md)
- [CreateWebhookRequest](docs/Model/CreateWebhookRequest.md)
- [DeleteWebhook200Response](docs/Model/DeleteWebhook200Response.md)
- [FinalizeProjectDraftRequest](docs/Model/FinalizeProjectDraftRequest.md)
- [GetAccount200Response](docs/Model/GetAccount200Response.md)
- [GetAccount200ResponseLimits](docs/Model/GetAccount200ResponseLimits.md)
- [GetAccount200ResponseRateLimits](docs/Model/GetAccount200ResponseRateLimits.md)
- [GetAccount200ResponseSubscription](docs/Model/GetAccount200ResponseSubscription.md)
- [IntelligenceTask](docs/Model/IntelligenceTask.md)
- [IntelligenceTaskCreateRequest](docs/Model/IntelligenceTaskCreateRequest.md)
- [IntelligenceTaskUpdateRequest](docs/Model/IntelligenceTaskUpdateRequest.md)
- [IntelligenceTaskUpdateResponse](docs/Model/IntelligenceTaskUpdateResponse.md)
- [LaunchRecommendationsRequest](docs/Model/LaunchRecommendationsRequest.md)
- [ListCompetitors200Response](docs/Model/ListCompetitors200Response.md)
- [ListProjects200Response](docs/Model/ListProjects200Response.md)
- [ListWebhooks200Response](docs/Model/ListWebhooks200Response.md)
- [ListWebhooks200ResponseDataInner](docs/Model/ListWebhooks200ResponseDataInner.md)
- [Ping200Response](docs/Model/Ping200Response.md)
- [Project](docs/Model/Project.md)
- [ProjectCreateRequest](docs/Model/ProjectCreateRequest.md)
- [ProjectCreateRequestCollectionsInner](docs/Model/ProjectCreateRequestCollectionsInner.md)
- [ProjectCreateRequestCompetitorsInner](docs/Model/ProjectCreateRequestCompetitorsInner.md)
- [ProjectCreateRequestOwnedMedia](docs/Model/ProjectCreateRequestOwnedMedia.md)
- [ProjectCreateResponse](docs/Model/ProjectCreateResponse.md)
- [ProjectCreateResponseCollectionsInner](docs/Model/ProjectCreateResponseCollectionsInner.md)
- [ProjectCreateResponseCompetitors](docs/Model/ProjectCreateResponseCompetitors.md)
- [ProjectCreateResponseEmailSubscription](docs/Model/ProjectCreateResponseEmailSubscription.md)
- [ProjectCreateResponseLimits](docs/Model/ProjectCreateResponseLimits.md)
- [ProjectCreateResponsePrompts](docs/Model/ProjectCreateResponsePrompts.md)
- [ProjectCreateResponseSameDomainProjectsInner](docs/Model/ProjectCreateResponseSameDomainProjectsInner.md)
- [ProjectDetails](docs/Model/ProjectDetails.md)
- [ProjectDetailsAllOfStats](docs/Model/ProjectDetailsAllOfStats.md)
- [PromptSummaryResponse](docs/Model/PromptSummaryResponse.md)
- [PromptSummaryRow](docs/Model/PromptSummaryRow.md)
- [PromptsCreateRequest](docs/Model/PromptsCreateRequest.md)
- [PromptsCreateResponse](docs/Model/PromptsCreateResponse.md)
- [PromptsCreateResponseDataInner](docs/Model/PromptsCreateResponseDataInner.md)
- [SampleWebhookPayloads200Response](docs/Model/SampleWebhookPayloads200Response.md)
- [SampleWebhookPayloads200ResponseDataInner](docs/Model/SampleWebhookPayloads200ResponseDataInner.md)
- [SearchConsoleFiltersInner](docs/Model/SearchConsoleFiltersInner.md)
- [SovResponse](docs/Model/SovResponse.md)
- [SovResponseBreakdownInner](docs/Model/SovResponseBreakdownInner.md)
- [SovResponseCurrentInner](docs/Model/SovResponseCurrentInner.md)
- [SovResponseOverTimeInner](docs/Model/SovResponseOverTimeInner.md)
- [SovResponsePeriodsInner](docs/Model/SovResponsePeriodsInner.md)
- [SovResponseSample](docs/Model/SovResponseSample.md)
- [SummaryResponse](docs/Model/SummaryResponse.md)
- [SummaryResponseAllOfPositionDistribution](docs/Model/SummaryResponseAllOfPositionDistribution.md)
- [SummaryResponseAllOfSummaryValueInner](docs/Model/SummaryResponseAllOfSummaryValueInner.md)
- [TimeseriesPoint](docs/Model/TimeseriesPoint.md)
- [TimeseriesResponse](docs/Model/TimeseriesResponse.md)
- [TimeseriesSeries](docs/Model/TimeseriesSeries.md)
- [TopSourcesResponse](docs/Model/TopSourcesResponse.md)
- [TopSourcesResponseDataInner](docs/Model/TopSourcesResponseDataInner.md)
- [UpdateAnnotationRequest](docs/Model/UpdateAnnotationRequest.md)
- [UpdateCollectionRequest](docs/Model/UpdateCollectionRequest.md)
- [UpdateCompetitorRequest](docs/Model/UpdateCompetitorRequest.md)
- [UpdateProjectDraftRequest](docs/Model/UpdateProjectDraftRequest.md)
- [UpdateProjectRequest](docs/Model/UpdateProjectRequest.md)

## Authorization

Authentication schemes defined for the API:
### BearerAuth

- **Type**: Bearer authentication

## Tests

To run the tests, use:

```bash
composer install
vendor/bin/phpunit
```

## Author

info@llmpulse.ai

## About this package

This PHP package is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: `1.50.0`
    - Generator version: `7.24.0`
- Build package: `org.openapitools.codegen.languages.PhpClientCodegen`
