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
*AIAgentTrafficApi* | [**getWebAnalyticsSchema**](docs/Api/AIAgentTrafficApi.md#getwebanalyticsschema) | **GET** /web_analytics/schema | Web analytics query format (Growth+)
*AIAgentTrafficApi* | [**listAgentBots**](docs/Api/AIAgentTrafficApi.md#listagentbots) | **GET** /dimensions/agent_bots | AI bot catalog (Scale plan or above)
*AIAgentTrafficApi* | [**queryWebAnalytics**](docs/Api/AIAgentTrafficApi.md#querywebanalytics) | **POST** /web_analytics/query | Live web analytics query (Growth+)
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
*CollectionsTagsApi* | [**removePromptTags**](docs/Api/CollectionsTagsApi.md#removeprompttags) | **POST** /prompts/remove_tags | Bulk-detach tags from prompts
*CollectionsTagsApi* | [**updateCollection**](docs/Api/CollectionsTagsApi.md#updatecollection) | **PATCH** /collections/{id} | Update a tag
*CompetitorsApi* | [**createCompetitor**](docs/Api/CompetitorsApi.md#createcompetitor) | **POST** /competitors | Add a competitor
*CompetitorsApi* | [**deleteCompetitor**](docs/Api/CompetitorsApi.md#deletecompetitor) | **DELETE** /competitors/{id} | Delete a competitor
*CompetitorsApi* | [**getCompetitorDetails**](docs/Api/CompetitorsApi.md#getcompetitordetails) | **GET** /dimensions/competitors/{id} | Competitor details
*CompetitorsApi* | [**listCompetitorSuggestions**](docs/Api/CompetitorsApi.md#listcompetitorsuggestions) | **GET** /competitors/suggestions | List competitor suggestions
*CompetitorsApi* | [**listCompetitors**](docs/Api/CompetitorsApi.md#listcompetitors) | **GET** /dimensions/competitors | List competitors
*CompetitorsApi* | [**updateCompetitor**](docs/Api/CompetitorsApi.md#updatecompetitor) | **PATCH** /competitors/{id} | Update a competitor
*CustomReportsApi* | [**getCustomReport**](docs/Api/CustomReportsApi.md#getcustomreport) | **GET** /custom_reports/{id} | Get a custom report with its widget data
*CustomReportsApi* | [**listCustomReports**](docs/Api/CustomReportsApi.md#listcustomreports) | **GET** /custom_reports | List custom reports
*CustomReportsApi* | [**sendCustomReport**](docs/Api/CustomReportsApi.md#sendcustomreport) | **POST** /custom_reports/{id}/send | Send a custom report now
*GEOAuditsApi* | [**compareGeoAuditRuns**](docs/Api/GEOAuditsApi.md#comparegeoauditruns) | **GET** /geo_audits/{id}/comparison | Compare two GEO audit runs
*GEOAuditsApi* | [**createGeoAudits**](docs/Api/GEOAuditsApi.md#creategeoaudits) | **POST** /geo_audits | Create GEO audits
*GEOAuditsApi* | [**deleteGeoAudit**](docs/Api/GEOAuditsApi.md#deletegeoaudit) | **DELETE** /geo_audits/{id} | Delete (archive) a GEO audit
*GEOAuditsApi* | [**getGeoAudit**](docs/Api/GEOAuditsApi.md#getgeoaudit) | **GET** /geo_audits/{id} | Get a GEO audit
*GEOAuditsApi* | [**getGeoAuditRun**](docs/Api/GEOAuditsApi.md#getgeoauditrun) | **GET** /geo_audits/{geo_audit_id}/runs/{sequence} | Get a GEO audit run
*GEOAuditsApi* | [**listGeoAlerts**](docs/Api/GEOAuditsApi.md#listgeoalerts) | **GET** /geo_alerts | List GEO audit alerts
*GEOAuditsApi* | [**listGeoAuditFindings**](docs/Api/GEOAuditsApi.md#listgeoauditfindings) | **GET** /geo_audits/{geo_audit_id}/runs/{sequence}/findings | List the findings of a GEO audit run
*GEOAuditsApi* | [**listGeoAuditIssues**](docs/Api/GEOAuditsApi.md#listgeoauditissues) | **GET** /geo_audits/{geo_audit_id}/issues | List the issues of a GEO audit
*GEOAuditsApi* | [**listGeoAuditRuns**](docs/Api/GEOAuditsApi.md#listgeoauditruns) | **GET** /geo_audits/{geo_audit_id}/runs | List the runs of a GEO audit
*GEOAuditsApi* | [**listGeoAudits**](docs/Api/GEOAuditsApi.md#listgeoaudits) | **GET** /geo_audits | List GEO audits
*GEOAuditsApi* | [**runGeoAudit**](docs/Api/GEOAuditsApi.md#rungeoaudit) | **POST** /geo_audits/{geo_audit_id}/runs | Run a GEO audit now
*GEOAuditsApi* | [**updateGeoAudit**](docs/Api/GEOAuditsApi.md#updategeoaudit) | **PATCH** /geo_audits/{id} | Update a GEO audit
*GEOAuditsApi* | [**updateGeoAuditIssue**](docs/Api/GEOAuditsApi.md#updategeoauditissue) | **PATCH** /geo_audits/{geo_audit_id}/issues/{id} | Accept or reopen a GEO audit issue
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
*OwnedMediaCommunitiesApi* | [**getOwnedMediaProfiles**](docs/Api/OwnedMediaCommunitiesApi.md#getownedmediaprofiles) | **GET** /projects/{id}/owned_media | Get a project&#39;s owned-media profiles
*OwnedMediaCommunitiesApi* | [**getOwnedMediaSummary**](docs/Api/OwnedMediaCommunitiesApi.md#getownedmediasummary) | **GET** /dimensions/owned_media/summary | Get an owned-media summary
*OwnedMediaCommunitiesApi* | [**listOwnedMedia**](docs/Api/OwnedMediaCommunitiesApi.md#listownedmedia) | **GET** /dimensions/owned_media | List owned-media citations
*OwnedMediaCommunitiesApi* | [**listOwnedMediaCitingPrompts**](docs/Api/OwnedMediaCommunitiesApi.md#listownedmediacitingprompts) | **GET** /dimensions/owned_media/citing_prompts | List the answers citing an owned-media item
*OwnedMediaCommunitiesApi* | [**listRedditCitations**](docs/Api/OwnedMediaCommunitiesApi.md#listredditcitations) | **GET** /dimensions/reddit | List cited Reddit content
*OwnedMediaCommunitiesApi* | [**updateOwnedMediaProfiles**](docs/Api/OwnedMediaCommunitiesApi.md#updateownedmediaprofiles) | **PATCH** /projects/{id}/owned_media | Update a project&#39;s owned-media profiles
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
*PromptsApi* | [**acceptSuggestedPrompts**](docs/Api/PromptsApi.md#acceptsuggestedprompts) | **POST** /suggested_prompts/accept | Accept suggested prompts
*PromptsApi* | [**createPromptGeneration**](docs/Api/PromptsApi.md#createpromptgeneration) | **POST** /prompt_generations | Generate prompt suggestions
*PromptsApi* | [**createPrompts**](docs/Api/PromptsApi.md#createprompts) | **POST** /prompts | Bulk-create prompts
*PromptsApi* | [**deletePrompt**](docs/Api/PromptsApi.md#deleteprompt) | **DELETE** /prompts/{id} | Delete a prompt
*PromptsApi* | [**getPromptGeneration**](docs/Api/PromptsApi.md#getpromptgeneration) | **GET** /prompt_generations/{id} | Get a prompt generation run
*PromptsApi* | [**importPrompts**](docs/Api/PromptsApi.md#importprompts) | **POST** /prompts/import | Import prompts
*PromptsApi* | [**listPromptExecutions**](docs/Api/PromptsApi.md#listpromptexecutions) | **GET** /dimensions/prompt_executions | List prompt executions
*PromptsApi* | [**listPrompts**](docs/Api/PromptsApi.md#listprompts) | **GET** /dimensions/prompts | List prompts
*PromptsApi* | [**listQueryFanOuts**](docs/Api/PromptsApi.md#listqueryfanouts) | **GET** /dimensions/query_fan_outs | List query fan-out
*PromptsApi* | [**listSuggestedPrompts**](docs/Api/PromptsApi.md#listsuggestedprompts) | **GET** /suggested_prompts | List suggested prompts
*PromptsApi* | [**rejectSuggestedPrompts**](docs/Api/PromptsApi.md#rejectsuggestedprompts) | **POST** /suggested_prompts/reject | Reject suggested prompts
*PromptsApi* | [**updatePrompt**](docs/Api/PromptsApi.md#updateprompt) | **PATCH** /prompts/{id} | Edit a prompt&#39;s categorization
*RecommendationsApi* | [**getRecommendation**](docs/Api/RecommendationsApi.md#getrecommendation) | **GET** /recommendations/{id} | Get recommendation run with items
*RecommendationsApi* | [**launchRecommendations**](docs/Api/RecommendationsApi.md#launchrecommendations) | **POST** /recommendations | Launch a recommendations generation
*RecommendationsApi* | [**listRecommendations**](docs/Api/RecommendationsApi.md#listrecommendations) | **GET** /recommendations | List recommendation runs
*RecommendationsApi* | [**updateRecommendationItem**](docs/Api/RecommendationsApi.md#updaterecommendationitem) | **PATCH** /recommendations/{id}/items/{item_id} | Complete, archive or restore a recommendation item
*ReputationStudiesApi* | [**getReputationReport**](docs/Api/ReputationStudiesApi.md#getreputationreport) | **GET** /reputation/reports/{id} | Get reputation report scores
*ReputationStudiesApi* | [**getStudy**](docs/Api/ReputationStudiesApi.md#getstudy) | **GET** /studies/{id} | Get a custom AI study
*ReputationStudiesApi* | [**getStudyReport**](docs/Api/ReputationStudiesApi.md#getstudyreport) | **GET** /studies/{id}/reports/{report_id} | Get custom study report scores
*ReputationStudiesApi* | [**listReputationReports**](docs/Api/ReputationStudiesApi.md#listreputationreports) | **GET** /reputation/reports | List reputation reports
*ReputationStudiesApi* | [**listStudies**](docs/Api/ReputationStudiesApi.md#liststudies) | **GET** /studies | List custom AI studies
*SearchConsoleApi* | [**getSearchConsolePages**](docs/Api/SearchConsoleApi.md#getsearchconsolepages) | **GET** /search_console/pages | Top Search Console pages (Growth+)
*SearchConsoleApi* | [**getSearchConsoleQueries**](docs/Api/SearchConsoleApi.md#getsearchconsolequeries) | **GET** /search_console/queries | Top Search Console queries (Growth+)
*SearchConsoleApi* | [**getSearchConsoleRows**](docs/Api/SearchConsoleApi.md#getsearchconsolerows) | **GET** /search_console/rows | Search Console rows by several dimensions (Growth+)
*SearchConsoleApi* | [**getSearchConsoleSummary**](docs/Api/SearchConsoleApi.md#getsearchconsolesummary) | **GET** /search_console/summary | Search Console summary (Growth+)
*SearchConsoleApi* | [**getSearchConsoleTimeseries**](docs/Api/SearchConsoleApi.md#getsearchconsoletimeseries) | **GET** /search_console/timeseries | Search Console time series (Growth+)
*SearchConsoleApi* | [**listSearchConsoleProperties**](docs/Api/SearchConsoleApi.md#listsearchconsoleproperties) | **GET** /search_console/properties | List Search Console properties (Growth+)
*SentimentsApi* | [**getSentimentTags**](docs/Api/SentimentsApi.md#getsentimenttags) | **GET** /reports/sentiment/tags | Sentiment by tag (Growth plan or above)
*SentimentsApi* | [**getSentimentTopics**](docs/Api/SentimentsApi.md#getsentimenttopics) | **GET** /reports/sentiment/topics | Sentiment by topic (Growth plan or above)
*SentimentsApi* | [**listSentimentCategories**](docs/Api/SentimentsApi.md#listsentimentcategories) | **GET** /dimensions/sentiments | List sentiment categories (Growth plan or above)
*SentimentsApi* | [**listSentimentRecords**](docs/Api/SentimentsApi.md#listsentimentrecords) | **GET** /sentiments | List sentiment records (Growth plan or above)
*ShoppingAdsApi* | [**listAds**](docs/Api/ShoppingAdsApi.md#listads) | **GET** /dimensions/ads | List AI ad placements
*ShoppingAdsApi* | [**listLocalBusinesses**](docs/Api/ShoppingAdsApi.md#listlocalbusinesses) | **GET** /dimensions/local_businesses | List local businesses
*ShoppingAdsApi* | [**listShopping**](docs/Api/ShoppingAdsApi.md#listshopping) | **GET** /dimensions/shopping | List shopping results
*SourcesCitationIntelligenceApi* | [**getCitedUrlContent**](docs/Api/SourcesCitationIntelligenceApi.md#getcitedurlcontent) | **GET** /citation_intelligence/urls/{url_sha256}/content | Cited URL cached content
*SourcesCitationIntelligenceApi* | [**getCitedUrlDetail**](docs/Api/SourcesCitationIntelligenceApi.md#getcitedurldetail) | **GET** /citation_intelligence/urls/{url_sha256} | Cited URL detail
*SourcesCitationIntelligenceApi* | [**getMentionsByCitingDomain**](docs/Api/SourcesCitationIntelligenceApi.md#getmentionsbycitingdomain) | **GET** /citation_intelligence/mentions_by_domain | Mention share by citing domain
*SourcesCitationIntelligenceApi* | [**listCitationGroups**](docs/Api/SourcesCitationIntelligenceApi.md#listcitationgroups) | **GET** /citation_intelligence/groups | Grouped citation intelligence
*SourcesCitationIntelligenceApi* | [**listCitedUrlOccurrences**](docs/Api/SourcesCitationIntelligenceApi.md#listcitedurloccurrences) | **GET** /citation_intelligence/urls/{url_sha256}/occurrences | Cited URL occurrences
*SourcesCitationIntelligenceApi* | [**listSources**](docs/Api/SourcesCitationIntelligenceApi.md#listsources) | **GET** /dimensions/sources | List source URLs
*StoreIntegrationsApi* | [**acceptCatalogPromptSuggestions**](docs/Api/StoreIntegrationsApi.md#acceptcatalogpromptsuggestions) | **POST** /catalog_prompt_suggestions/accept | Accept catalog prompt suggestions
*StoreIntegrationsApi* | [**createCatalogPromptSuggestions**](docs/Api/StoreIntegrationsApi.md#createcatalogpromptsuggestions) | **POST** /catalog_prompt_suggestions | Suggest buyer prompts from catalog products
*StoreIntegrationsApi* | [**getStoreConnection**](docs/Api/StoreIntegrationsApi.md#getstoreconnection) | **GET** /store_connection | Match a store to a project
*StoreIntegrationsApi* | [**listAiOrders**](docs/Api/StoreIntegrationsApi.md#listaiorders) | **GET** /ai_orders | Read AI-referred store orders
*StoreIntegrationsApi* | [**listCatalogPromptSuggestions**](docs/Api/StoreIntegrationsApi.md#listcatalogpromptsuggestions) | **GET** /catalog_prompt_suggestions | List catalog prompt suggestions
*StoreIntegrationsApi* | [**rejectCatalogPromptSuggestions**](docs/Api/StoreIntegrationsApi.md#rejectcatalogpromptsuggestions) | **POST** /catalog_prompt_suggestions/reject | Reject catalog prompt suggestions
*StoreIntegrationsApi* | [**replaceAiOrders**](docs/Api/StoreIntegrationsApi.md#replaceaiorders) | **PUT** /ai_orders | Replace AI-referred store orders for a window
*TeamApi* | [**createTeamInvitation**](docs/Api/TeamApi.md#createteaminvitation) | **POST** /team_invitations | Invite a team member
*TeamApi* | [**listTeamInvitations**](docs/Api/TeamApi.md#listteaminvitations) | **GET** /team_invitations | List pending team invitations
*TeamApi* | [**listTeamMembers**](docs/Api/TeamApi.md#listteammembers) | **GET** /team_members | List team members
*TeamApi* | [**removeTeamMember**](docs/Api/TeamApi.md#removeteammember) | **DELETE** /team_members/{id} | Remove a team member
*TeamApi* | [**revokeTeamInvitation**](docs/Api/TeamApi.md#revoketeaminvitation) | **DELETE** /team_invitations/{id} | Revoke a pending team invitation
*TechnicalGEOReportsApi* | [**createTechnicalGeoReports**](docs/Api/TechnicalGEOReportsApi.md#createtechnicalgeoreports) | **POST** /technical_geo_reports | Run technical GEO analysis
*TechnicalGEOReportsApi* | [**getTechnicalGeoReport**](docs/Api/TechnicalGEOReportsApi.md#gettechnicalgeoreport) | **GET** /technical_geo_reports/{id} | Get a technical GEO report
*TechnicalGEOReportsApi* | [**listTechnicalGeoReports**](docs/Api/TechnicalGEOReportsApi.md#listtechnicalgeoreports) | **GET** /technical_geo_reports | List technical GEO reports
*TechnicalGEOReportsApi* | [**revertTechnicalGeoReportContent**](docs/Api/TechnicalGEOReportsApi.md#reverttechnicalgeoreportcontent) | **POST** /technical_geo_reports/{id}/revert_content | Revert llms.txt report content
*TechnicalGEOReportsApi* | [**updateTechnicalGeoReportContent**](docs/Api/TechnicalGEOReportsApi.md#updatetechnicalgeoreportcontent) | **PATCH** /technical_geo_reports/{id}/content | Edit llms.txt report content
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
- [AiOrdersResponse](docs/Model/AiOrdersResponse.md)
- [AiOrdersResponseBySourceInner](docs/Model/AiOrdersResponseBySourceInner.md)
- [AiOrdersResponseSeriesInner](docs/Model/AiOrdersResponseSeriesInner.md)
- [AiOrdersResponseTotals](docs/Model/AiOrdersResponseTotals.md)
- [AiOrdersUpdateRequest](docs/Model/AiOrdersUpdateRequest.md)
- [AiOrdersUpdateRequestDaysInner](docs/Model/AiOrdersUpdateRequestDaysInner.md)
- [AiOrdersUpdateResponse](docs/Model/AiOrdersUpdateResponse.md)
- [AnnotationCreateResponse](docs/Model/AnnotationCreateResponse.md)
- [AnnotationCreateResponseAnnotation](docs/Model/AnnotationCreateResponseAnnotation.md)
- [AnswerDetails](docs/Model/AnswerDetails.md)
- [AnswerDetailsLocale](docs/Model/AnswerDetailsLocale.md)
- [ApiError](docs/Model/ApiError.md)
- [ApiErrorError](docs/Model/ApiErrorError.md)
- [AssignPromptTagsRequest](docs/Model/AssignPromptTagsRequest.md)
- [CatalogProduct](docs/Model/CatalogProduct.md)
- [CatalogPromptSuggestion](docs/Model/CatalogPromptSuggestion.md)
- [CatalogPromptSuggestionIdsRequest](docs/Model/CatalogPromptSuggestionIdsRequest.md)
- [CatalogPromptSuggestionProduct](docs/Model/CatalogPromptSuggestionProduct.md)
- [CatalogPromptSuggestionsAcceptResponse](docs/Model/CatalogPromptSuggestionsAcceptResponse.md)
- [CatalogPromptSuggestionsAcceptResponseAcceptedInner](docs/Model/CatalogPromptSuggestionsAcceptResponseAcceptedInner.md)
- [CatalogPromptSuggestionsAcceptResponseSkippedInner](docs/Model/CatalogPromptSuggestionsAcceptResponseSkippedInner.md)
- [CatalogPromptSuggestionsCreateRequest](docs/Model/CatalogPromptSuggestionsCreateRequest.md)
- [CatalogPromptSuggestionsCreateResponse](docs/Model/CatalogPromptSuggestionsCreateResponse.md)
- [CatalogPromptSuggestionsRejectResponse](docs/Model/CatalogPromptSuggestionsRejectResponse.md)
- [CatalogPromptSuggestionsResponse](docs/Model/CatalogPromptSuggestionsResponse.md)
- [CitationMatchMode](docs/Model/CitationMatchMode.md)
- [CitationRecord](docs/Model/CitationRecord.md)
- [CitationsResponse](docs/Model/CitationsResponse.md)
- [CollectionCreateResponse](docs/Model/CollectionCreateResponse.md)
- [CollectionCreateResponseCollection](docs/Model/CollectionCreateResponseCollection.md)
- [CollectionsResponse](docs/Model/CollectionsResponse.md)
- [Competitor](docs/Model/Competitor.md)
- [CompetitorCreateResponse](docs/Model/CompetitorCreateResponse.md)
- [CompetitorCreateResponseCompetitor](docs/Model/CompetitorCreateResponseCompetitor.md)
- [CompetitorDetails](docs/Model/CompetitorDetails.md)
- [CompetitorDiscoveryState](docs/Model/CompetitorDiscoveryState.md)
- [CompetitorMentionRecord](docs/Model/CompetitorMentionRecord.md)
- [CompetitorMentionsResponse](docs/Model/CompetitorMentionsResponse.md)
- [CompetitorSuggestion](docs/Model/CompetitorSuggestion.md)
- [CompetitorSuggestionsResponse](docs/Model/CompetitorSuggestionsResponse.md)
- [CreateAnnotationRequest](docs/Model/CreateAnnotationRequest.md)
- [CreateCollectionRequest](docs/Model/CreateCollectionRequest.md)
- [CreateCompetitorRequest](docs/Model/CreateCompetitorRequest.md)
- [CreateProjectDraftRequest](docs/Model/CreateProjectDraftRequest.md)
- [CreateTeamInvitation201Response](docs/Model/CreateTeamInvitation201Response.md)
- [CreateTeamInvitationRequest](docs/Model/CreateTeamInvitationRequest.md)
- [CreateTechnicalGeoReportsRequest](docs/Model/CreateTechnicalGeoReportsRequest.md)
- [CreateWebhook201Response](docs/Model/CreateWebhook201Response.md)
- [CreateWebhookRequest](docs/Model/CreateWebhookRequest.md)
- [CustomReportBlock](docs/Model/CustomReportBlock.md)
- [CustomReportDateRange](docs/Model/CustomReportDateRange.md)
- [CustomReportDetailResponse](docs/Model/CustomReportDetailResponse.md)
- [CustomReportFilters](docs/Model/CustomReportFilters.md)
- [CustomReportSchedule](docs/Model/CustomReportSchedule.md)
- [CustomReportSendResponse](docs/Model/CustomReportSendResponse.md)
- [CustomReportSummary](docs/Model/CustomReportSummary.md)
- [CustomReportWidget](docs/Model/CustomReportWidget.md)
- [CustomReportWidgetRef](docs/Model/CustomReportWidgetRef.md)
- [CustomReportsResponse](docs/Model/CustomReportsResponse.md)
- [DeleteWebhook200Response](docs/Model/DeleteWebhook200Response.md)
- [FinalizeProjectDraftRequest](docs/Model/FinalizeProjectDraftRequest.md)
- [GeoAlert](docs/Model/GeoAlert.md)
- [GeoAlertEventsInner](docs/Model/GeoAlertEventsInner.md)
- [GeoAlertList](docs/Model/GeoAlertList.md)
- [GeoAudit](docs/Model/GeoAudit.md)
- [GeoAuditArchived](docs/Model/GeoAuditArchived.md)
- [GeoAuditComparison](docs/Model/GeoAuditComparison.md)
- [GeoAuditComparisonChangesInner](docs/Model/GeoAuditComparisonChangesInner.md)
- [GeoAuditCreateRequest](docs/Model/GeoAuditCreateRequest.md)
- [GeoAuditCreateResponse](docs/Model/GeoAuditCreateResponse.md)
- [GeoAuditFinding](docs/Model/GeoAuditFinding.md)
- [GeoAuditFindingList](docs/Model/GeoAuditFindingList.md)
- [GeoAuditIssue](docs/Model/GeoAuditIssue.md)
- [GeoAuditIssueList](docs/Model/GeoAuditIssueList.md)
- [GeoAuditIssueResponse](docs/Model/GeoAuditIssueResponse.md)
- [GeoAuditIssueUpdateRequest](docs/Model/GeoAuditIssueUpdateRequest.md)
- [GeoAuditList](docs/Model/GeoAuditList.md)
- [GeoAuditResponse](docs/Model/GeoAuditResponse.md)
- [GeoAuditRun](docs/Model/GeoAuditRun.md)
- [GeoAuditRunDetail](docs/Model/GeoAuditRunDetail.md)
- [GeoAuditRunList](docs/Model/GeoAuditRunList.md)
- [GeoAuditRunResponse](docs/Model/GeoAuditRunResponse.md)
- [GeoAuditSchedule](docs/Model/GeoAuditSchedule.md)
- [GeoAuditUpdateRequest](docs/Model/GeoAuditUpdateRequest.md)
- [GetAccount200Response](docs/Model/GetAccount200Response.md)
- [GetAccount200ResponseLimits](docs/Model/GetAccount200ResponseLimits.md)
- [GetAccount200ResponseRateLimits](docs/Model/GetAccount200ResponseRateLimits.md)
- [GetAccount200ResponseSubscription](docs/Model/GetAccount200ResponseSubscription.md)
- [IntelligenceTask](docs/Model/IntelligenceTask.md)
- [IntelligenceTaskCreateRequest](docs/Model/IntelligenceTaskCreateRequest.md)
- [IntelligenceTaskProduct](docs/Model/IntelligenceTaskProduct.md)
- [IntelligenceTaskProductImagesInner](docs/Model/IntelligenceTaskProductImagesInner.md)
- [IntelligenceTaskSummary](docs/Model/IntelligenceTaskSummary.md)
- [IntelligenceTaskUpdateRequest](docs/Model/IntelligenceTaskUpdateRequest.md)
- [IntelligenceTaskUpdateResponse](docs/Model/IntelligenceTaskUpdateResponse.md)
- [IntelligenceTasksResponse](docs/Model/IntelligenceTasksResponse.md)
- [LaunchRecommendationsRequest](docs/Model/LaunchRecommendationsRequest.md)
- [ListCompetitors200Response](docs/Model/ListCompetitors200Response.md)
- [ListProjects200Response](docs/Model/ListProjects200Response.md)
- [ListTeamInvitations200Response](docs/Model/ListTeamInvitations200Response.md)
- [ListTeamMembers200Response](docs/Model/ListTeamMembers200Response.md)
- [ListWebhooks200Response](docs/Model/ListWebhooks200Response.md)
- [ListWebhooks200ResponseDataInner](docs/Model/ListWebhooks200ResponseDataInner.md)
- [LlmsTxtTechnicalGeoReport](docs/Model/LlmsTxtTechnicalGeoReport.md)
- [LlmsTxtTechnicalGeoReportResultData](docs/Model/LlmsTxtTechnicalGeoReportResultData.md)
- [LocalBusiness](docs/Model/LocalBusiness.md)
- [LocalBusinessesResponse](docs/Model/LocalBusinessesResponse.md)
- [LocalBusinessesTotals](docs/Model/LocalBusinessesTotals.md)
- [LocalesResponse](docs/Model/LocalesResponse.md)
- [MentionRecord](docs/Model/MentionRecord.md)
- [MentionsResponse](docs/Model/MentionsResponse.md)
- [MetricsFiltersEcho](docs/Model/MetricsFiltersEcho.md)
- [ModelsResponse](docs/Model/ModelsResponse.md)
- [OwnedMediaAgeBucketShare](docs/Model/OwnedMediaAgeBucketShare.md)
- [OwnedMediaCitedItem](docs/Model/OwnedMediaCitedItem.md)
- [OwnedMediaCitedItemStats](docs/Model/OwnedMediaCitedItemStats.md)
- [OwnedMediaCitingAnswer](docs/Model/OwnedMediaCitingAnswer.md)
- [OwnedMediaCitingPromptsResponse](docs/Model/OwnedMediaCitingPromptsResponse.md)
- [OwnedMediaContentTypeShare](docs/Model/OwnedMediaContentTypeShare.md)
- [OwnedMediaCountryShare](docs/Model/OwnedMediaCountryShare.md)
- [OwnedMediaKpiChanges](docs/Model/OwnedMediaKpiChanges.md)
- [OwnedMediaKpis](docs/Model/OwnedMediaKpis.md)
- [OwnedMediaListResponse](docs/Model/OwnedMediaListResponse.md)
- [OwnedMediaModelShare](docs/Model/OwnedMediaModelShare.md)
- [OwnedMediaPlatformProfiles](docs/Model/OwnedMediaPlatformProfiles.md)
- [OwnedMediaPlatformRollup](docs/Model/OwnedMediaPlatformRollup.md)
- [OwnedMediaPlatformRollupWeeklyInner](docs/Model/OwnedMediaPlatformRollupWeeklyInner.md)
- [OwnedMediaProfile](docs/Model/OwnedMediaProfile.md)
- [OwnedMediaProfileSettings](docs/Model/OwnedMediaProfileSettings.md)
- [OwnedMediaProfilesResponse](docs/Model/OwnedMediaProfilesResponse.md)
- [OwnedMediaProfilesUpdateResponse](docs/Model/OwnedMediaProfilesUpdateResponse.md)
- [OwnedMediaRow](docs/Model/OwnedMediaRow.md)
- [OwnedMediaStoreTotals](docs/Model/OwnedMediaStoreTotals.md)
- [OwnedMediaSummaryResponse](docs/Model/OwnedMediaSummaryResponse.md)
- [OwnedMediaSummaryResponsePrevious](docs/Model/OwnedMediaSummaryResponsePrevious.md)
- [OwnedMediaWeek](docs/Model/OwnedMediaWeek.md)
- [PaginatedEnvelope](docs/Model/PaginatedEnvelope.md)
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
- [ProjectDetailsAllOfAgentTraffic](docs/Model/ProjectDetailsAllOfAgentTraffic.md)
- [ProjectDetailsAllOfAiTraffic](docs/Model/ProjectDetailsAllOfAiTraffic.md)
- [ProjectDetailsAllOfDataCoverage](docs/Model/ProjectDetailsAllOfDataCoverage.md)
- [ProjectDetailsAllOfSearchConsole](docs/Model/ProjectDetailsAllOfSearchConsole.md)
- [ProjectDetailsAllOfStats](docs/Model/ProjectDetailsAllOfStats.md)
- [ProjectDetailsAllOfStatsPromptsByBrandKind](docs/Model/ProjectDetailsAllOfStatsPromptsByBrandKind.md)
- [ProjectProfile](docs/Model/ProjectProfile.md)
- [ProjectUpdateResponse](docs/Model/ProjectUpdateResponse.md)
- [PromptCategorization](docs/Model/PromptCategorization.md)
- [PromptCategorizationResponse](docs/Model/PromptCategorizationResponse.md)
- [PromptExecutionRecord](docs/Model/PromptExecutionRecord.md)
- [PromptExecutionsResponse](docs/Model/PromptExecutionsResponse.md)
- [PromptGenerationRequest](docs/Model/PromptGenerationRequest.md)
- [PromptGenerationResponse](docs/Model/PromptGenerationResponse.md)
- [PromptGenerationResponseError](docs/Model/PromptGenerationResponseError.md)
- [PromptGenerationResponseParams](docs/Model/PromptGenerationResponseParams.md)
- [PromptRecord](docs/Model/PromptRecord.md)
- [PromptSummaryResponse](docs/Model/PromptSummaryResponse.md)
- [PromptSummaryRow](docs/Model/PromptSummaryRow.md)
- [PromptTagsAssignResponse](docs/Model/PromptTagsAssignResponse.md)
- [PromptTagsRemoveResponse](docs/Model/PromptTagsRemoveResponse.md)
- [PromptsCreateRequest](docs/Model/PromptsCreateRequest.md)
- [PromptsCreateResponse](docs/Model/PromptsCreateResponse.md)
- [PromptsCreateResponseDataInner](docs/Model/PromptsCreateResponseDataInner.md)
- [PromptsImportRequest](docs/Model/PromptsImportRequest.md)
- [PromptsImportRequestRowsInner](docs/Model/PromptsImportRequestRowsInner.md)
- [PromptsImportResponse](docs/Model/PromptsImportResponse.md)
- [PromptsImportResponseRowErrorsInner](docs/Model/PromptsImportResponseRowErrorsInner.md)
- [PromptsResponse](docs/Model/PromptsResponse.md)
- [QueryWebAnalyticsRequest](docs/Model/QueryWebAnalyticsRequest.md)
- [RecommendationItem](docs/Model/RecommendationItem.md)
- [RecommendationItemUpdateResponse](docs/Model/RecommendationItemUpdateResponse.md)
- [RecommendationSummary](docs/Model/RecommendationSummary.md)
- [RecommendationSummarySummary](docs/Model/RecommendationSummarySummary.md)
- [RecommendationsResponse](docs/Model/RecommendationsResponse.md)
- [RemovePromptTagsRequest](docs/Model/RemovePromptTagsRequest.md)
- [RemoveTeamMember200Response](docs/Model/RemoveTeamMember200Response.md)
- [RevokeTeamInvitation200Response](docs/Model/RevokeTeamInvitation200Response.md)
- [SampleWebhookPayloads200Response](docs/Model/SampleWebhookPayloads200Response.md)
- [SampleWebhookPayloads200ResponseDataInner](docs/Model/SampleWebhookPayloads200ResponseDataInner.md)
- [SearchConsoleExcludedProperty](docs/Model/SearchConsoleExcludedProperty.md)
- [SearchConsoleFiltersInner](docs/Model/SearchConsoleFiltersInner.md)
- [SearchConsoleListResponse](docs/Model/SearchConsoleListResponse.md)
- [SearchConsoleListResponseDataInner](docs/Model/SearchConsoleListResponseDataInner.md)
- [SearchConsoleMetrics](docs/Model/SearchConsoleMetrics.md)
- [SearchConsolePropertiesResponse](docs/Model/SearchConsolePropertiesResponse.md)
- [SearchConsolePropertiesResponseDataInner](docs/Model/SearchConsolePropertiesResponseDataInner.md)
- [SearchConsoleProperty](docs/Model/SearchConsoleProperty.md)
- [SearchConsolePropertyError](docs/Model/SearchConsolePropertyError.md)
- [SearchConsoleRowsResponse](docs/Model/SearchConsoleRowsResponse.md)
- [SearchConsoleRowsResponseDataInner](docs/Model/SearchConsoleRowsResponseDataInner.md)
- [SearchConsoleSummaryResponse](docs/Model/SearchConsoleSummaryResponse.md)
- [SearchConsoleSummaryResponseBreakdownInner](docs/Model/SearchConsoleSummaryResponseBreakdownInner.md)
- [SearchConsoleTimeseriesResponse](docs/Model/SearchConsoleTimeseriesResponse.md)
- [SearchConsoleTimeseriesResponseDataInner](docs/Model/SearchConsoleTimeseriesResponseDataInner.md)
- [SendCustomReportRequest](docs/Model/SendCustomReportRequest.md)
- [SentimentBreakdownBrand](docs/Model/SentimentBreakdownBrand.md)
- [SentimentBreakdownCounts](docs/Model/SentimentBreakdownCounts.md)
- [SentimentBreakdownEnvelope](docs/Model/SentimentBreakdownEnvelope.md)
- [SentimentRecord](docs/Model/SentimentRecord.md)
- [SentimentTagRow](docs/Model/SentimentTagRow.md)
- [SentimentTagsResponse](docs/Model/SentimentTagsResponse.md)
- [SentimentTopicRow](docs/Model/SentimentTopicRow.md)
- [SentimentTopicsResponse](docs/Model/SentimentTopicsResponse.md)
- [SentimentsResponse](docs/Model/SentimentsResponse.md)
- [SovResponse](docs/Model/SovResponse.md)
- [SovResponseBreakdownInner](docs/Model/SovResponseBreakdownInner.md)
- [SovResponseCurrentInner](docs/Model/SovResponseCurrentInner.md)
- [SovResponseOthersInner](docs/Model/SovResponseOthersInner.md)
- [SovResponseOverTimeInner](docs/Model/SovResponseOverTimeInner.md)
- [SovResponsePeriodsInner](docs/Model/SovResponsePeriodsInner.md)
- [SovResponseSample](docs/Model/SovResponseSample.md)
- [StoreConnectionResponse](docs/Model/StoreConnectionResponse.md)
- [StoreConnectionResponseAccount](docs/Model/StoreConnectionResponseAccount.md)
- [StoreConnectionResponseCandidatesInner](docs/Model/StoreConnectionResponseCandidatesInner.md)
- [StoreConnectionResponseProject](docs/Model/StoreConnectionResponseProject.md)
- [SuggestedPrompt](docs/Model/SuggestedPrompt.md)
- [SuggestedPromptIdsRequest](docs/Model/SuggestedPromptIdsRequest.md)
- [SuggestedPromptsAcceptRequest](docs/Model/SuggestedPromptsAcceptRequest.md)
- [SuggestedPromptsAcceptResponse](docs/Model/SuggestedPromptsAcceptResponse.md)
- [SuggestedPromptsAcceptResponseAcceptedInner](docs/Model/SuggestedPromptsAcceptResponseAcceptedInner.md)
- [SuggestedPromptsRejectResponse](docs/Model/SuggestedPromptsRejectResponse.md)
- [SuggestedPromptsResponse](docs/Model/SuggestedPromptsResponse.md)
- [SummaryResponse](docs/Model/SummaryResponse.md)
- [SummaryResponseAllOfPositionDistribution](docs/Model/SummaryResponseAllOfPositionDistribution.md)
- [SummaryResponseAllOfSummaryValueInner](docs/Model/SummaryResponseAllOfSummaryValueInner.md)
- [TagRef](docs/Model/TagRef.md)
- [TeamAccountRole](docs/Model/TeamAccountRole.md)
- [TeamInvitation](docs/Model/TeamInvitation.md)
- [TeamMember](docs/Model/TeamMember.md)
- [TechnicalGeoReportContentRevertRequest](docs/Model/TechnicalGeoReportContentRevertRequest.md)
- [TechnicalGeoReportContentUpdateRequest](docs/Model/TechnicalGeoReportContentUpdateRequest.md)
- [TechnicalGeoReportContentUpdateRequestEdits](docs/Model/TechnicalGeoReportContentUpdateRequestEdits.md)
- [TechnicalGeoReportContentUpdateResponse](docs/Model/TechnicalGeoReportContentUpdateResponse.md)
- [TimeseriesPoint](docs/Model/TimeseriesPoint.md)
- [TimeseriesResponse](docs/Model/TimeseriesResponse.md)
- [TimeseriesSeries](docs/Model/TimeseriesSeries.md)
- [TopSourcesResponse](docs/Model/TopSourcesResponse.md)
- [TopSourcesResponseDataInner](docs/Model/TopSourcesResponseDataInner.md)
- [UpdateAnnotationRequest](docs/Model/UpdateAnnotationRequest.md)
- [UpdateCollectionRequest](docs/Model/UpdateCollectionRequest.md)
- [UpdateCompetitorRequest](docs/Model/UpdateCompetitorRequest.md)
- [UpdateOwnedMediaProfilesRequest](docs/Model/UpdateOwnedMediaProfilesRequest.md)
- [UpdateProjectDraftRequest](docs/Model/UpdateProjectDraftRequest.md)
- [UpdateProjectRequest](docs/Model/UpdateProjectRequest.md)
- [UpdatePromptRequest](docs/Model/UpdatePromptRequest.md)
- [UpdateRecommendationItemRequest](docs/Model/UpdateRecommendationItemRequest.md)
- [WebAnalyticsQueryResponse](docs/Model/WebAnalyticsQueryResponse.md)
- [WebAnalyticsQueryResponseColumnsInner](docs/Model/WebAnalyticsQueryResponseColumnsInner.md)
- [WebAnalyticsSchemaResponse](docs/Model/WebAnalyticsSchemaResponse.md)

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

- API version: `1.68.0`
    - Generator version: `7.24.0`
- Build package: `org.openapitools.codegen.languages.PhpClientCodegen`
