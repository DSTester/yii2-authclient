Yii Framework 2 authclient extension Change Log
===============================================

2.2.18 under development
------------------------

- Bug #393: Fix type for `BaseOAuth` property - `accessToken` (max-s-lab)


2.2.17 February 13, 2025
------------------------

- Bug #392: Now using array as default value for `token_endpoint_auth_methods_supported` in `OpenIdConnect::applyClientCredentialsToRequest()` (strtob, rhertogh)


2.2.16 May 10, 2024
-------------------

- Enh #387: Use appropriate exception if client does not exist (eluhr)
- Enh #388: Added support to configure the OAuth2 access token location in requests and added a generic OAuth2 client (rhertogh)
- Enh #389: Added ability to configure OpenIdConnect cache duration, default is 1 week (viktorprogger)


2.2.15 December 16, 2023
------------------------

- Enh GHSA-w8vh-p74j-x9xp: Improved security for OAuth1, OAuth2 and OpenID Connect clients by using timing attack safe string comparsion (rhertogh)
- Enh GHSA-rw54-6826-c8j5: Improved security for OAuth2 client by requiring an `authCodeVerifier` if PKCE is enabled and clearing it after usage (rhertogh)
- Bug #364: Use issuer claim from OpenID Configuration (radwouters)
- Enh #367: Throw more specific `ClientErrorResponseException` when the response code in `BaseOAuth::sendRequest()` is a 4xx (rhertogh)


2.2.14 November 18, 2022
------------------------

- Bug #351: Unable to set TokenParamKey in OAuth2 config, gets hard overwritten in OAuth2::createToken() (DSTester)


2.2.13 September 04, 2022
-------------------------

- Bug #354: Fix PHP 8.1 deprecated message in BaseOAuth `stripos(): Passing null to parameter #1 ($haystack) of type string is deprecated` (marty-macfly)


2.2.12 December 03, 2021
------------------------

- Bug #330: OpenID Connect client now defaults to `'client_secret_basic'` in case `token_endpoint_auth_methods_supported` isn't specified (rhertogh)
- Bug #331: OpenID Connect `aud` claim can either be a string or a list of strings (azmeuk)
- Bug #332: OpenID Connect `aud` nonce is passed from the authentication request to the token request (azmeuk)
- Bug #339: OpenID Connect client now regenerates a new `nonce` when refreshing the access token (rhertogh)
- Bug #344: Fix Facebook OAuth 400 error when latin characters are used in App name (pawelkania)
- Enh #279: Add `AuthAction::$defaultClientId` and `AuthAction::getClientId()` (ditibal)
- Enh #341: OpenID Connect client now uses access token `'id_token'` claim for `getUserAttributes()` if `userinfo_endpoint` is not available (rhertogh)
- Enh #342: OpenID Connect client support for JWT in `userinfo_endpoint` response (rhertogh)


2.2.11 August 09, 2021
----------------------

- Enh #318: Add `statusCode` from response to init `InvalidResponseException` in `sendRequest` method of `yii\authclient\BaseOAuth` class (vleedev)
- Enh #327: Use `random_int()` when generating OAuth1 nonce (samdark)


2.2.10 May 05, 2021
-------------------

- Chg #315: Add proof key for code exchange PKCE support to oauth2 (AdeAttwood)


2.2.9 November 13, 2020
-----------------------

- Bug #312: do not refresh access token if it is not expired (albertborsos)


2.2.8 November 10, 2020
-----------------------

- Bug #309: Try to refresh token in `BaseOAuth->beforeApiRequestSend()` if `BaseOAuth->autoRefreshAccessToken = true` instead of throwing "Invalid access token" exception (marty-macfly)
- Bug #311: Fix PHP 8 compatibility (samdark)


2.2.7 February 12, 2020
-----------------------

- Bug #292: Updated GitHub token transfer method according to https://developer.github.com/changes/2019-11-05-deprecated-passwords-and-authorizations-api/#authenticating-using-query-parameters (raidkon)


2.2.6 November 19, 2019
-----------------------

- Bug #288: Default request option for turning off SSL peer verification was removed (Rutger, samdark)
- Enh #205: Add alternative storage system based on cache component (marty-macfly, tunecino)


2.2.5 November 05, 2019
-----------------------

- Enh #217: Replace spomky-labs/jose by JWT Framework (marty-macfly, smcyr)


2.2.4 July 02, 2019
-------------------

- Enh #276: Bumped VK API version to 5.95, according to developers recommendation (EvgeniyRRU)
- Enh #278: Keep only selected parameters in default return URLs of OAuth services (albertborsos)


2.2.3 June 04, 2019
-------------------

- Chg #273: `OpenIdConnect::validateClaims()` is now protected (samdark)


2.2.2 May 14, 2019
------------------

- Bug #270: Updated Facebook icon to match brand guidelines (ServerDotBiz)


2.2.1 April 23, 2019
--------------------

- Bug #252: Fix bug when `OAuthToken` is incorrectly instantiated if configuration array has incorrect order (rob006)


2.2.0 April 16, 2019
--------------------

- Bug #266: Updated Google client image (nurielmeni)
- Bug #267: Upgrade LinkedIn client to v2 (machour)


2.1.8 January 28, 2019
----------------------

- Bug #237: Fix redirect from LinkedIn if user refused to authorize permissions request (jakim)
- Enh #218: Allow configuring user component in `AuthAction` (samdark, lab362)
- Enh #258: Use Google Sign-in API instead of Google Plus in `yii\authclient\clients\Google` as Google Plus is deprecated (alexeevdv)
- Enh #259: Allow to pass buildAuthUrl params to OAuth flows in `AuthAction` (albertborsos)


2.1.7 September 20, 2018
------------------------

- Bug #241: Unset parameter `scope` on `defaultReturnUrl` for `OAuth2` class since it was causing bad request response from Google provider (okiwan)


2.1.6 September 07, 2018
------------------------

- Bug #211: `RsaSha` was not passing `$key` to `openssl_pkey_get_private()` in `generateSignature()` (cfhodges)
- Bug #220: Make `OpenIdConnect` client send token as bearer auth instead of querystring parameter (lukos)
- Bug #237: Fixed redirect if user cancels login in auth form (msvit1989)
- Enh #203: Updated VKontakte client to use API version 5.0 (Shketkol)


2.1.5 February 08, 2018
-----------------------

- Enh #187: URL endpoints for `authUrl` and `tokenUrl` for `yii\authclient\clients\LinkedIn` updated (Felli)
- Enh #195: `yii\authclient\AuthAction` refactored to use `yii\web\Application::$request` for request data access (klimov-paul)
- Enh #196: Added `yii\authclient\AuthAction::$cancelCallback` allowing custom handling for authentication cancelation (terales, klimov-paul)


2.1.4 November 03, 2017
-----------------------

- Bug #152: Fixed JavaScript callback generated by `\yii\authclient\widgets\GooglePlusButton` consider 'immediate_failed' as instant auth error (klimov-paul)
- Bug: Usage of deprecated `yii\base\Object` changed to `yii\base\BaseObject` allowing compatibility with PHP 7.2 (klimov-paul)
- Enh #178: Added `yii\authclient\clients\TwitterOAuth2` supporting 'application-only authentication' workflow for Twitter (klimov-paul)
- Enh #179: Added `apiVersion` at `yii\authclient\clients\VKontakte` (isudakoff)
- Enh #185: `yii\authclient\clients\VKontakte::initUserAttributes()` now throws verbose exception on unexpected API response instead of PHP error (klimov-paul)


2.1.3 June 23, 2017
-------------------

- Bug #152: Fixed `\yii\authclient\OAuth1::fetchRequestToken()` skips formatting for `yii\httpclient\Request` (klimov-paul)
- Bug #160: Fixed `\yii\authclient\OAuth1::composeSignatureBaseString()` does not take URL query string into account (klimov-paul)
- Enh #155: Added `\yii\authclient\OpenIdConnect` supporting [OpenID Connect](https://openid.net/connect/) protocol (klimov-paul)
- Enh #156: Added `\yii\authclient\signature\RsaSha` and `\yii\authclient\signature\HmacSha` supporting general 'SHAwithRSA' and 'HMAC SHA' signature methods (klimov-paul)
- Enh #157: Added `\yii\authclient\OAuth2::authenticateUserJwt()` supporting authentication via JSON Web Token (JWT) (klimov-paul)
- Enh #163: Added support for exchanging access token at `yii\authclient\clients\Facebook` (klimov-paul)
- Enh #163: Added support for client-specific access tokens at `yii\authclient\clients\Facebook` (klimov-paul)
- Chg #163: `yii\authclient\clients\Facebook::$autoRefreshAccessToken` is now disabled by default (klimov-paul)


2.1.2 February 15, 2017
-----------------------

- Bug #135: Fixed `\yii\authclient\OAuth1::fetchRequestToken()` duplicates auth params in the request body, which may cause error on some OAuth 1.0 providers (klimov-paul)
- Bug #149: Changed `$` to `jQuery` to prevent global conflicts in widget JavaScript (Ariestattoo)
- Enh #67: Added `appsecret_proof` generation for the API requests at `yii\authclient\clients\Facebook` (blackhpro, SDKiller, klimov-paul)


2.1.1 August 29, 2016
---------------------

- Bug #128: Fixed `\yii\authclient\BaseClient::createRequest()` does not apply `defaultRequestOptions` and `requestOptions` (klimov-paul)
- Bug #130: Fixed `\yii\authclient\OAuth1::fetchRequestToken()` unable to unset current access token (klimov-paul)
- Enh #27: Added `\yii\authclient\OAuth1::authorizationHeaderMethods` option allowing to control request methods, which require authorization header (klimov-paul)
- Enh #132: URL endpoints for `authUrl` and `tokenUrl` for `yii\authclient\clients\VKontakte` updated (KhristenkoYura)


2.1.0 August 04, 2016
---------------------

- Enh #27: This extension no longer require PHP 'cURL' extension to be installed (klimov-paul)
- Enh #30: Added support for 'client_credentials' grant type via `\yii\authclient\OAuth2::authenticateClient()` (klimov-paul)
- Enh #33: Added ability to pass raw request content at `\yii\authclient\BaseOAuth::api()` (klimov-paul)
- Enh #41: Added support for signature generation from request token at `\yii\authclient\OAuth1::fetchAccessToken()` (klimov-paul)
- Enh #63: Markup for `\yii\authclient\widgets\AuthChoice` simplified (klimov-paul)
- Enh #108: This extension now uses `yii2-httpclient` library for the HTTP requests (klimov-paul)
- Enh #118: Added support for 'password' grant type via `\yii\authclient\OAuth2::authenticateUser()` (klimov-paul)
- Enh #121: Auth client 'State Storage' abstraction layer extracted (klimov-paul)
- Enh #124: Methods `clientLink()` and `renderMainContent()` of `yii\authclient\widgets\AuthChoice` reworked to return HTML instead of echo (klimov-paul)
- Enh #127: Auth 'state' validation added to `OAuth2` for preventing cross-site request forgery (klimov-paul)


2.0.6 July 08, 2016
-------------------

- Bug #37: Fixed `\yii\authclient\widgets\AuthChoice` overrides any `<a>` tag click behavior between `begin()` and `end()` methods (klimov-paul)
- Enh #31: Allow to disable automatic 'refresh access token' requests (klimov-paul)
- Enh #58: Added support for user attribute request params setup for Twitter (umanamente, klimov-paul)
- Enh #111: `yii\authclient\clients\GitHub` now retrieves user email even if it is set as 'private' at GitHub account (klimov-paul)


2.0.5 September 23, 2015
------------------------

- Bug #25: `yii\authclient\BaseOAuth` now can be used without without `session` application component available (klimov-paul)
- Enh #40: Added `attributeNames` field to `yii\authclient\clients\Facebook`, which allows definition of attributes list fetched from API (samdark)
- Chg: #47: Default popup size for `yii\authclient\clients\Facebook` has been increased up to 860x480 (lame07, klimov-paul)


2.0.4 May 10, 2015
------------------

- Bug #7224: Fixed incorrect POST fields composition at `yii\authclient\OAuth1` (klimov-paul)
- Bug #7639: Automatic exception throw on 'error' key presence at `yii\authclient\BaseOAuth::processResponse()` removed (klimov-paul)
- Enh #17: Added `attributeNames` field to `yii\authclient\clients\VKontakte` and `yii\authclient\clients\LinkedIn`, which allows definition of attributes list fetched from API (klimov-paul)
- Enh #6743: Icon for Google at `yii\authclient\widgets\AuthChoice` fixed to follow the Google Brand guidelines (klimov-paul)
- Enh #7733: `yii\authclient\clients\VKontakte` now gets attributes from access token also (klimov-paul)
- Enh #7754: New client `yii\authclient\clients\GooglePlus` added to support Google recommended auth flow (klimov-paul)
- Chg: #7754: `yii\authclient\clients\GoogleOpenId` is now deprecated because this auth method is no longer supported by Google as of April 20, 2015 (klimov-paul)


2.0.3 March 01, 2015
--------------------

- Enh #6892: Default value of `yii\authclient\clients\Twitter::$authUrl` changed to 'authenticate', allowing usage of previous logged user without request an access (kotchuprik)


2.0.2 January 11, 2015
----------------------

- Bug #6502: Fixed `\yii\authclient\OAuth2::refreshAccessToken()` does not save fetched token (sebathi)
- Bug #6510: Fixed infinite redirect loop using default `\yii\authclient\AuthAction::cancelUrl` (klimov-paul)


2.0.1 December 07, 2014
-----------------------

- Bug #6000: Fixed CCS for `yii\authclient\widgets\AuthChoice` does not loaded if `popupMode` disabled (klimov-paul)


2.0.0 October 12, 2014
----------------------

- Enh #5135: Added ability to operate nested and complex attributes via `yii\authclient\BaseClient::normalizeUserAttributeMap` (zinzinday, klimov-paul)


2.0.0-rc September 27, 2014
---------------------------

- Bug #3633: OpenId return URL comparison advanced to prevent url encode problem (klimov-paul)
- Bug #4490: `yii\authclient\widgets\AuthChoice` does not preserve initial settings while opening popup (klimov-paul)
- Bug #5011: OAuth API Response with 20x status were not considered success (ychongsaytc)
- Enh #3416: VKontakte OAuth support added (klimov-paul)
- Enh #4076: Request HTTP headers argument added to `yii\authclient\BaseOAuth::api()` method (klimov-paul)
- Enh #4134: `yii\authclient\InvalidResponseException` added for tracking invalid remote server response (klimov-paul)
- Enh #4139: User attributes requesting at GoogleOAuth switched to Google+ API (klimov-paul)


2.0.0-beta April 13, 2014
-------------------------

- Initial release.
