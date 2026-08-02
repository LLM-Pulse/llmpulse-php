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


$apiInstance = new LLMPulse\Api\AIModelInsightsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$range = 56; // int | Number of days to look back (alternative to from/to)
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$granularity = 'granularity_example'; // string
$collection_id = 56; // int
$country_code = 'country_code_example'; // string | ISO country code (e.g. US, GB, DE)
$language_code = 'language_code_example'; // string | ISO language code (e.g. en, es, de)
$prompt_type = 'prompt_type_example'; // string | Filter by prompt type (search intent)
$brand_kind = 'brand_kind_example'; // string | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
$competitors = 'competitors_example'; // string | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)

try {
    $apiInstance->getAiModelInsightsSummary($project_id, $range, $from, $to, $granularity, $collection_id, $country_code, $language_code, $prompt_type, $brand_kind, $competitors);
} catch (Exception $e) {
    echo 'Exception when calling AIModelInsightsApi->getAiModelInsightsSummary: ', $e->getMessage(), PHP_EOL;
}

```

## API Endpoints

All URIs are relative to *https://api.llmpulse.ai/api/v1*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AIModelInsightsApi* | [**getAiModelInsightsSummary**](docs/Api/AIModelInsightsApi.md#getaimodelinsightssummary) | **GET** /reports/ai_model_insights/summary | AI Model Insights summary
*AIModelInsightsApi* | [**getAiModelPositionDistribution**](docs/Api/AIModelInsightsApi.md#getaimodelpositiondistribution) | **GET** /reports/ai_model_insights/position_distribution | Position distribution comparison
*AIModelInsightsApi* | [**getAiOverviewResults**](docs/Api/AIModelInsightsApi.md#getaioverviewresults) | **GET** /reports/ai_model_insights/ai_overview_results | Google AI Overview result availability
*AnnotationsApi* | [**createAnnotation**](docs/Api/AnnotationsApi.md#createannotation) | **POST** /annotations | Create a timeline annotation
*AnnotationsApi* | [**deleteAnnotation**](docs/Api/AnnotationsApi.md#deleteannotation) | **DELETE** /annotations/{id} | Delete a timeline annotation
*AnnotationsApi* | [**listAnnotations**](docs/Api/AnnotationsApi.md#listannotations) | **GET** /annotations | List timeline annotations
*AnnotationsApi* | [**updateAnnotation**](docs/Api/AnnotationsApi.md#updateannotation) | **PATCH** /annotations/{id} | Update a timeline annotation
*AnswersApi* | [**getAnswer**](docs/Api/AnswersApi.md#getanswer) | **GET** /answers/{id} | Get one AI response
*AnswersApi* | [**listAnswers**](docs/Api/AnswersApi.md#listanswers) | **GET** /answers | List AI responses
*CitationIntelligenceApi* | [**getCitedUrlContent**](docs/Api/CitationIntelligenceApi.md#getcitedurlcontent) | **GET** /citation_intelligence/urls/{url_sha256}/content | Cited URL cached content
*CitationIntelligenceApi* | [**getCitedUrlDetail**](docs/Api/CitationIntelligenceApi.md#getcitedurldetail) | **GET** /citation_intelligence/urls/{url_sha256} | Cited URL detail
*CitationIntelligenceApi* | [**getMentionsByCitingDomain**](docs/Api/CitationIntelligenceApi.md#getmentionsbycitingdomain) | **GET** /citation_intelligence/mentions_by_domain | Mention share by citing domain
*CitationIntelligenceApi* | [**listCitationGroups**](docs/Api/CitationIntelligenceApi.md#listcitationgroups) | **GET** /citation_intelligence/groups | Grouped citation intelligence
*CitationIntelligenceApi* | [**listCitedUrlOccurrences**](docs/Api/CitationIntelligenceApi.md#listcitedurloccurrences) | **GET** /citation_intelligence/urls/{url_sha256}/occurrences | Cited URL occurrences
*CollectionsApi* | [**createCollection**](docs/Api/CollectionsApi.md#createcollection) | **POST** /collections | Create a tag
*CollectionsApi* | [**deleteCollection**](docs/Api/CollectionsApi.md#deletecollection) | **DELETE** /collections/{id} | Delete a tag
*CollectionsApi* | [**updateCollection**](docs/Api/CollectionsApi.md#updatecollection) | **PATCH** /collections/{id} | Update a tag
*CompetitorsApi* | [**createCompetitor**](docs/Api/CompetitorsApi.md#createcompetitor) | **POST** /competitors | Add a competitor
*CompetitorsApi* | [**deleteCompetitor**](docs/Api/CompetitorsApi.md#deletecompetitor) | **DELETE** /competitors/{id} | Delete a competitor
*CompetitorsApi* | [**updateCompetitor**](docs/Api/CompetitorsApi.md#updatecompetitor) | **PATCH** /competitors/{id} | Update a competitor
*DimensionsApi* | [**getCompetitorDetails**](docs/Api/DimensionsApi.md#getcompetitordetails) | **GET** /dimensions/competitors/{id} | Competitor details
*DimensionsApi* | [**getProjectDetails**](docs/Api/DimensionsApi.md#getprojectdetails) | **GET** /dimensions/projects/{id} | Project details
*DimensionsApi* | [**listAgentBots**](docs/Api/DimensionsApi.md#listagentbots) | **GET** /dimensions/agent_bots | AI bot catalog (Scale+)
*DimensionsApi* | [**listAllCitations**](docs/Api/DimensionsApi.md#listallcitations) | **GET** /dimensions/all_citations | List all citations (brand + competitor)
*DimensionsApi* | [**listAllMentions**](docs/Api/DimensionsApi.md#listallmentions) | **GET** /dimensions/all_mentions | List all mentions (brand + competitor)
*DimensionsApi* | [**listCitations**](docs/Api/DimensionsApi.md#listcitations) | **GET** /dimensions/citations | List brand citations
*DimensionsApi* | [**listCollections**](docs/Api/DimensionsApi.md#listcollections) | **GET** /dimensions/collections | List tags/collections
*DimensionsApi* | [**listCompetitorCitations**](docs/Api/DimensionsApi.md#listcompetitorcitations) | **GET** /dimensions/competitor_citations | List competitor citations
*DimensionsApi* | [**listCompetitorMentions**](docs/Api/DimensionsApi.md#listcompetitormentions) | **GET** /dimensions/competitor_mentions | List competitor mentions
*DimensionsApi* | [**listCompetitors**](docs/Api/DimensionsApi.md#listcompetitors) | **GET** /dimensions/competitors | List competitors
*DimensionsApi* | [**listLocales**](docs/Api/DimensionsApi.md#listlocales) | **GET** /dimensions/locales | List locales with data
*DimensionsApi* | [**listMentions**](docs/Api/DimensionsApi.md#listmentions) | **GET** /dimensions/mentions | List brand mentions
*DimensionsApi* | [**listModels**](docs/Api/DimensionsApi.md#listmodels) | **GET** /dimensions/models | List models with data
*DimensionsApi* | [**listProjects**](docs/Api/DimensionsApi.md#listprojects) | **GET** /dimensions/projects | List projects
*DimensionsApi* | [**listPromptExecutions**](docs/Api/DimensionsApi.md#listpromptexecutions) | **GET** /dimensions/prompt_executions | List prompt executions
*DimensionsApi* | [**listPrompts**](docs/Api/DimensionsApi.md#listprompts) | **GET** /dimensions/prompts | List prompts
*DimensionsApi* | [**listSentimentCategories**](docs/Api/DimensionsApi.md#listsentimentcategories) | **GET** /dimensions/sentiments | List sentiment categories
*DimensionsApi* | [**listSources**](docs/Api/DimensionsApi.md#listsources) | **GET** /dimensions/sources | List source URLs
*DimensionsApi* | [**listTags**](docs/Api/DimensionsApi.md#listtags) | **GET** /dimensions/tags | List tags (alias for /collections)
*GEOWriterApi* | [**createIntelligenceTask**](docs/Api/GEOWriterApi.md#createintelligencetask) | **POST** /intelligence_tasks | Create a GEO Writer task
*GEOWriterApi* | [**getIntelligenceTask**](docs/Api/GEOWriterApi.md#getintelligencetask) | **GET** /intelligence_tasks/{id} | Get a GEO Writer task
*GEOWriterApi* | [**listIntelligenceTasks**](docs/Api/GEOWriterApi.md#listintelligencetasks) | **GET** /intelligence_tasks | List GEO Writer tasks
*HealthApi* | [**ping**](docs/Api/HealthApi.md#ping) | **GET** /ping | Health check
*MetricsApi* | [**getAgentTraffic**](docs/Api/MetricsApi.md#getagenttraffic) | **GET** /metrics/agent_traffic | AI bot crawler traffic (Scale+, Beta)
*MetricsApi* | [**getAiTraffic**](docs/Api/MetricsApi.md#getaitraffic) | **GET** /metrics/ai_traffic | AI referral traffic (Scale+)
*MetricsApi* | [**getPromptSummary**](docs/Api/MetricsApi.md#getpromptsummary) | **GET** /metrics/prompt_summary | Per-prompt metrics summary
*MetricsApi* | [**getShareOfVoice**](docs/Api/MetricsApi.md#getshareofvoice) | **GET** /metrics/sov | Share of Voice
*MetricsApi* | [**getSummary**](docs/Api/MetricsApi.md#getsummary) | **GET** /metrics/summary | Aggregated metrics summary
*MetricsApi* | [**getTimeseries**](docs/Api/MetricsApi.md#gettimeseries) | **GET** /metrics/timeseries | Time-series metrics
*MetricsApi* | [**getTopSources**](docs/Api/MetricsApi.md#gettopsources) | **GET** /metrics/top_sources | Top cited sources
*ProjectsApi* | [**createProject**](docs/Api/ProjectsApi.md#createproject) | **POST** /projects | Create a project (fast mode)
*ProjectsApi* | [**createProjectDraft**](docs/Api/ProjectsApi.md#createprojectdraft) | **POST** /project_drafts | Start a project draft (wizard step 1)
*ProjectsApi* | [**finalizeProjectDraft**](docs/Api/ProjectsApi.md#finalizeprojectdraft) | **POST** /project_drafts/{id}/finalize | Finalize a draft into a real project
*ProjectsApi* | [**getProjectDraft**](docs/Api/ProjectsApi.md#getprojectdraft) | **GET** /project_drafts/{id} | Read a project draft
*ProjectsApi* | [**updateProjectDraft**](docs/Api/ProjectsApi.md#updateprojectdraft) | **PATCH** /project_drafts/{id} | Submit a wizard step
*PromptsApi* | [**assignPromptTags**](docs/Api/PromptsApi.md#assignprompttags) | **POST** /prompts/assign_tags | Bulk-attach tags to prompts
*PromptsApi* | [**createPrompts**](docs/Api/PromptsApi.md#createprompts) | **POST** /prompts | Bulk-create prompts
*PromptsApi* | [**deletePrompt**](docs/Api/PromptsApi.md#deleteprompt) | **DELETE** /prompts/{id} | Delete a prompt
*RecommendationsApi* | [**getRecommendation**](docs/Api/RecommendationsApi.md#getrecommendation) | **GET** /recommendations/{id} | Get recommendation run with items
*RecommendationsApi* | [**launchRecommendations**](docs/Api/RecommendationsApi.md#launchrecommendations) | **POST** /recommendations | Launch a recommendations generation
*RecommendationsApi* | [**listRecommendations**](docs/Api/RecommendationsApi.md#listrecommendations) | **GET** /recommendations | List recommendation runs
*ReportsApi* | [**createTechnicalGeoReports**](docs/Api/ReportsApi.md#createtechnicalgeoreports) | **POST** /technical_geo_reports | Run technical GEO analysis
*SearchConsoleApi* | [**getSearchConsolePages**](docs/Api/SearchConsoleApi.md#getsearchconsolepages) | **GET** /search_console/pages | Top Search Console pages (Growth+)
*SearchConsoleApi* | [**getSearchConsoleQueries**](docs/Api/SearchConsoleApi.md#getsearchconsolequeries) | **GET** /search_console/queries | Top Search Console queries (Growth+)
*SearchConsoleApi* | [**getSearchConsoleSummary**](docs/Api/SearchConsoleApi.md#getsearchconsolesummary) | **GET** /search_console/summary | Search Console summary (Growth+)
*SearchConsoleApi* | [**getSearchConsoleTimeseries**](docs/Api/SearchConsoleApi.md#getsearchconsoletimeseries) | **GET** /search_console/timeseries | Search Console time series (Growth+)
*SentimentsApi* | [**listSentimentRecords**](docs/Api/SentimentsApi.md#listsentimentrecords) | **GET** /sentiments | List sentiment records
*WebhooksApi* | [**createWebhook**](docs/Api/WebhooksApi.md#createwebhook) | **POST** /webhooks | Create a webhook subscription
*WebhooksApi* | [**deleteWebhook**](docs/Api/WebhooksApi.md#deletewebhook) | **DELETE** /webhooks/{id} | Delete a webhook subscription
*WebhooksApi* | [**listWebhooks**](docs/Api/WebhooksApi.md#listwebhooks) | **GET** /webhooks | List webhook subscriptions
*WebhooksApi* | [**sampleWebhookPayloads**](docs/Api/WebhooksApi.md#samplewebhookpayloads) | **GET** /webhooks/sample/{event_type} | Sample event payloads

## Models

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
- [IntelligenceTask](docs/Model/IntelligenceTask.md)
- [IntelligenceTaskCreateRequest](docs/Model/IntelligenceTaskCreateRequest.md)
- [LaunchRecommendationsRequest](docs/Model/LaunchRecommendationsRequest.md)
- [ListCompetitors200Response](docs/Model/ListCompetitors200Response.md)
- [ListProjects200Response](docs/Model/ListProjects200Response.md)
- [ListWebhooks200Response](docs/Model/ListWebhooks200Response.md)
- [ListWebhooks200ResponseDataInner](docs/Model/ListWebhooks200ResponseDataInner.md)
- [Ping200Response](docs/Model/Ping200Response.md)
- [Project](docs/Model/Project.md)
- [ProjectCreateRequest](docs/Model/ProjectCreateRequest.md)
- [ProjectCreateRequestCompetitorsInner](docs/Model/ProjectCreateRequestCompetitorsInner.md)
- [ProjectCreateRequestOwnedMedia](docs/Model/ProjectCreateRequestOwnedMedia.md)
- [ProjectCreateResponse](docs/Model/ProjectCreateResponse.md)
- [ProjectCreateResponseCompetitors](docs/Model/ProjectCreateResponseCompetitors.md)
- [ProjectCreateResponseEmailSubscription](docs/Model/ProjectCreateResponseEmailSubscription.md)
- [ProjectCreateResponseLimits](docs/Model/ProjectCreateResponseLimits.md)
- [ProjectCreateResponsePrompts](docs/Model/ProjectCreateResponsePrompts.md)
- [ProjectDetails](docs/Model/ProjectDetails.md)
- [ProjectDetailsAllOfStats](docs/Model/ProjectDetailsAllOfStats.md)
- [PromptSummaryResponse](docs/Model/PromptSummaryResponse.md)
- [PromptSummaryRow](docs/Model/PromptSummaryRow.md)
- [PromptsCreateRequest](docs/Model/PromptsCreateRequest.md)
- [PromptsCreateResponse](docs/Model/PromptsCreateResponse.md)
- [PromptsCreateResponseDataInner](docs/Model/PromptsCreateResponseDataInner.md)
- [SampleWebhookPayloads200Response](docs/Model/SampleWebhookPayloads200Response.md)
- [SampleWebhookPayloads200ResponseDataInner](docs/Model/SampleWebhookPayloads200ResponseDataInner.md)
- [SovResponse](docs/Model/SovResponse.md)
- [SovResponseBreakdownInner](docs/Model/SovResponseBreakdownInner.md)
- [SovResponseCurrentInner](docs/Model/SovResponseCurrentInner.md)
- [SovResponseOverTimeInner](docs/Model/SovResponseOverTimeInner.md)
- [SovResponsePeriodsInner](docs/Model/SovResponsePeriodsInner.md)
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

- API version: `1.22.0`
    - Generator version: `7.24.0`
- Build package: `org.openapitools.codegen.languages.PhpClientCodegen`
