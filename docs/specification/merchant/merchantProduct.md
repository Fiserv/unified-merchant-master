# Merchant Products

* **Description**:
* **API section**: products
* **Table Name**: UMM.MERCHANT_PRODUCT

## List of Fields

### MERCHANT_ID

* Description: Unique identifier of the merchant. It is required to add merchant-specific information to the database.
* API field: `merchantId`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 8        |    50        |    Required     | Required     | Required |    Required     |

* Merchant Id is required for carrying out any operation on a specific merchant.

<!-- type: tab -->

| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Required   | Required   | Required   | Required  |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 8        |    8        |    Required     | Required     | Required |    NA     |

<!-- type: tab-end -->
---

### PLATFORM_CODE

* Description: Code to identify the specific backend platform. It adds the required information for the merchant.
* API field: `platformCode`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Required     | Required     | Required |    Required  |

**Valid Values**:
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| NORTH     |   North Backend     |
| OMNIPAY26     |  Omnipay Backend ( GMA)      |
| SOUTH     |     South  Backend |
| OMNIPAY21     |    Omnipay ( Australia)    |

<!-- type: tab -->

| Type   | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------:|:------------:|:------------:|:------------:|
| String   | Required   | Required   | Required   | Required     |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| NORTH     |     North   |

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Required     | Required     | Required |       NA     |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| OMNIPAY26     |  Omnipay Backend ( GMA)    |
| OMNIPAY21     |    Omnipay ( Australia)    |

<!-- type: tab-end -->
---

### PRDCT_CODE

* Description: The product code associated with the product and defined by UMM API.
* API field: productCode
* Field Specification:

<!-- type: tab 
titles: UMM
-->

| Type   | Minimum Length | Max Length | Inquiry | Create | Update | Delete |
|--------|:--------------:|:----------:|:-------:|:------:|:------:|:------:|
| Enum   |   NA   |   NA  |  Available |  Required   |     NA      |   NA   |

**Valid Values**:
|      Product Category   |                    Valid Value                |                 Description                     |
|:------------------------|:----------------------------------------------|:------------------------------------------------|
| ENTITLEMENT | ENTLVI | Visa Entitlement |
| ENTITLEMENT | ENTLPVTLBL | Private Label Multicard Entitlement |
| ENTITLEMENT | ENTLAMEXPT | Amex Pass Through Entitlement |
| ENTITLEMENT | ENTLJCB | Jcb Entitlement |
| ENTITLEMENT | ENTLAMEXOB | Amex Opt Blue Entitlement |
| ENTITLEMENT | ENTLVOYGER | Voyager Entitlement |
| ENTITLEMENT | ENTLENCORE | Encore Entitlement |
| ENTITLEMENT | ENTLDBTEDS | Debit Eds Entitlement |
| ENTITLEMENT | ENTLJBS | Jbs Entitlement |
| ENTITLEMENT | ENTLTCK | Telecheck Entitlement |
| ENTITLEMENT | ENTLTELCRD | Telecredit Entitlement |
| ENTITLEMENT | ENTLETC | Etc Entitlement |
| ENTITLEMENT | ENTLEXPLR | Explore Entitlement |
| ENTITLEMENT | ENTLINTLNK | Interlink Entitlement |
| ENTITLEMENT | ENTLPURCRD | $ |
| ENTITLEMENT | ENTLEBT | Ebt Entitlement |
| ENTITLEMENT | ENTLDBTGTW | Debit Gateway Entitlement |
| ENTITLEMENT | ENTLFNDSV | Funded Stored Value Entitlement |
| ENTITLEMENT | ENTLUFNDSV | Unfunded Stored Value Entitlement |
| ENTITLEMENT | ENTLGNPVLB | Generic Private Label Entitlement |
| ENTITLEMENT | ENTLT2CRD | Tier Ii Credit Entitlement |
| ENTITLEMENT | ENTLCHKWAR | Check Warranty Entitlement |
| ENTITLEMENT | ENTLCHKNWR | Check Non Warranty Entitlement |
| ENTITLEMENT | ENTLWRTEXP | Wright Express Entitlement |
| ENTITLEMENT | ENTLFLTCOR | Fleetcore Entitlement |
| ENTITLEMENT | ENTLFLTONE | Fleetone Entitlement |
| ENTITLEMENT | ENTLFRPET1 | Future Petroleum 1 Entitlement |
| ENTITLEMENT | ENTLFRPET2 | Future Petroleum 2 Entitlement |
| ENTITLEMENT | ENTLFRPET3 | Future Petroleum 3 Entitlement |
| ENTITLEMENT | ENTLERNLYT | Earn Loyalty Entitlement |
| ENTITLEMENT | ENTLBILLAT | Bill Me Later Entitlement |
| ENTITLEMENT | ENTLGLALTM | Global Alternate Mops Entitlement |
| ENTITLEMENT | ENTLPAYPAL | Paypal Entitlement |
| ENTITLEMENT | ENTLGGLCKT | Google Checkout Entitlement |
| ENTITLEMENT | ENTLARVEOL | Arvato Eold Entitlement |
| ENTITLEMENT | ENTLOFRWSE | Offerwise Entitlement |
| ENTITLEMENT | ENTLSIGDBT | Signature Debit Entitlement |
| ENTITLEMENT | ENTLMCMA | Mastercard Ma Entitlement |
| ENTITLEMENT | ENTLVIMA | Visa Ma Entitlement |
| ENTITLEMENT | ENTLDISCMA | Discover Ma Entitlement |
| ENTITLEMENT | ENTLAMEXMA | Amex Ma Entitlement |
| ENTITLEMENT | ENTLDBTMA | Debit Ma Entitlement |
| ENTITLEMENT | ENTLMSTROI | Maestro International Entitlement |
| ENTITLEMENT | ENTLCLOVERGO | Clover Mobile Payment Application On Your Own Device |
| ENTITLEMENT | ENTLVASGYFT | Gyft Smb Gift Card Solution For All Clover Merchants. Includes Both Physical And Digital Gift Cards. |
| ENTITLEMENT | ENTLPPALDIS | Paypal Enablement For Discover Full Service Merchant |
| ENTITLEMENT | ENTLALIPAY | Alipay Will Be Enabled For  Certain Type Of Merchants To Process Alipay Transaction |
| ENTITLEMENT | ENTLCUP | China Union Pay Will Be Enabled For  Certain Type Of Merchants To Process China Union Pay Transaction |
| ENTITLEMENT | ENTLVALLNK | Valuelink Auto Board Allows for a Mechanized Process for Adding The Valuelink Entitlement to Premium Merchants |
| ENTITLEMENT | ENTLPPLVNMO | The Paypal/Venmo QRC Program Will Provide Participating Merchants The Ability To Process Paypal And Venmo Transactions Via Quick Response (QR) Code Payment Types |
| ENTITLEMENT | ENTLBNTBOX | Shows Elgibility For Bentobox Product Offering |
| ENTITLEMENT | ENTLINTERACFLS | Interac Flash Entitlement |
| ENTITLEMENT | ENTLINTERACCNT | Interac Contact Entitlement |
| ENTITLEMENT | ENTLINTERACINAPP | Interac In App Entitlement |
| ENTITLEMENT | ENTLUPIDBT | UPI Debit Entitlement |
| ENTITLEMENT | ENTLUPICRD | UPI Credit Entitlement |
| ENTITLEMENT | ENTLPPRO | PPRO |
| ENTITLEMENT | ENTLWECHATPAY | We Chat Pay |
| ENTITLEMENT | ENTLDINER | Diners Entitlement |
| ENTITLEMENT | ENTLMC | Mastercard Entitlement |
| ENTITLEMENT | ENTLAPM | ACQ APM |
| ENTITLEMENT | ENTLVIDB | Visa Debit Entitlement |
| ENTITLEMENT | ENTLMCDB | Mastercard Debit Entitlement |
| ENTITLEMENT | ENTLSVBLKHWK | Stored Value Cards - Blackhawk |
| ENTITLEMENT | ENTLSVESI | Stored Value Cards - ESI |
| ENTITLEMENT | ENTLFLEET | Fleet Cards |
| ENTITLEMENT | ENTLDISCDRCT | Discover Direct Entitlement |
| ENTITLEMENT | ENTLEFTPOS | Electronic Funds Transfer at Point of Sale |
| VAS | VASSAMSPLS | Free SAMS Club Plus membership for the term of your merchant contract. This promo is offered as long as a merchant has an active processing account (activity within last 6 months). |
| VAS | VASWELLSP | Wells Statement And Notice Preferences |
| VAS | VASMSTTIST | Main Street Insights |
| VAS | VASPERKA | Perka Is A Mobile Loyalty Application |
| VAS | VASVETPRG | The Veterans Program Will Provide Particpating Merchants With Special Treatment (Such As Reduced Billing On Veterans Day, And Other Times Of Year). |
| VAS | VASPAYEEZY | This Program Indicates That A Merchant Is Using A Payeezy Product - Includes Specific Software Api Developed By Third Parties |
| VAS | VASMSTPWLT | The Masterpass Wallet Program Is Offerred By Mastercard International To Allow Merchants To Accept Transactions From Cardholders That Are Participating. |
| VAS | VASVRUSRV | This Program Is For Capture Of Attributes Related To The Vru Service ( Such As Whether The Merchant Is Vru White Listed Or Black Listed) |
| VAS | VASTRNSARM | This Program Enables Pci Compliance By Allowing A Merchant To Receive A Daily File Of Transarmor Tokenized Transaction Data.  The Data Included May Contain Authorization Data, Settlement Data, Or Both. |
| VAS | VASEMVCMP | The Emv Campaign Is Targeting Existing Clients Who Are Not Emv Ready To Purchase Emv Compatible Terminals Such As Clover.  Customers Are Separated Into Precious Metal Segments Based On Their Processing Volume - Platinum, Gold, Silver And Bronze. |
| VAS | VASTEMPUS | First Data Is Billing Merchants For Pass Through Fees For Tempus, 3Rd Party Gateway. Set Up Fee, Transaction Fees And Equipment Purchase + Shipping And Tax. |
| VAS | VASFRDFLX | Fraud Flexdetect Is A White Labeled, First Data Ecommerce Fraud Solution That Utilizes Accertifys Intercept As Risk Platform |
| VAS | VASEMVENB | EMV Enablement Field Will Be Provided By The Boarding Tools And Sent To MAI For All Merchants. |
| VAS | VASFRDDTCT | Merchant Fraud Solution Which Will Score Transactions And Identify Fraud. |
| VAS | VASBPMOB | Store Terminal Type For Bp Terminals |
| VAS | VASTAP2PE | Transarmor P2PE (Point To Point Encyption) Progam |
| VAS | VASENTINSD | Add On Product To Enterprise Insights To Provide Demographics Information |
| VAS | VASENTINSB | Add On Product To Enterprise Insights To Provide Bench Sub-Product |
| VAS | VASENTINSL | Add On Product To Enterprise Insights To Provide Lobby Sub-Product |
| VAS | VASTXNINS | Transaction Insights Provides In Depth Merchant Acquiring Transaction Visibility To Mid Market And National Merchants |
| VAS | VASADVINS | Tool To Measure Marketing Campaign Effectiveness |
| VAS | VASENTINS | Enterprise Insights |
| VAS | VASPDATAPRT | Tokenization Of PII, PHI And SPI Data |
| VAS | VASMERSRCH | Surcharging Allows Merchants To Add a Checkout Fee To a Credit Card Transaction To Cover The Merchants Credit Card Processing Fees |
| VAS | VASGBSPOSINS | The Objective Of This Program Is To Launch Pos Installments Solutions To Our Merchants, Where They Can Allow Their Customers To Pay For Goods And Services In Affordable Installment Payments. This Is To Help Our Merchants Drive Sales And Help Consumers Get |
| VAS | VASLCRFB | Fall-Back Is a Process By Which Fes Will Route Transactions Via The Credit Card Path, After Receiving a Soft Decline From The Debit Gateway.  If Indicator Is Set To Y, Fall-Back Logic Will Be Turned Off. |
| VAS | VASNTWKTKN | Fiserv Will Be a Merchant Token Requestor And Request Network Tokens From Card Associations On Behalf Of Fiserv Merchants. |
| VAS | VASWSLENT | Identifies Merchants Belonging To Different Merchant Hierarchies Who Are Subscribed To The Wisely Services |
| VAS | VASLCRDBT | Make Debit Flags Optional Will Allow Merchants To Launch Lcr Without Making Any Changes.  The Flag Will Indicate That The Data In The Response Will Not Be Updated With Debit Response Data.  If Indicator Is Set To Y, Optional Debit Flag, Where The Mop Will |
| VAS | VASDBTRT | Debit Routing |
| VAS | VASDAAS | DaaS - Enhance Data Service |
| VAS | VASDAASRET | DaaS- Return Optimization |
| VAS | VASAUTHOPT | Auth Optimization |
| VAS | VASINTRTNG | Intelligent Routing |
| VAS | VASMCMONEYSEND | MASTERCARD MONEYSEND WILL ENABLE CERTAIN TYPE OF MERCHANTS THE ABILITY TO PULL AND OR PUSH FUNDS TO A MASTERCARD CARD. |
| VAS | VASVISAACTUPD | VISA ACCOUNT UPDATER IS A PRE-AUTHORISATION SERVICE THAT ENABLES MERCHANTS WHO HANDLE RECURRING TRANSACTOINS TO RECEIVE UPDATED CARD NUMBER, EXPIRY DATE AND STOP ADVICES FROM A DATABASE. |
| VAS | VASVISAOCT | VISA OCT WILL ENABLE CERTAIN TYPE OF MERCHANTS THE ABILITY TO PULL AND OR PUSH FUNDS TO A VISA CARD |
| VAS | VASVISACHKOUT | VISA CHECKOUT IS VISAS ONLINE PAYMENT SYSTEM WHICH ALLOWS USERS TO STORE THEIR PERSONAL DETAILS AND CARD INFORMATION TO BE USED TO MAKE ONLINE PURCHASES WHILE AUTHENTICATING WITH A USERNAME AND PASSWORD |
| VAS | VASVISAACTFNDTRX | ACCOUNT FUNDING TRANSACTIONS (AFT) IS A VISA TRANSACTION USED TO PULL FUNDS FROM A VISA CARD ACCOUNT FOR THE PURPOSE OF FUNDING A DIFFERENT, NON-MERCHANT ACCOUNT. |
| VAS | VASDISCDBTACP | DISCOVER DEBT REPAYMENT PROGRAM ALLOWS MERCHANTS WITH MCC 6012 OR MCC 6051 THE ABILITY TO ACCEPT DEBIT CARDS FOR PAYMENT OF LOANS INCLUDED BUT NOT LIMITED TO RECURRING, CAR LOANS AND MORTGAGE PAYMENTS |
| VAS | VASDISCINCAUTH | DISCOVER INCREMENTAL AUTH ALLOWS MERCHANTS TRANSACTING IN CERTAIN MCCS IN THE TRAVEL AND ENTERTAINMENT INDUSTRIES TO SUPPORT MULTIPLE AUTHORIZATIONS THAT WILL TIE TO A SINGLE SETTLEMENT TRANSACTION. INCREMENTAL AUTHORIZATIONS ALLOW MERCHANTS TO INCREASE |
| VAS | VASDISCPROMPRG | THIS PROGRAM WILL BE APPLIED TO DISCOVER FULL SERVICE MERCHANTS WITH ANNUAL VOLUME < $5MN. ONLY SPECIFIC CHANNEL WILL BE APPLICABLE. DISCOVER WILL PROVIDE THE PVI VALUE. |
| VAS | VASDBTTERMID | Debit Term ID |
| VAS | VASPINLESSECOM | TRANSACTION ROUTING FOR PINLESS NASHVILLE/DEBIT GATEWAY TO SOUTH BACKEND |
| VAS | VASTCKCP | TELECHECK CHECK PRESENTATION ENTITLEMENT |
| VAS | VASLEASE | Lease Product |
| VAS | VASCASHADV | Cash Advance Product |
| VAS | VASENDATASVC | DaaS - Enhance Data Service |
| VAS | VASRETOPTMZN | DaaS- Return Optimization |
| FEE | F100PRODUCTS | 100 Products |
| FEE | FONETIMEACCTSETUP | 1Time Acct Setup Add Loc Fee |
| FEE | F3MNTHSTMTCRD250 | 250 Statement Cred Over 3 Mos |
| FEE | F3RDPRTYACCTINTRMMNTH | 3Rdprty Accntintrm Monthly Fee |
| FEE | F3RDPRTYACCTSETUP | 3Rdprty Accntintrm Setup Fee |
| FEE | FBLKHWK12MNTHINSTALLMT | 3Rdprty Blackhwk Instlmt Fee12 |
| FEE | FBLKHWK24MNTHINSTALLMT | 3Rdprty Blackhwk Instlmt Fee24 |
| FEE | FBLKHWK36MNTHINSTALLMT | 3Rdprty Blackhwk Instlmt Fee36 |
| FEE | FBLKHWKMNTH | 3Rdprty Blackhwk Monthly Fee |
| FEE | FBLKHWKSETUP | 3Rdprty Blackhwk Setup Fee |
| FEE | FCSHSTR12MNTHINSTALLMT | 3Rdprty Cashstar Instlmt Fee12 |
| FEE | FCSHSTR24MNTHINSTALLMT | 3Rdprty Cashstar Instlmt Fee24 |
| FEE | FCSHSTR36MNTHINSTALLMT | 3Rdprty Cashstar Instlmt Fee36 |
| FEE | FCSHSTRMNTH | 3Rdprty Cashstar Monthly Fee |
| FEE | FCSHSTRSETUP | 3Rdprty Cashstar Setup Fee |
| FEE | FCOINSTR12MNTHINSTALLMT | 3Rdprty Coinstar Instlmt Fee12 |
| FEE | FCOINSTR24MNTHINSTALLMT | 3Rdprty Coinstar Instlmt Fee24 |
| FEE | FCOINSTR36MNTHINSTALLMT | 3Rdprty Coinstar Instlmt Fee36 |
| FEE | FCOINSTRMNTH | 3Rdprty Coinstar Monthly Fee |
| FEE | FCOINTRSETUP | 3Rdprty Coinstar Setup Fee |
| FEE | FEGFTSOCMNTH | 3Rdprty Egftsoc Monthly Fee |
| FEE | FEGFTSOCSETUP | 3Rdprty Egftsoc Setup Fee |
| FEE | FGFTTANGO12MNTHINSTALLMT | 3Rdprty Giftango Instlmt Fee12 |
| FEE | FGFTTANGO24MNTHINSTALLMT | 3Rdprty Giftango Instlmt Fee24 |
| FEE | FGFTTANGO36MNTHINSTALLMT | 3Rdprty Giftango Instlmt Fee36 |
| FEE | FGFTTANGOMNTH | 3Rdprty Giftango Monthly Fee |
| FEE | FGFTTANGOSETUP | 3Rdprty Giftango Setup Fee |
| FEE | FGLSMNTH | 3Rdprty Gls Monthly Fee |
| FEE | FGLSSETUP | 3Rdprty Gls Setup Fee |
| FEE | F3RDPRTYINCOMMMNTH | 3Rdprty Incomm Monthly Fee |
| FEE | F3RDPRTYINCOMMSETUP | 3Rdprty Incomm Setup Fee |
| FEE | FINCOM12MNTHINSTALLMT | 3Rdprty Incomm Instlmt Fee12 |
| FEE | FINCOM24MNTHINSTALLMT | 3Rdprty Incomm Instlmt Fee24 |
| FEE | FINCOM36MNTHINSTALLMT | 3Rdprty Incomm Instlmt Fee36 |
| FEE | FJETMNTH | 3Rdprty Jet Monthly Fee |
| FEE | FJETSETUP | 3Rdprty Jet Setup Fee |
| FEE | FLSNMNTH | 3Rdprty Lsn Monthly Fee |
| FEE | FLSNSETUP | 3Rdprty Lsn Setup Fee |
| FEE | FTIPPRMNTH | 3Rdprty Tippr Monthly Fee |
| FEE | FTIPPRSETUP | 3Rdprty Tippr Setup Fee |
| FEE | FWHRMNTH | 3Rdprty Where Monthly Fee |
| FEE | FWHRSETUP | 3Rdprty Where Setup Fee |
| FEE | F6MNTHSTMTCRD500 | 500 Statement Cred Over 6 Mos |
| FEE | F12MNTHSTMTCRD750 | 750 Statement Cred Over 12 Mos |
| FEE | FACCELNTWKANNUAL | Accel Network Annual Fee |
| FEE | FACCTVERFSVC | Accnt Verification Service Fee |
| FEE | FACCTMIN | Account Minimum Fee |
| FEE | FACCTMINADJREV | Account Minimum Fee Adj/Rev |
| FEE | FACCTONFILEF44N | Account On File Fee |
| FEE | FACCTBRDNGCOMP | Acct Boarding & Comp. Fee |
| FEE | FACHRJCTATBANK | Ach Rejected At Bank |
| FEE | FACHTXN | Ach Transaction Fee |
| FEE | FACTIVATIONREBATE | Activation Rebate |
| FEE | FADDRVERSVC | Addrs Verification Service Fee |
| FEE | FRPDPRDT12MNTHINSTALLMT | Advrpt Dpromodet Instlmt Fee12 |
| FEE | FRPDPRDT24MNTHINSTALLMT | Advrpt Dpromodet Instlmt Fee24 |
| FEE | FRPDPRDT36MNTHINSTALLMT | Advrpt Dpromodet Instlmt Fee36 |
| FEE | FRPDPRDTMNTH | Advrpt Dpromodet Monthly Fee |
| FEE | FRPDPRDTSETUP | Advrpt Dpromodet Setup Fee |
| FEE | FRPMPRDT12MNTHINSTALLMT | Advrpt Mpromodet Instlmt Fee12 |
| FEE | FRPMPRDT24MNTHINSTALLMT | Advrpt Mpromodet Instlmt Fee24 |
| FEE | FRPMPRDT36MNTHINSTALLMT | Advrpt Mpromodet Instlmt Fee36 |
| FEE | FRPMPRDTMNTH | Advrpt Mpromodet Monthly Fee |
| FEE | FRPMPRDTSETUP | Advrpt Mpromodet Setup Fee |
| FEE | FRPOUTSTDBAL12MNTHINSTALLMT | Advrpt Outstdbal Instlmt Fee12 |
| FEE | FRPOUTSTDBAL24MNTHINSTALLMT | Advrpt Outstdbal Instlmt Fee24 |
| FEE | FRPOUTSTDBAL36MNTHINSTALLMT | Advrpt Outstdbal Instlmt Fee36 |
| FEE | FRPOUTSTDBALMNTH | Advrpt Outstdbal Monthly Fee |
| FEE | FRPOUTSTDBALSETUP | Advrpt Outstdbal Setup Fee |
| FEE | FALIPAYAUTH | Alipay Authorization Fee |
| FEE | FALIPAYRETDSC | Alipay Return Discount Fee |
| FEE | FALIPAYRETTXN | Alipay Return Transaction Fee |
| FEE | FALIPAYSLSDSC | Alipay Sales Discount Fee |
| FEE | FALIPAYSLSTXN | Alipay Sales Transaction Fee |
| FEE | FAMX3000 | Amex 3000 |
| FEE | FAMX3200 | Amex 3200 |
| FEE | FAMX950AUTH | Amex 950 Auth Fee |
| FEE | FAMXACPTNOACPT | Amex Accept/No Accept Fee |
| FEE | FAMXARULCLAUTH | Amex Aru Local Auth Fee |
| FEE | FAMXARUWATSAUTH | Amex Aru Wats Auth Fee |
| FEE | FAMXAUTOADDRVER | Amex Auto Addr Verification |
| FEE | FAMXBATCHAUTH | Amex Batch Authorization |
| FEE | FAMXBATCHAUTHFOYC | Amex Batch Authorization Fee |
| FEE | FAMXBLBKAMT | Amex Billback Amount |
| FEE | FAMXCHGBKFAXMAILRECD | Amex Cb Excpt Recd Fax/Mail |
| FEE | FAMXCHGBKFAXMAILCRSPND | Amex Cb/Excpt Package Fax/Mail |
| FEE | FAMXCHGBKRTVL | Amex Chargb Retriev Fee |
| FEE | FAMXCHGBK | Amex Chargeback |
| FEE | FAMXCHGBKAMTF20L | Amex Chargeback Fee |
| FEE | FAMXCHGBKTXN | Amex Chargeback Trans |
| FEE | FAMXCPUAUTH | Amex Cpu Authorization |
| FEE | FAMXDBTRETDSC | Amex Debit Returns Disc Fee |
| FEE | FAMXDBTRETTXN | Amex Debit Returns Tran Fee |
| FEE | FAMXDBTSLSDSC | Amex Debit Sales Disc Fee |
| FEE | FAMXDBTSLSTXN | Amex Debit Sales Tran Fee |
| FEE | FAMXDFLTAUTH | Amex Default Auth Fee |
| FEE | FAMXADJREVDSC | Amex Discount Fee Adj/Rev |
| FEE | FAMXDSC | Amex Discount Rate |
| FEE | FAMXECRADDRVER | Amex Ecr Address Verification |
| FEE | FAMXINTRNTAUTH | Amex Internet Auth Fee |
| FEE | FAMXLATERESP | Amex Late Response Fee |
| FEE | FAMXMQCRDTTXN | Amex Mid Qual Credits Tran Fee |
| FEE | FAMXMQRTNDSC | Amex Mid Qual Returns Discount |
| FEE | FAMXMQSLSDSC | Amex Mid Qual Sales Discount |
| FEE | FAMXMQSLSTXN | Amex Mid Qual Sales Trans Fee |
| FEE | FAMXNQCRDTTXN | Amex Non Qual Credit Tran Fee |
| FEE | FAMXNQRTNDSC | Amex Non Qual Returns Discount |
| FEE | FAMXNQSLSDSC | Amex Non Qual Sales Discount |
| FEE | FAMXNQSLSTXN | Amex Non Qual Sales Tran Fee |
| FEE | FAMXPRGMPRICING | Amex Program Pricing |
| FEE | FAMXRTVLFAXMAILCRSPND | Amex Retr Correspond Fax/Mail |
| FEE | FAMXRTVLFAXMAILRECD | Amex Retr Recd Fax/Mail |
| FEE | FAMXSLSDSC | Amex Sales Discount |
| FEE | FAMXTRMNLBLNG | Amex Terminal Billing |
| FEE | FAMXADJREVTXN | Amex Transaction Fee Adj/Rev |
| FEE | FAMXVOICEADDRVERAUTH | Amex Voice Addr Ver/Auth |
| FEE | FAMXVOICEAUTHF06Y | Amex Voice Auth Issuer Refer |
| FEE | FAMXVOICEISSUERREF | Amex Voice Issuer Referral Fee |
| FEE | FAMXDSCTXN | Amex/Discover Transaction Fee |
| FEE | FANNUALMNTNCPRIOR12MONTH | Annl Mntnce Fee Prior 12 Mths |
| FEE | FANNUALCMPLNC | Annual Compliance Fee |
| FEE | FANNUALCMPLNCREBATE | Annual Compliance Fee Rebate |
| FEE | FANNUALCMPLNCSVC | Annual Compliance Svc Fee |
| FEE | FANNUALLICENSE | Annual License Fee |
| FEE | FANNUALMNTNC | Annual Maintenance Fee |
| FEE | FANNUALMNTNCF49D | Annual Maintenance Fee |
| FEE | FANNUALPRPTYTAX | Annual Property Tax Billing |
| FEE | FANNUALSLSTAXCALC | Annual Sales Tax Calc Fee |
| FEE | FAUTOBILLMNTH | Autobill Monthly Fee Per Mid |
| FEE | FAUTOBILLSETUP | Autobill Set Up Fee |
| FEE | FAXPACQTXN | Axp Acquirer Trans Fee |
| FEE | FAXPPGMCONTINUATION | Axp Program Continuation Fee |
| FEE | FBNTOCTRNGORDR | Bentobox Catering Order Fee |
| FEE | FBENTOBOXEVNTSORDR | Bentobox Group Order/Event Fee |
| FEE | FBNTOONLORD | Bentobox Online Order Fee |
| FEE | FBLBKSRCHRG | Billback Surcharge Fee |
| FEE | FBLKACTVTNAUTH | Block Activation Auth Fee |
| FEE | FBMLAUTH | Bml Authorization Fee |
| FEE | FBMLDSC | Bml Discount Fee |
| FEE | FBMLTXN | Bml Transactions Fee |
| FEE | FBNDLSTMTCRD | Bundling Statement Credit |
| FEE | FBUSADVNTGPKG | Business Advantage Package |
| FEE | FBUYPASBTCH | Buypass Batch Fee |
| FEE | FCNCL | Cancellation Fee |
| FEE | FCARDRDRRBT | Card Reader Rebate |
| FEE | FCARDRDRSTMTCRD | Card Reader Statement Credit |
| FEE | FCARDPOINTEEGTWYSETUP | Cardpointe Gateway Setup Fee |
| FEE | FCASHADVSUPPRT | Cash Advance Support Fee |
| FEE | FCHGBKFAXMAIL | Cb/Except Fax/Mail |
| FEE | FSTRCHGBKFAXMAILS | Cb/Except Fax/Mail Star |
| FEE | FCHGBKADJ | Chargeback Adjustments |
| FEE | FCHGBKREBATE | Chargeback Fee Rebate |
| FEE | FCHGBKOVERTHRSHLD | Chargeback Over Threshold Fee |
| FEE | FCHGBKSUSPNS | Chargeback Suspense |
| FEE | FCKTFRAMESETUP | Circuit Fee/Frame Setup |
| FEE | FCLVRTASVC | Clover & Transarmor Services |
| FEE | FCLVRMNGDSCRTY | Managed Security Non Validated |
| FEE | FCLVRNONSWIPEDAUTH | Clover Non Swiped Authrztn Fee |
| FEE | FCLVRONLINE | Clover Online |
| FEE | FCLVRSCRTYMNTH | Clover Security Monthly |
| FEE | FCLVRSCRTYPLUSMNTH | Clover Security Plus Monthly |
| FEE | FCLVRMNGDSCRTYVLDTD | Managed Security Validated |
| FEE | FCMPSFRAUD192MSC | Cmps Fraud 192 Fee Msc |
| FEE | FCMPSFRAUDCARDCOPSMSC | Cmps Fraud Card Cops Msc |
| FEE | FCMPSFRAUDIDANALYTMSC | Cmps Fraud Id Analyt Msc |
| FEE | FCMPSFRAUDIDOLOGYMSC | Cmps Fraud Idology Msc |
| FEE | FCMPSFRAUDINSIGHT | Cmps Fraud Insight Fee |
| FEE | FCMPSFRAUDMNTH | Cmps Fraud Monthly Fee |
| FEE | FCMPSFRAUDPSTLVALIDMSC | Cmps Fraud Postal Valid Msc |
| FEE | FCMPSFRAUDRAPLEAF | Cmps Fraud Rapleaf Fee |
| FEE | FCMPSFRAUDSETUP | Cmps Fraud Setup Fee |
| FEE | FCMPSFRAUDTELESIGNMSC | Cmps Fraud Telesign Msc |
| FEE | FCMPSFRAUDTXNMSC | Cmps Fraud Trans Msc |
| FEE | FCNPAUTHMNTH | Cnp Auth Monthly Fee |
| FEE | FCNPAVS | Cnp Avs Fee |
| FEE | FCRDTCARDBTCHSTLMT | Credit Card Batch Settlements |
| FEE | FCYBRCASHERTHLNK | Cybercash Earthlink Fee |
| FEE | FCYBRIDLOCK | Cyberidlock |
| FEE | FCYBRSRCMNTH | Cybersource Monthly Fee |
| FEE | FCYBRSRCSETUP | Cybersource Setup Fee |
| FEE | FDATABREACHSCRTY | Data Breach Security Fee |
| FEE | FDBTACPTNC | Debit Acceptance Fee |
| FEE | FDBTADJPROCESSING | Debit Adjustmnt Processing Fee |
| FEE | FCMBDBTAUTH | Debit Authorization Fee Fs |
| FEE | FDBTDCLNINTCG | Debit Decline Interchange Fee |
| FEE | FDBTGTWYSWTCH | Debit Gateway Switch Fee |
| FEE | FDBTSETUP | Debit Set Up Fee |
| FEE | FDBTATMCARDTXN | Debit/Atm Card Transaction Fee |
| FEE | FDPLYMNT | Deployment Fee |
| FEE | FDGTLENBLMNT | Digital Enablement Fee |
| FEE | FDGTLINVSTMNT | Digital Investment Fee |
| FEE | FDNR950AUTH | Diners 950 Auth Fee |
| FEE | FMCDRCTENDCAPTURE | Direct Send Capture Fee |
| FEE | FDRCTVPNCONCTN | Direct Vpn Connection |
| FEE | FDSCVACCPTNOACPPT | Disc Accept/No Accept Fee |
| FEE | FDSCVCHGBKFAXMAILRECD | Disc Cb Excpt Recd Fax/Mail |
| FEE | FDSCVCHGBKFAXMAILPKG | Disc Cb/Excpt Package Fax/Mail |
| FEE | FDSCVLATERESP | Disc Late Response Fee |
| FEE | FDSCVRTVLFAXMAILCRSPND | Disc Retr Correspond Fax/Mail |
| FEE | FDSCVRTVLFAXMAILRECD | Disc Retr Recd Fax/Mail |
| FEE | FDSCNTMNTH | Discount Fee |
| FEE | FAMXDSCNTMNTH | Discount Fee |
| FEE | FDSCNTPERITEM | Discount Rate Per Item |
| FEE | FDSCV950AUTH | Discover 950 Auth Fee |
| FEE | FDSCVACCTUPDTPERTXN | Discover Acct Upd Per Tran Fee |
| FEE | FDSCVAUTOADDRVER | Discover Auto Addr Verif |
| FEE | FDSCVBTCHAUTH | Discover Batch Authorization |
| FEE | FDSCVBLBKAMT | Discover Billback Amount |
| FEE | FDSCVCPUAUTH | Discover Cpu Authorization |
| FEE | FDSCVDATAUSG | Discover Data Usage Fee |
| FEE | FDSCVDFLTAUTH | Discover Default Auth Fee |
| FEE | FDSCVDSCNT | Discover Discount Rate |
| FEE | FDSCVDUESASSMNT | Discover Dues/Assessment Fee |
| FEE | FDSCVEASIDSCNT | Discover Easi Discount Rate |
| FEE | FDSCVEASIMEMBRSHP | Discover Easi Membership Fee |
| FEE | FDSCVECRADDRVER | Discover Ecr Addr Verification |
| FEE | FDSCVINTRNTAUTH | Discover Internet Auth Fee |
| FEE | FDSCVRTVL | Discover Retrieval Fee |
| FEE | FDSCVVOICEADDRVERAUTH | Discover Voice Adr Ver/Auth |
| FEE | FDSCVVOICEAUTH | Discover Voice Auth Fee |
| FEE | FDSCVVCAUTHISRREF | Discover Voice Auth Issuer Ref |
| FEE | FDSCVDBTBLBKRDCN | Discvr Dbt Billbck Reduction |
| FEE | FDSCVINTLPROCESSING | Discvr Intl Processing Fee |
| FEE | FDSCVINTLSVC | Discvr Intl Service Fee |
| FEE | FMCDISPUTECASEDMS | Dispute Case Fee Mc Dms |
| FEE | FMSTRODISPUTEIMGSMS | Dispute Image Fee Maestro Sms |
| FEE | FMCDISPUTEIMGDMS | Dispute Image Fee Mc Dms |
| FEE | FSTARDISPUTEIMGSMS | Dispute Image Fee Star Sms |
| FEE | FVIDISPUTEIMGDMS | Dispute Image Fee Visa Dms |
| FEE | FDISPUTEMGMTMNTH | Dispute Man. Mthly. Fee |
| FEE | FDSPRGINTGCMBASB | Ds Pgrm Integrity Com Base Sub |
| FEE | FDSPRGINTGBASB | Ds Pgrm Integrity Fee Base Sub |
| FEE | FDSPREMMDQRETTXN | Ds Prem Midql Return Trns Fee |
| FEE | FDSPREMMDQSLSTXN | Ds Prem Midql Sales Trns Fee |
| FEE | FDSPREMMQRETDIS | Ds Prem Midqual Return Discnt |
| FEE | FDSPREMMQSLSDIS | Ds Prem Midqual Sls Discnt |
| FEE | FDSPREMNQRETTXN | Ds Prem Nonql Return Trns Fee |
| FEE | FDSPREMNQSLSTXN | Ds Prem Nonql Sales Trns Fee |
| FEE | FDSPREMNQRETDIS | Ds Prem Nonqual Return Discnt |
| FEE | FDSPREMNQSLSDIS | Ds Prem Nonqual Sls Discount |
| FEE | FDSPREMRETSDIS | Ds Premium Returns Discount |
| FEE | FDSPREMRETSTXN | Ds Premium Returns Trans Fee |
| FEE | FDSPREMSLSDIS | Ds Premium Sales Discount |
| FEE | FDSPREMSLSTXN | Ds Premium Sales Trans Fee |
| FEE | FEBTAUTH | Ebt Authorizations |
| FEE | FEBTBLNCINQ | Ebt Balance Inquiry |
| FEE | FEBTDCLN | Ebt Decline Fee |
| FEE | FEBTFDSTMPRTN | Ebt Food Stamp Return |
| FEE | FEBTFDSTMPRTNF02Y | Ebt Food Stamp Returns Fee |
| FEE | FEMFMNTH | Emf Monthly Fee |
| FEE | FEQPMT | Equipment Fees |
| FEE | FEQPMTWRNTY | Equipment Warranty Fee |
| FEE | FESPMNTH | Esp Monthly Fee |
| FEE | FESPNONCMPLNC | Esp Non Compliance |
| FEE | FEXECSSIVECHGBK | Excessive Chargeback Fee |
| FEE | FFDMOBILEPAYSETUP | Fd Mobilepay Setup |
| FEE | FFDMSDBTGTWY | Fdms Debit Gateway Fee |
| FEE | FFDMSOREDSGTWY | Fdms/Eds Gateway Fee |
| FEE | FFLATDSCNTMNTH | Flat Discount Fee |
| FEE | FFLEETCORAUTH | Fleetcor Auth Fee |
| FEE | FFLEETCORAUTHF0B3 | Fleetcor Authorization Fee |
| FEE | FFLEETCORLCLAUTH | Fleetcor Local Auth Fee |
| FEE | FFRAMERELAYMNTH | Frame Relay |
| FEE | FFRAUDMGMTPGM | Fraud Mgmt Program |
| FEE | FFRAUDFLXCSTMUSE | Fraud Services Custom Use Fee |
| FEE | FFRAUDFLXBASEMNTH | Fraud Services Monthly Fee B |
| FEE | FFRDFLXFULLMNTH | Fraud Services Monthly Fee F |
| FEE | FFRAUDFLXBASESETUP | Fraud Services Setup Fee B |
| FEE | FFRAUDFLXFULLSETUP | Fraud Services Setup Fee F |
| FEE | FFRDFLXBASETXN | Fraud Services Trans Fee B |
| FEE | FFRDFLXFULLTXN | Fraud Services Trans Fee F |
| FEE | FFRAUDWATCHMNTH | Fraud Watch Monthly Fee |
| FEE | FFRAUDWATCHSETUP | Fraud Watch Setup Fee |
| FEE | FGTWYACTVN | Gateway Activation Fee |
| FEE | FGTWYAUTHF36D | Gateway Auth Fee |
| FEE | FGTWYCHKTXN | Gateway Check Trx Fee |
| FEE | FGTWYMNTH | Gateway Monthly Fee Per Mid |
| FEE | FGTWYREACTVTN | Gateway Re Activation Fee |
| FEE | FGTWYSFTWR | Gateway/Software Fee |
| FEE | FGCACCTSETUP | Gc Account Set Up |
| FEE | FGCACHRJCT | Gc Ach Reject |
| FEE | FGCACHRTN | Gc Ach Return |
| FEE | FGCACHSETUP | Gc Ach Set Up Fee |
| FEE | FGCACHTXN | Gc Ach Transaction Fee |
| FEE | FGCACHTXNSRCHRG | Gc Ach Transaction Surcharge |
| FEE | FGCACTVTN | Gc Activation |
| FEE | FGCBLNCINQ | Gc Balance Inquiry |
| FEE | FGCBLKACTVN | Gc Block Activation Fee |
| FEE | FGCCLRANDIMGSETUP | Gc Color And Image Set Up |
| FEE | FGCDBINFOTXFR | Gc Database Info Transfer |
| FEE | FGCGRPHICDESIGN | Gc Graphic Design |
| FEE | FGCMNTHLYMIN | Gc Merchant Monthly Minimum |
| FEE | FGCACHMNTH | Gc Monthly Ach Fee |
| FEE | FGCMNTHF32V | Gc Monthly Fee |
| FEE | FGCORDRCNCL | Gc Order Cancellation |
| FEE | FGCOTHRTXN | Gc Other Transactions |
| FEE | FGCREDEMPTION | Gc Redemption |
| FEE | FGCRELOAD | Gc Reload |
| FEE | FGCSMIDTIERPGMMNTH | Gcs Midtr Pgm Mntly Fee |
| FEE | FGCSSMBPGMMNTH | Gcs Small Bsn Pgm Mntly |
| FEE | FGCSVCSETUP | Gc Service Fee Set Up |
| FEE | FGCVOIDRVSL | Gc Void/Reversal |
| FEE | FGCVRUUSG | Gc Vru Usage |
| FEE | FGCMNTH | Gift Card Monthly |
| FEE | FGCUNLMTDMNTH | Gift Card Unlimited Mnthly Fee |
| FEE | FYRPAYSETUP | Global Gateway Setup Fee |
| FEE | FYRPAYMNTHLYUSG | Global Gtway Monthly Usage Fee |
| FEE | FGOLDSVCPKG | Gold Service Fee |
| FEE | FGOOGLECHKOUTAUTH | Google Check Out Auth Fee |
| FEE | FGOOGLECHKOUTSLSTXN | Google Sales Trans Fee |
| FEE | FGPRSVENDINGNONMBLMNTH | Gprs Vend Non Mobil Mnth Fee |
| FEE | FGPRSVENDINGACTVN | Gprs Vending Activation Fee |
| FEE | FGPRSVENDINGDNLD | Gprs Vending Download Fee |
| FEE | FGRS | Grs Fee |
| FEE | FMCHOSTCAPTURE | Host Capture Fee |
| FEE | FAMEXHOSTCPTR | Host Capture Fee Amex |
| FEE | FAMXHOTELLNK | Hotel Link Amex Fee |
| FEE | FILTRLNKINOUTEXCEPTSMS | In/Out Except Sms Interlink |
| FEE | FACCELINOUTEXCEPTSMS | In/Outgoing Except Sms Accel |
| FEE | FACSINOUTEXCEPTSMS | In/Outgoing Except Sms Acs |
| FEE | FAFFNINOUTEXCEPTSMS | In/Outgoing Except Sms Affn |
| FEE | FATHINOUTEXCEPTSMS | In/Outgoing Except Sms Ath |
| FEE | FCU24INOUTEXCEPTSMS | In/Outgoing Except Sms Cu24 |
| FEE | FEFNINOUTEXCEPTSMS | In/Outgoing Except Sms Efunds |
| FEE | FJNEINOUTEXCEPTSMS | In/Outgoing Except Sms Jeanie |
| FEE | FMSTRINOUTEXCEPTSMS | In/Outgoing Except Sms Maestro |
| FEE | FNYCEINOUTEXCEPTSMS | In/Outgoing Except Sms Nyce |
| FEE | FPULSEINOUTEXCEPTSMS | In/Outgoing Except Sms Pulse |
| FEE | FSZMINOUTEXCEPTSMS | In/Outgoing Except Sms Shazam |
| FEE | FSTRINOUTEXCEPTSMS | In/Outgoing Except Sms Star |
| FEE | FVTLINOUTEXCEPTSMS | In/Outgoing Except Sms Vital |
| FEE | FILTRLNKINMERRESPSMS | Inc Merch Resp Sms Interlink |
| FEE | FINMERRESPDMS | Inc Merch Response Dms All |
| FEE | FAMXINMERRESPDMS | Inc Merch Response Dms Amex |
| FEE | FDSCVINMERRESPDMS | Inc Merch Response Dms Disc |
| FEE | FJCBINMERRESPDMS | Inc Merch Response Dms Jcb |
| FEE | FMCINMERRESPDMS | Inc Merch Response Dms Mc |
| FEE | FPVTLBLINMERRSPDMS | Inc Merch Response Dms Pl |
| FEE | FSTRINMERRSPDMS | Inc Merch Response Dms Star |
| FEE | FVIINMERRSPDMS | Inc Merch Response Dms Visa |
| FEE | FVOYINMERRSPDMS | Inc Merch Response Dms Voyage |
| FEE | FWEXINMERRSPDMS | Inc Merch Response Dms Wex |
| FEE | FACCELINMERRSPSMS | Inc Merch Response Sms Accel |
| FEE | FACSINMERRSPSMS | Inc Merch Response Sms Acs |
| FEE | FAFNINMERRSPSMS | Inc Merch Response Sms Affn |
| FEE | FATHINMERRSPSMS | Inc Merch Response Sms Ath |
| FEE | FCU24INMERRSPSMS | Inc Merch Response Sms Cu24 |
| FEE | FEFNINMERRSPSMS | Inc Merch Response Sms Efunds |
| FEE | FJNEINMERCRSPSMS | Inc Merch Response Sms Jeanie |
| FEE | FMSTRINMERMERRSPSMS | Inc Merch Response Sms Maestro |
| FEE | FNYCINMERRSPSMS | Inc Merch Response Sms Nyce |
| FEE | FPULSEINMERRSPSMS | Inc Merch Response Sms Pulse |
| FEE | FSHZINMERRSPSMS | Inc Merch Response Sms Shazam |
| FEE | FSTRINMERRSPSMS | Inc Merch Response Sms Star |
| FEE | FVTLINMERRSPSMS | Inc Merch Response Sms Vital |
| FEE | FACCELINCHGBKSMS | Incoming Cb Sms Accel |
| FEE | FACSINCHGBKSMS | Incoming Cb Sms Acs |
| FEE | FAFFNINCHGBKSMS | Incoming Cb Sms Affn |
| FEE | FATHINCHGBKSMS | Incoming Cb Sms Ath |
| FEE | FCU24INCHGBKSMS | Incoming Cb Sms Cu24 |
| FEE | FEFNINCHGBKSMS | Incoming Cb Sms Efunds |
| FEE | FINTRLNKINCHGBKSMS | Incoming Cb Sms Interlink |
| FEE | FJNEINCHGBKSMS | Incoming Cb Sms Jeanie |
| FEE | FMSTRINCHGBKSMS | Incoming Cb Sms Maestro |
| FEE | FNYCEINCHGBKSMS | Incoming Cb Sms Nyce |
| FEE | FPULSEINCHGBKSMS | Incoming Cb Sms Pulse |
| FEE | FSHZINCHGBKSMS | Incoming Cb Sms Shazam |
| FEE | FSTRINCHGBKSMS | Incoming Cb Sms Star |
| FEE | FVTLINCHGBKSMS | Incoming Cb Sms Vital |
| FEE | FAMXCHGBKDMS | Incoming Chargeback Dms Amex |
| FEE | FDSCVCHGBKDMS | Incoming Chargeback Dms Disc |
| FEE | FJCBCHGBKDMS | Incoming Chargeback Dms Jcb |
| FEE | FMCCHGBKDMS | Incoming Chargeback Dms Mc |
| FEE | FPVTLBLCHGBKDMS | Incoming Chargeback Dms Pl |
| FEE | FSTRCHGBKDMS | Incoming Chargeback Dms Star |
| FEE | FVICHGBKDMS | Incoming Chargeback Dms Visa |
| FEE | FVOYCHGBKDMS | Incoming Chargeback Dms Voyage |
| FEE | FWEXCHGBKDMS | Incoming Chargeback Dms Wex |
| FEE | FINCHGBKSMSFZ01 | Incoming Chargeback Sms |
| FEE | FINCHGBKSMS | Incoming Chargeback Sms |
| FEE | FINCHGBKDMS | Incoming Chargebacks All |
| FEE | FINMERRESPSMSFZ02 | Incoming Merchant Response Sms |
| FEE | FINMERRESPSMS | Incoming Merchant Response Sms |
| FEE | FINTRLNKINRTVLSMS | Incoming Retr Sms Interlink |
| FEE | FINRTVLSMS | Incoming Retrieval Sms |
| FEE | FACCELINRTVLSMS | Incoming Retrieval Sms Accel |
| FEE | FACSINRTVLSMS | Incoming Retrieval Sms Acs |
| FEE | FAFFNINRTVLSMS | Incoming Retrieval Sms Affn |
| FEE | FATHINRTVLSMS | Incoming Retrieval Sms Ath |
| FEE | FCU24INRTVLSMS | Incoming Retrieval Sms Cu24 |
| FEE | FEFNINRTVLSMS | Incoming Retrieval Sms Efunds |
| FEE | FJNEINRTVLSMS | Incoming Retrieval Sms Jeanie |
| FEE | FMSTRINRTVLSMS | Incoming Retrieval Sms Maestro |
| FEE | FNYCEINRTVLSMS | Incoming Retrieval Sms Nyce |
| FEE | FPULSEINRTVLSMS | Incoming Retrieval Sms Pulse |
| FEE | FSHZINRTVLSMS | Incoming Retrieval Sms Shazam |
| FEE | FSTRINRTVLSMS | Incoming Retrieval Sms Star |
| FEE | FVTLINRTVLSMS | Incoming Retrieval Sms Vital |
| FEE | FDSCVINOUTEXCPT | Incoming/Outgoing Except Disc |
| FEE | FMCINOUTEXCPT | Incoming/Outgoing Except Mc |
| FEE | FSTRINOUTEXCPT | Incoming/Outgoing Except Star |
| FEE | FVIINOUTEXCPT | Incoming/Outgoing Except Visa |
| FEE | FINGENICOMGMTMNTH | Ingenico Monthly Mgt Fee |
| FEE | FINSTL | Installation Fee |
| FEE | FINTRLNKDBTSLS | Interlink Debit Sale Fee |
| FEE | FINTRLNKINPREDISPUTESMS | Interlink Inc Predispute Sms |
| FEE | FINTRNTACCESS | Internet Access Fee |
| FEE | FINTRNTACCESSMNTH | Internet Monthly Access Fee |
| FEE | FINTRNTSETUP | Internet Set Up Fee |
| FEE | FINVCNOWACTVTN | Invoicenow Activation Fee |
| FEE | FINVCNOWMNTH | Invoicenow Monthly Fee Per Mid |
| FEE | FINVCNOWPERINVC | Invoicenow Per Invoice Fee |
| FEE | FJCB950AUTH | Jcb 950 Auth Fee |
| FEE | FJCBDCLN | Jcb Decline |
| FEE | FJCBDFLTAUTH | Jcb Default Auth Fee |
| FEE | FXBORDERLAC | Lac Cross Border Fee 1 |
| FEE | FXBORDERLACLCL | Lac Cross Border Fee 1, Local |
| FEE | FMCDMSTCLACAUTH | Lac Mc Domestic Auth Fee |
| FEE | FMCDMSTCLACLR | Lac Mc Domestic Clearing Fee |
| FEE | FMCINTLLACAUTH | Lac Mc Intl Authorization Fee |
| FEE | FMCINTLLACCLR | Lac Mc Intl Clearing Fee |
| FEE | FVILACACQRADMIN | Lac Vi Acquirer Admin Fee |
| FEE | FVILACDMSTCPROCESSING | Lac Vi Domestic Proc Fee |
| FEE | FVILACINTLAUSTAUTHREQ | Lac Vi Intl Auth Req Fee Ust |
| FEE | FVILACINTLAAUTHREQ | Lac Vi Intl Auth Request Fee |
| FEE | FVILACINTLPROCESSING | Lac Vi Intl Processing Fee |
| FEE | FVILACINTLUSTPROCESSING | Lac Vi Intl Processing Fee Ust |
| FEE | FINTLLACAPACQR | Lac/Ap Intl Acq Fee |
| FEE | FINTLLACAPCASHDISP | Lac/Ap Intl Cash Disp Fee |
| FEE | FVILATEACCPTDAY21TO25DMS | Late Accept Day 21 25 Visa Dms |
| FEE | FVILATEACCPTDAY21TO25SMS | Late Accept Day 21 25 Visa Sms |
| FEE | FVILATEACCPTDAY26TO30DMS | Late Accept Day 26 30 Visa Dms |
| FEE | FVILATEACCPTDAY26TO30SMS | Late Accept Day 26 30 Visa Sms |
| FEE | FLEVEL2SUPPRT | Level 2 Support Fee |
| FEE | FMENULOAD | Load Fee |
| FEE | FDSCVLOSTFILINGDMS | Lost Filing Dms Discover |
| FEE | FMCLOSTFILINGDMS | Lost Filing Dms Mastercard |
| FEE | FSTRLOSTFILINGDMS | Lost Filing Dms Star |
| FEE | FVILOSTFILINGDMS | Lost Filing Dms Visa |
| FEE | FLOSTFILINGSMS | Lost Filing Sms |
| FEE | FLOSTFILINGSMSFZ04 | Lost Filing Sms |
| FEE | FLLTYMEMBERWEBSITE | Loyalty Member Website |
| FEE | FLYLTSVCCALLCUSTMR | Loyalty Srv Call Customer |
| FEE | FLYLTSVCCALLMRCHNT | Loyalty Srv Call Merchant |
| FEE | FMCINTRNTAUTH | M/C Internet Auth Fee |
| FEE | FMC950AUTH | Mastercard 950 Auth Fee |
| FEE | FMCARULCLAUTH | Mastercard Aru Local Auth Fee |
| FEE | FMCARUWATSAUTH | Mastercard Aru Wats Auth Fee |
| FEE | FMCAUTH | Mastercard Auth Fee |
| FEE | FMCAUTOADDRVER | Mastercard Auto Address Verif |
| FEE | FMCBATCHAUTH | Mastercard Batch Authorization |
| FEE | FMCCPUAUTH | Mastercard Cpu Authorization |
| FEE | FMCDBTPERITEMFEE | Mastercard Debit Per Item Fee |
| FEE | FMCDBTPERITEMRATE | Mastercard Debit Pricing Rate |
| FEE | FMCDFLTAUTH | Mastercard Default Auth Fee |
| FEE | FMCECRADDRSVER | Mastercard Ecr Address Verif |
| FEE | FMCVOICEADDRVERAUTH | Mastercard Voice Addr Ver/Auth |
| FEE | FMCACCPTNOACCPT | Mc Accept/No Accept Fee |
| FEE | FMCACCPTPERMSG | Mc Access Per Message Fee |
| FEE | FMCACCTSTTSINQINTER | Mc Acct Status Inq Svc Interre |
| FEE | FMCACCTSTTSINQINTERREG | Mc Acct Status Inq Svc Interre |
| FEE | FMCACCTSTTSINQINTRAREG | Mc Acct Status Inq Svc Intrare |
| FEE | FMCACQRAVSBILING | Mc Acquirer Avs Billing |
| FEE | FMCANNUALLICENSEFEB | Mc Annual License Fee Feb |
| FEE | FMCANNUALLICENSESEP | Mc Annual License Fee Sept |
| FEE | FMCAPINTLASSMT | Mc Ap Intl Assessment Fee |
| FEE | FMCASSMTFEEGTEQ1KRTL | Mc Assessment Fee >=$1K |
| FEE | FMCASSMTFEEGTEQ1KWHLSL | Mc Assessmnt Fee >=$1K Wholsle |
| FEE | FMCAUTHCNCTVTY | Mc Auth Connectivity Fee |
| FEE | FMCAUTHSUSPCTFRAUDRVSL | Mc Auth Suspect Fraud Reversal |
| FEE | FMCAUTOBILLINGUPDTMNTH | Mc Auto Billing Upd Mth Fee |
| FEE | FMCAUTOBILLINGUPDTTXN | Mc Auto Billing Upd Tran Fee |
| FEE | FMCCHGBKFAXEMAILRECD | Mc Cb Excpt Recd Fax/Mail |
| FEE | FMCCHGBKFAXEMAILPKG | Mc Cb/Excpt Package Fax/Mail |
| FEE | FMCCLEARINGCNCTVTY | Mc Clearing Connectivity Fee |
| FEE | FMCTAXSVC | Mc Comm Card I/C Savings Adj |
| FEE | FMCCNCTVTYAUTH | Mc Connectivity Auth Fee |
| FEE | FMCCVC2TXN | Mc Cvc2 Transaction Fee |
| FEE | FMCDBTBILBKREDUCTION | Mc Debit Billback Reduction |
| FEE | FMCFREIGHTPRGM | Mc Freight Prgm Fee |
| FEE | FMCGLBLWHLSLTRVB2B | Mc Glbl Wholesale Trav B2B Fee |
| FEE | FMCGLBLACQR | Mc Global Acquirer Fee |
| FEE | FMCCASHASSESGUAMNMI | Mc Guam/Nmi Cash Assess Fee |
| FEE | FMCCRDTASSESSGUAMNMI | Mc Guam/Nmi Credit Assess Fee |
| FEE | FMCINSTLPRGMPRCHSINSA | Mc Instlmt Prog Fee Pur Insa |
| FEE | FMCINSTLPRGMPRCHSINSB | Mc Instlmt Prog Fee Pur Insb |
| FEE | FMCINSTLPRGMPRCHSINSC | Mc Instlmt Prog Fee Pur Insc |
| FEE | FMCINSTLPRGMRFNDINSA | Mc Instlmt Prog Fee Ref Insa |
| FEE | FMCINSTLPRGMRFNDINSB | Mc Instlmt Prog Fee Ref Insb |
| FEE | FMCINSTLPRGMRFNDINSC | Mc Instlmt Prog Fee Ref Insc |
| FEE | FMCICDOWNGRADE | Mc Interchange Downgrade Fee |
| FEE | FMCIRAMTXN | Mc Iram Transaction Fee |
| FEE | FMCNONAUTHLAC | Mc Lac Non Authentication Fee |
| FEE | FMCPREAUTHDMSTCLAC | Mc Lac Preauth Fee Dom |
| FEE | FMCPREAUTHDXBORDERLAC | Mc Lac Preauth Fee Xbor |
| FEE | FMCLATERESP | Mc Late Response Fee |
| FEE | FMCLICENSEPERITEM | Mc License Per Item Fee |
| FEE | FMCMERCHANNUALLOCAPR | Mc Merch Annual Location Fee |
| FEE | FMCMERCHANNUALLOCJAN | Mc Merch Annual Location Fee |
| FEE | FMCMERCHANNUALLOC | Mc Merch Location Fee |
| FEE | FMCMERCHLOCMNTH | Mc Merch Monthly Location Fee |
| FEE | FMCLOCMNTH | Mc Monthly Location Fee |
| FEE | FMCMRPANNUAL | Mc Mrp Annual Fee |
| FEE | FMCLICENSEMNTH | Mc Mthly License Fee |
| FEE | FMCNTWRKACCESSSAUTH | Mc Network Access Auth Fee |
| FEE | FMCPIFDTLRPT | Mc Pif Detail Report |
| FEE | FMCPIFFINALORPREAUTHMIN | Mc Pif Final/Pre Auth Min |
| FEE | FMCPRASSMTDBPP | Mc Pr Assessment Fee Db/Pp |
| FEE | FMCPIFINALAUTH | Mc Proc Integ Final Auth |
| FEE | FMCPIFPREAUTH | Mc Proc Integ Pre Auth |
| FEE | FMCPIFUNDEFAUTH | Mc Proc Integ Undef Auth |
| FEE | FMCPRCSINGINTGRTY | Mc Processing Integrity Fee |
| FEE | FMCRTVLFAXMAILCRSPND | Mc Retr Correspond Fax/Mail |
| FEE | FMCRTVLFAXMAILCRCD | Mc Retr Recd Fax/Mail |
| FEE | FMCTPEACQRADVC | Mc Tpe Acq Merch Advice Code |
| FEE | FMCTPEEXCSVAUTH | Mc Tpe Excessive Auth |
| FEE | FMCTPENOMINALAMTAUTH | Mc Tpe Nominal Amnt Auth |
| FEE | FMCUSVIASSMT | Mc Usvi Assessment Fee |
| FEE | FMCUSVIINTLASSMT | Mc Usvi Intl Assessment Fee |
| FEE | FMCVOICEAUTHRFRL | Mc Voice Auth Issuer Referral |
| FEE | FMCAUTHDGTLENBLMNT | Mc Auth Digital Enablement Fee |
| FEE | FMCAUTHDGTLENBLMNTMAX | Mc Auth Digital Enablement Max |
| FEE | FMCAUTHDGTLENBLMNTMIN | Mc Auth Digital Enablement Min |
| FEE | FMCCRDTNLCNTNTY | Mc Credential Continuity Fee |
| FEE | FMCDCLNRSNCDSVC | Mc Decline Reason Code Svc Fee |
| FEE | FMEETINMIDDLECNCTN | Meet In Middle Connection |
| FEE | FMERCHOWNPLAN | Merch Own Plan |
| FEE | FVIMERCHRESPDAY21TO25DMS | Merch Rsp Day 21 25 Visa Dms |
| FEE | FVIMERCHRESPDAY21TO25SMS | Merch Rsp Day 21 25 Visa Sms |
| FEE | FVIMERCHRESPDAY26TO30DMS | Merch Rsp Day 26 30 Visa Dms |
| FEE | FVIMERCHRESPDAY26TO30SMS | Merch Rsp Day 26 30 Visa Sms |
| FEE | FVIMERCHRESPSMS | Merchan Rsp Fee Visa Sms |
| FEE | FVIMERCHRESPDAY01TO20DMS | Merchant Rsp Day 1 20 Visa Dms |
| FEE | FVIMERCHRESPDAY01TO20SMS | Merchant Rsp Day 1 20 Visa Sms |
| FEE | FVIMERCHRESPDMS | Merchant Rsp Fee Visa Dms |
| FEE | FGTWYCHKMNTH | Mo. Gateway Check Fee |
| FEE | FMOBLPYMNTMNTH | Mobile Payments Monthly Fee |
| FEE | FMOBLPYMNTSETUP | Mobile Payments Set Up Fee |
| FEE | FCLNTLNMNTH | Monthly Clientline Fee |
| FEE | FDISPUTEMGRMTH | Monthly Disp Mgr Fee |
| FEE | FFILEDLVRYMNTH | Monthly File Delivery Fee |
| FEE | FINTGRTDPYMNTMNTH | Monthly Integrated Payment Fee |
| FEE | FMINREBATEMNTH | Monthly Minimum Rebate |
| FEE | FONLNINQMNTH | Monthly Online Inquiry Fee |
| FEE | FRISKMNTH | Monthly Risk Fee |
| FEE | FSVCMNTH | Monthly Service Fee |
| FEE | FSMRTRTNGMNTH | Monthly Smart Routing Fee |
| FEE | FSUPPRTMNTH | Monthly Support Fee |
| FEE | FWIRELESSMNTH | Monthly Wireless Fee |
| FEE | FMPAYGTWYMNTH | Mpay Gateway Monthly Fee |
| FEE | FNTWKAUTH | Network Authorization Fee |
| FEE | FNTWKTKNPERPROVISION | Network Token Per Provision |
| FEE | FNTWKTKNPERTXN | Network Token Per Trans Fee |
| FEE | FINTRLNKNOACCPTSMS | No Acceptance Interlink Sms |
| FEE | FVINOACCPTDMS | No Acceptance Visa Dms |
| FEE | FNONBNKCARD | Non Bankcard Fee |
| FEE | FNONSWIPEDDSCNT | Non Swiped Discount |
| FEE | FNONSWIPEDTXN | Non Swiped Transaction Fee |
| FEE | FNONQUALICSRCHRG | Nonqual Interchange Surcharge |
| FEE | FPCICMPLNONVLDTN | Non Validation Pci Compliance |
| FEE | FINTLNKNWACCPTDAY00TO20SMS | Nw Acpt Day 0 20 Interlink Sms |
| FEE | FINTLNKNWCASEFILINGSMS | Nw Case Filing Fee Interlink |
| FEE | FMSTRNWCASEFILINGSMS | Nw Case Filing Fee Maestro Sms |
| FEE | FMCNWCASEFILINGDMS | Nw Case Filing Fee Mc Dms |
| FEE | FSZMNWCASEFILINGSMS | Nw Case Filing Fee Shazam Sms |
| FEE | FVINWCASEFILINGDMS | Nw Case Filing Fee Visa Dms |
| FEE | FMSTRNWCASEFILINGWDSMS | Nw Case Filing Wd Maestro Sms |
| FEE | FMCNWCASEFILINGWDDMS | Nw Case Filing Wd Mc Dms |
| FEE | FPULSENWCASEFILINGWDSMS | Nw Case Filing Wd Pulse Sms |
| FEE | FACCELNWCASERULNGSMS | Nw Case Ruling Fee Accel Sms |
| FEE | FINTLNKNWCASERULNGSMS | Nw Case Ruling Fee Interlink |
| FEE | FMSTRNWCASERULNGSMS | Nw Case Ruling Fee Maestro Sms |
| FEE | FMCNWCASERULNGDMS | Nw Case Ruling Fee Mc Dms |
| FEE | FPULSENWCASERULNGSMS | Nw Case Ruling Fee Pulse Sms |
| FEE | FSZMNWCASERULNGSMS | Nw Case Ruling Fee Shazam Sms |
| FEE | FSTRNWCASERULNGSMS | Nw Case Ruling Fee Star Sms |
| FEE | FVINWCASERULNGDMS | Nw Case Ruling Fee Visa Dms |
| FEE | FACCELNWCHGBKRPSMNTSMS | Nw Cb Representment Accel Sms |
| FEE | FNYCENWCHGBKRPSMNTSMS | Nw Cb Representment Nyce Sms |
| FEE | FPULSENWCHGBKRPSMNTSMS | Nw Cb Representment Pulse Sms |
| FEE | FSZMNWCHGBKRPSMNTSMS | Nw Cb Representment Shazam Sms |
| FEE | FVTLNWCHGBKRPSMNTSMS | Nw Cb Representment Vital Sms |
| FEE | FACCELNWCOPYREQSMS | Nw Copy Request Accel Sms |
| FEE | FMCDISPUTEEXCSVPGEDMS | Nw Dispute Excssive Pge Mc Dms |
| FEE | FNWDISPUTIMGFEESMS | Nw Dispute Image Fee Sms |
| FEE | FNWDISPUTIMGFEESMSF48I | Nw Dispute Image Fee Smss |
| FEE | FNYCENWINRPSMNTDNLSMS | Nw Inc Rep Denial Nyce Sms |
| FEE | FNYCENWINRPSMNTDNLRVSLSMS | Nw Inc Rep Denial Rev Nyce Sms |
| FEE | FACCELNWINCHGBKSMS | Nw Incoming Cb Accel Sms |
| FEE | FACSNWINCHGBKSMS | Nw Incoming Cb Acs Sms |
| FEE | FAFFNNWINCHGBKSMS | Nw Incoming Cb Affn Sms |
| FEE | FATHNWINCHGBKSMS | Nw Incoming Cb Ath Sms |
| FEE | FCU24NWINCHGBKSMS | Nw Incoming Cb Cu24 Sms |
| FEE | FEFNDSNWINCHGBKSMS | Nw Incoming Cb Efunds Sms |
| FEE | FINTLNKNWINCHGBKSMS | Nw Incoming Cb Interlink Sms |
| FEE | FNYCNWINCHGBKSMS | Nw Incoming Cb Jeanie Sms |
| FEE | FJNENWINCHGBKSMS | Nw Incoming Cb Nyce Sms |
| FEE | FPULSENWINCHGBKSMS | Nw Incoming Cb Pulse Sms |
| FEE | FSZMNWINCHGBKSMS | Nw Incoming Cb Shazam Sms |
| FEE | FSTRNWINCHGBKSMS | Nw Incoming Cb Star Sms |
| FEE | FVTLNWINCHGBKSMS | Nw Incoming Cb Vital Sms |
| FEE | FPULSENWINEXCEPTSMS | Nw Incoming Except Pulse Sms |
| FEE | FVILATEACCTPDAY0TO20DMS | Nw Late Acpt Day 0 20 Visa Dms |
| FEE | FMCNWPREARBTNACCPT | Nw Mc Pre Arbitration Acpt Fee |
| FEE | FACCELNWOUTEXCPTSMS | Nw Outgoing Except Accel Sms |
| FEE | FAFFNNWOUTEXCPTSMS | Nw Outgoing Except Affn Sms |
| FEE | FMSTRNWOUTEXCPTSMS | Nw Outgoing Except Maestro Sm |
| FEE | FVINWPRCOMPIMGDMS | Nw Precomp Image Fee Visa Dm |
| FEE | FSTRRTVLFLFLMNTSMS | Nw Retr Fulfillment Star Sms |
| FEE | FINTLNKNWRTVLNFLMNT | Nw Retr Nonfulfill Interlink |
| FEE | FVINWRTVLNONFLFLMNTDMS | Nw Retr Nonfulfill Visa Dms |
| FEE | FPULSENWRTVLNFLMNT | Nw Retr Nonfulfillment Pulse |
| FEE | FVINWRTVLDMS | Nw Retrieval Visa Dms |
| FEE | FDSCVNWTCKTRTVLREQDMS | Nw Ticket Rtr Request Disc Dms |
| FEE | FVINWPREARBTCNPRMDYDMS | Nw Visa Prearb Cnp Remedy Dms |
| FEE | FNYCEFILE | Nyce File Fee |
| FEE | FONERTLODGING | Onerate Lodging |
| FEE | FONERTMOTOAVSANDECOM | Onerate Moto W/Avs And E Comm |
| FEE | FONERATEREST | Onerate Restaurant |
| FEE | FONERATERETAIL | Onerate Retail |
| FEE | FONLNDBTDNL | Online Debit Denial |
| FEE | FOTHRRVNURBT | Other Revenue Rebates |
| FEE | FCHGBKOUTCORREXCEPT | Outgoing Corr Cb/Except |
| FEE | FSTRCHGBKOUTCORREXCEPT | Outgoing Corr Cb/Except Star |
| FEE | FRTVLOUTCORREXCEPT | Outgoing Corr Retrieval |
| FEE | FSTRRTVLOUTCORREXCEPT | Outgoing Corr Retrieval Star |
| FEE | FPLATERMNTH | Pay Later Monthly Fee |
| FEE | FPZYAUTH | Payeezy Authorization Fee |
| FEE | FPZYMNTH | Payeezy Monthly Fee |
| FEE | FPZYSETUP | Payeezy Setup Fee |
| FEE | FPYMNTESSNTLSVCPKG | Payment Essentials Svs Fee Pkg |
| FEE | FPYPLASSMNTF45H | Paypal Assessment Fee |
| FEE | FPYPLAUTH | Paypal Authorization Fee |
| FEE | FPYPLAUTHF45U | Paypal Authorization Fee |
| FEE | FPYPLNTWKAUTH | Paypal Network Auth Fee |
| FEE | FPYPLRETTXN | Paypal Return Trans Fee |
| FEE | FPYPLSLSTXN | Paypal Sales Trans Fee |
| FEE | FPYPLSLSTXNF13A | Paypal Sales Trans Fee |
| FEE | FPYPLSLSTXNF45V | Paypal Sales Trans Fee |
| FEE | FPAYWRMOBSVCMNTH | Payware Mobile Monthly Svc Fee |
| FEE | FPAYWRMOBSETUP | Payware Mobile Setup Fee |
| FEE | FPAYWRMOBTXN | Payware Mobile Transaction Fee |
| FEE | FPYPLTERMBLNG | Payy Terminal Billing Fee |
| FEE | FPCCHRGANNUAL | Pc Charge Annual Fee |
| FEE | FPCARDLEVELIIIAUTH | Pcard Level Iii Auth Fee |
| FEE | FPCICMPLSVCPGM | Pci Compliance Service Pgm Fee |
| FEE | FPCICMPLANNUAL | Pci Complyally Annual |
| FEE | FPCICMPLMNTH | Pci Complyally Monthly |
| FEE | FPCIDSSCMPLADMIN | Pci Dss Compliance Admin Fee |
| FEE | FPCICMPLSUPRTPKG | Pci Support Package |
| FEE | FPERKASOLN | Perka Solution |
| FEE | FPFACANNUALREVW | Pfac Annual Review Fee |
| FEE | FPFACUNDRWRTNG | Pfac Underwriting Fee |
| FEE | FMCPFACUNDRWRTNG1MPLUS | Pfac Underwriting Fee Mc 1M+ |
| FEE | FPINDBTBLNCINQNTWK | Pin Debit Bal Inq Network Fee |
| FEE | FPINDBTDNL | Pin Debit Denial |
| FEE | FDBTCMBRETDSCNT | Pin/Sig/Credit Ret Discount |
| FEE | FDBTCMBSLSDSCNT | Pin/Sig/Credit Sales Discount |
| FEE | FDBTCMBSLSTXN | Pin/Sig/Credit Sales Trans Fee |
| FEE | FPINDBTBTCHSTLMNT | Pin Debit Batch Settlements |
| FEE | FPNLSCHGBKDSCNT | Pinless Chargeback Discount |
| FEE | FPNLSDBTAUTH | Pinless Debit Auth Fee |
| FEE | FPNLSDBTDCLN | Pinless Debit Decline Fee |
| FEE | FPNLSDBTDNL | Pinless Debit Denial |
| FEE | FPNLSDBTTXN | Pinless Debit Transaction Fee |
| FEE | FPNLSDBTIC | Pinless Interchange Fee |
| FEE | FPNLSDBTRETDSCNT | Pinless Returns Discount |
| FEE | FPNLSDBTRTVLDSCNT | Pinless Reversal Discount |
| FEE | FPNLSDBTSLSDSCNT | Pinless Sales Discount |
| FEE | FPLTFRMACCSSMNTH | Platform Access Monthly Fee |
| FEE | FPLTNMSVCPKGF40C | Platinum Service Fee |
| FEE | FPORTFLOMGR | Portfolio Manager |
| FEE | FPRMEQPSVCPGM | Premium Equipment Svc Program |
| FEE | FPVTLBL950AUTH | Private Label 950 Auth Fee |
| FEE | FAMEXPRGRMCOST | Program Cost Fee Ax |
| FEE | FPRMSNLSTMTCRDT | Promotional Credit |
| FEE | FPRMSNLPGMRBT | Promotional Program Rebate |
| FEE | FPRMSNLRBTB | Promotional Rebate B |
| FEE | FQSRCSTRSMLTKT | Qsr, C Store, Sml Tkt. |
| FEE | FQUARTERLYMNTNC | Quarterly Maintenance Fee |
| FEE | FPRMSNLRBTUPTO1000 | Rebate Up To 1000 |
| FEE | FREFUSLOFDATA | Refusal Of Data Fee |
| FEE | FREGDBTRETDSCNT | Reg Debit Returns Disc |
| FEE | FREGDBTRETTXN | Reg Debit Returns Trans Fee |
| FEE | FREGDBTSLSDSCNT | Reg Debit Sales Disc |
| FEE | FREGDBTSLSTXN | Reg Debit Sales Trans Fee |
| FEE | FREGPINDBTSLSDSCNT | Reg Pin Debit Sales Discount |
| FEE | FREGPINDBTSLSTXN | Reg Pin Debit Sales Tran Fee |
| FEE | FREGSIGDBTAUTHFS | Reg Sig Debit Auth Fee Fs |
| FEE | FREGSIGDBTRETTXN | Reg Sig Debit Ret Tran Fee |
| FEE | FREGSIGDBTRETDSCNT | Reg Sig Debit Returns Disc |
| FEE | FREGSIGDBTSLSDSCNT | Reg Sig Debit Sales Disc |
| FEE | FREGSIGDBTSLSTXN | Reg Sig Debit Sales Tran Fee |
| FEE | FRGLTRYPRDCT | Regulatory Product Fee |
| FEE | FRELEVANTSRCHMNTH | Relevant Search Monthly Fee |
| FEE | FRELEVANTSRCHSETUP | Relevant Search Set Up Fee |
| FEE | FEQPRENTALMNTH | Rental Fee |
| FEE | FEQPRENTAL | Rental Fee |
| FEE | FRTVLFAXEMAIL | Retrieval Fax/Mail |
| FEE | FSTRRTVLFAXEMAIL | Retrieval Fax/Mail Star |
| FEE | FRWRDSSURCHRGOPTNONE | Rewards Surcharge Option 1 |
| FEE | FSLSTXN | Sales Transaction Fee |
| FEE | FSAMEDAYACH | Same Day Ach Fee |
| FEE | FSAMEDAYACHVOL | Same Day Ach Volume Fee |
| FEE | FSECURECODETXN | Securecode Transaction Fee |
| FEE | FSIGDBTACCESS | Sig Debit Access Fee |
| FEE | FSIGDBTADDRSVER | Sig Debit Address Verif Fee |
| FEE | FSIGDBTBLBK | Sig Debit Billback |
| FEE | FSIGDBTELECAUTH | Sig Debit Electronic Auth Fee |
| FEE | FSIGDBTICF57E | Sig Debit Interchange |
| FEE | FSIGDBTMQRETTXN | Sig Debit Mid Qual Return Tran |
| FEE | FSIGDBTMQSLSDSCNT | Sig Debit Mid Qual Sales Disc |
| FEE | FSIGDBTMQSLSTXN | Sig Debit Mid Qual Sales Tran |
| FEE | FSIGDBTNQRETTXN | Sig Debit Non Qual Rtrn Trans |
| FEE | FSIGDBTNQSLSDSCNT | Sig Debit Non Qual Sales Disc |
| FEE | FSIGDBTNQSLSTXN | Sig Debit Non Qual Sales Trans |
| FEE | FSIGDBTRETDSCNT | Sig Debit Returns Discount |
| FEE | FSITEVISIT | Site Visitation |
| FEE | FSKIPJACKMNTH | Skipjack Monthly Fee |
| FEE | FSKIPJACKSETUP | Skipjack Setup Fee |
| FEE | FSMFUNDING | Sm Funding Fee |
| FEE | FSMRSKMNTRNGFULL | Sm Risk Monitoring Fee Full |
| FEE | FSMRSKMNTRNGPARTIAL | Sm Risk Monitoring Fee Partial |
| FEE | FSMARTROUTINGAUTH | Smart Routing Auth Fee |
| FEE | FSMARTROUTINGLICNS | Smart Routing License Fee |
| FEE | FSSTACCTIVATION | Sst Activation Fee |
| FEE | FSSTCNTCTLSMRKTNG | Sst Future |
| FEE | FSTRECLASS | St Reclass Fee |
| FEE | FSTRREFUNDTXN | St Refund Per Trans Fee |
| FEE | FSTRTKNEXCHG | St Token Exchange Fee |
| FEE | FSTRDECLN | Star Access Auth Decline Fee |
| FEE | FSTRCNPPERTRANBPS | Star Access Cnp Per Tran Bps |
| FEE | FSTRCNPPERTRAN | Star Access Cnp Per Tran Fee |
| FEE | FSTRCPPERTRAN | Star Access Per Tran Cp |
| FEE | FSTRAUTHREQ | Star Auth Request Fee |
| FEE | FSTRAUTHRVSLREQ | Star Auth Reversal Fee |
| FEE | FSTRDBTTKNEXCHG | Star Token Exchange Debit Fee |
| FEE | FSPNDTRNDSTMT | Statement Spendtrend Fee |
| FEE | FSTRDVLAUTH | Stored Value Authorization Fee |
| FEE | FSTRDVLMNTH | Stored Value Monthly Fee |
| FEE | FSTRDVLSETUP | Stored Value Set Up Fee |
| FEE | FSUPPRTPKGMNTH | Support Package Fee |
| FEE | FSVLVAGNTMNT | Sv Live Agent Minute |
| FEE | FSWIPEDDSCNTF23Z | Swiped Discount |
| FEE | FTAXALLOC | Tax Allocation |
| FEE | FTAXALLOCDEPOST | Tax Allocation Deposit |
| FEE | FTCKCROC | Tck Croc Fee |
| FEE | FTCKINPRSNWRNTYMINMNTH | Tck In Person Wrntd Mthly Min |
| FEE | FTCKPAPRNOWRNTYMINMNTH | Tck Paper Non Wrntd Mnthly Min |
| FEE | FTCKPAPRWRNTYMINMNTH | Tck Paper Wrntd Mnthly Min |
| FEE | FTCKVOICEAUTH | Tck Voice Auth Fee |
| FEE | FTECHMNTNCANNUAL | Technical Maint Annual Fee |
| FEE | FTECHMNTNCMNTH | Technical Maint Mthly Fee |
| FEE | FTCKINQRATE | Telecheck Inquiry Rate |
| FEE | FTCKMTHLYFLAT | Telecheck Monthly Flat Fee |
| FEE | FTCKTRDTNLMINMNTH | Telecheck Monthly Minimum |
| FEE | FTCKTXN | Telecheck Transaction Fee |
| FEE | FTERMMGMTMNTH | Terminal Management |
| FEE | FTERMTRAINING | Terminal Training Fee |
| FEE | FTRMNTN12MNTH | Termination Fee 12 Mnth |
| FEE | FTRMNTN13TO24MNTH | Termination Fee 13 24 Mnth |
| FEE | FTAENCRYPTONLY | Transarmor Encrypt Only |
| FEE | FTAENCRYPTONLYVF | Transarmor Encrypt Only Vf |
| FEE | FTAENCRYPTONLY3DES | Transarmor Tkn Encrypt 3Des |
| FEE | FTATKNONLY | Transarmor Token Only |
| FEE | FTATKNRGSTRN | Transarmor Token Registration |
| FEE | FVLTPERMIDMNTH | Vault Monthly Fee Per Mid |
| FEE | FVETRNFREEDAYPRCCSSNGRBT | Vet Free Day Processing Rebate |
| FEE | FVIACCTUPDMNTHLY | Vi Acct Upd Mnthly Fee |
| FEE | FVIACQRB2BVIRTSVCDMSTC | Vi Acq B2B Virtual Svc Fee Dom |
| FEE | FVIACQRB2BVIRTSVCDINTL | Vi Acq B2B Virtual Svcfee Intl |
| FEE | FVIACQRB2BVIRTSVCDINTRA | Vi Acqb2B Virtual Svcfee Intra |
| FEE | FVIVBASSANNUAL | Vi Annual Vbass Fee |
| FEE | FVIBASE2CRDVCHRCRDT | Vi Base Ii Cr Vcher Fee Us Cr |
| FEE | FVIBASE2CRDVCHRDBT | Vi Base Ii Cr Vcher Fee Us D/P |
| FEE | FVIBASE2CRDVCHRCRDTINTL | Vi Base Ii Crvcher Fee Intl Cr |
| FEE | FVIBASE2CRDVCHRDBTINTL | Vi Base Ii Crvcherfee Intl D/P |
| FEE | FVIBASE2SYSTEMFILE | Vi Base Ii System File Fee |
| FEE | FVICHKCARDBLBKRDCTN | Vi Chkcard Billback Reduction |
| FEE | FVICOMCARDICSVNGSADJ | Vi Comm Card I/C Savings Adj |
| FEE | FVICVV2 | Vi Cvv2 Result M Or N Fee |
| FEE | FVIDATAQLTY | Vi Data Quality Fee |
| FEE | FVIDATACONSXBRDR | Vi Data Quality Fee Xbor |
| FEE | FVIDCLNTXNRESUB | Vi Decline Tran Resub Fee |
| FEE | FVIDCLNTXNRESUBXBRDR | Vi Decline Tran Resub Fee Xbor |
| FEE | FVIESTMTDAUTH | Vi Estimated Auth Fee |
| FEE | FVICRDTASSESGUAMNMI | Vi Guam/Nmi Credit Assess Fee |
| FEE | FVIINCRAUTH | Vi Incremental Auth Fee |
| FEE | FVIINTGRTYDTLRPT | Vi Integrity Fee Detail Report |
| FEE | FVIMAGSTRPCNTCTLS | Vi Mag Stripe Contactless Fee |
| FEE | FVIMANCASHSWITCH | Vi Manual Cash Switch Fee |
| FEE | FVINEVERAPPRVDRATMPTXBRDR | Vi Never Approve Reatt Xborfee |
| FEE | FVINEVERAPPRVDRATMPT | Vi Never Approve Reattempt Fee |
| FEE | FVINTWKACQRPRCSSNGCRDTINTL | Vi Ntwk Acq Proc Fee Intl Cr |
| FEE | FVINTWKACQRPRCSSNGDBTINTL | Vi Ntwk Acq Proc Fee Intl D/P |
| FEE | FVINTWKACQRPRCSSNGCRDT | Vi Ntwk Acq Proc Fee Us Cr |
| FEE | FVINTWKACQRPRCSSNGDBT | Vi Ntwk Acq Proc Fee Us Db/Pp |
| FEE | FVISTGEDDGTLWALLET | Vi Staged Digital Wallet Fee |
| FEE | FVIUSCBPSPRTCPTN | Vi Us Cbps Participation Fee |
| FEE | FVIUSCRDTASSMNT | Vi Usvi Credit Assessment Fee |
| FEE | FVIADDRVERSVC | Vi Address Ver Svc Fee |
| FEE | FVIAPINTLASSMNTBASE | Vi Ap Intl Assessment Bse |
| FEE | FVIAPINTLASSMNTENHNCD | Vi Ap Intl Assessment Enh |
| FEE | FVIBASE2RET | Vi Base 2 Return Fee |
| FEE | FVICANINTACQRMLTICRNCYSVC | Vi Can Int Acq Svcfee Mult Cur |
| FEE | FVICANINTACQRSNGLCRNCYSVC | Vi Can Int Acq Svcfee Sing Cur |
| FEE | FVIEXCSVCHPFLBK | Vi Excessive Chip Fallback Fee |
| FEE | FVILACSECRCFNONTKN | Vi Lac Secure Cf Non Token Fee |
| FEE | FVIMRKTPLCPRGM | Vi Marketplace Program Fee |
| FEE | FVI950AUTH | Visa 950 Auth Fee |
| FEE | FVIACCPTNOACCPT | Visa Accept/No Accept Fee |
| FEE | FVIACCESSPERMSG | Visa Access Per Message Fee |
| FEE | FVIARULCLAUTH | Visa Aru Local Auth Fee |
| FEE | FVIARUWATSAUTH | Visa Aru Wats Auth Fee |
| FEE | FVIAUTH | Visa Auth Fee |
| FEE | FVIAUTOACCPT | Visa Auto Acceptance |
| FEE | FVIAUTOADDRVERIF | Visa Auto Address Verif |
| FEE | FVIBTCHAUTH | Visa Batch Authorization |
| FEE | FVICHGBKFAXEMAILRECD | Visa Cb Excpt Recd Fax/Mail |
| FEE | FVICHGBKFAXEMAILPKG | Visa Cb/Excpt Package Fax/Mail |
| FEE | FVICNCTVTYAUTH | Visa Connectivity Auth Fee |
| FEE | FVICPUAUTH | Visa Cpu Authorization |
| FEE | FVIDBTPERITEMFEE | Visa Debit Per Item Fee |
| FEE | FVIDBTPRCNGRATE | Visa Debit Pricing Rate |
| FEE | FVIDFLTAUTH | Visa Default Auth Fee |
| FEE | FVIECRADDRSVER | Visa Ecr Address Verification |
| FEE | FVIFRAUDRMDYDMS | Visa Fraud Remedy Merchant Dms |
| FEE | FVIFRAUDRMDYUPFRNTDMS | Visa Fraud Remedy Upfront Dms |
| FEE | FVIHIGHRISKANNUAL | Visa High Risk Annual Fee |
| FEE | FVIINPREDISPTDMS | Visa Incoming Predispute Dms |
| FEE | FVIINTRNTAUTH | Visa Internet Auth Fee |
| FEE | FVISVCBASEINT | Visa Intl Service Fee Base |
| FEE | FVISVCENHNCDINT | Visa Intl Service Fee Enh |
| FEE | FVICASHADVNCSVCINTL | Visa Intl Srvce Fee Cash Adv |
| FEE | FVILACNTASSMT | Visa Lac Intl Assessment Fee |
| FEE | FVILATEACCPTDAY21TO25 | Visa Late Accept 21 25 Days |
| FEE | FVILATEACCPTDAY26TO30 | Visa Late Accept 26 30 Days |
| FEE | FVIMISUSEOFAUTH | Visa Misuse Of Auth Fee |
| FEE | FVINTWKCNPFNF2 | Visa Network Fee Cnp Xx Xx |
| FEE | FVINTWKCNPFNF6 | Visa Network Fee Cnp Xx Xx |
| FEE | FVINOACCPTNC | Visa No Acceptance |
| FEE | FVIPRTLAUTHNPTXN | Visa Partial Auth Np Trans Fee |
| FEE | FVIPRCASHASSMNT | Visa Pr Cash Assessment Fee |
| FEE | FVIPRCRDTASSMNT | Visa Pr Credit Assessment Fee |
| FEE | FVIPRDBTASSMNT | Visa Pr Debit Assessment Fee |
| FEE | FVIRTVLFAXMAILCRSPND | Visa Retr Correspond Fax/Mail |
| FEE | FVIRTVLFAXMAILCRCD | Visa Retr Recd Fax/Mail |
| FEE | FVISTPPYMNTSVC | Visa Stop Payment Service Fee |
| FEE | FVIUSVICASHASSMT | Visa Usvi Cash Assessment Fee |
| FEE | FVIUSVIDBTASSMT | Visa Usvi Debit Assessment Fee |
| FEE | FVIVOICEADDRVERAUTH | Visa Voice Addr Verif/Auth |
| FEE | FVIVOICEAUTH | Visa Voice Auth Fee |
| FEE | FVIVOICEAUTHRFRL | Visa Voice Auth Issuer Refer |
| FEE | FVIZEROAMTVER | Visa Zero Acct Ver Db Fee |
| FEE | FVIZEROFLOORLIMIT | Visa Zero Floor Limit Fee |
| FEE | FVOY950AUTH | Voyager 950 Auth Fee |
| FEE | FVOYAUTH | Voyager Auth Fee |
| FEE | FVOYAUTHF0DI | Voyager Authorizations |
| FEE | FVOYBATCHAUTH | Voyager Batch Authorizations |
| FEE | FVOYCRDTTXN | Voyager Credit Tran Fee |
| FEE | FVOECRAUTH | Voyager Ecr Auth Fee |
| FEE | FVOYLCLAUTH | Voyager Local Auth Fee |
| FEE | FVOYPETROCHGBK | Voyager Petro Chargebacks |
| FEE | FVOYSLSTXNF00W | Voyager Sales Tran Fee |
| FEE | FVOYVOICEAUTHF0BW | Voyager Voice |
| FEE | FVOYVRU | Voyager Vru |
| FEE | FVOYWATSAUTH | Voyager Wats Auth Fee |
| FEE | FVIHIGHRSKACQRINTL | Vs Intl Acq Fee High Risk |
| FEE | FVIACQRINTL | Vs Intl Acquirer Fee |
| FEE | FWCPSLSDSCNT | Wcp Sales Discount Fee |
| FEE | FWCPSLSTXN | Wcp Sales Transaction Fee |
| FEE | FWEBPAGEIMALL | Web Page/Imall Fee |
| FEE | FWEBESNTNLSMNTH | Website Essentials Monthly Fee |
| FEE | FWEXCHGBK | Wex Chargeback Fee |
| FEE | FWEXRTVL | Wex Retrieval Fee |
| FEE | FAMXWHLSLPRGM | Wholesale Amex Program Pricing |
| FEE | FWHLSLDSIC | Wholesale Ds Interchange Fee |
| FEE | FWRLSACTVTN | Wireless Activation Fee |
| FEE | FWRLS | Wireless Fee |
| FEE | FWEXPLTXN | Wright Express (P/L) Trans Fee |
| FEE | FWEX950AUTH | Wright Express 950 Auth Fee |
| FEE | FWEXAUTH | Wright Express Authorizations |
| FEE | FWEXBATCHAUTH | Wright Express Batch Auth Fee |
| FEE | FWEXECRAUTH | Wright Express Ecr Auth Fee |
| FEE | FWEXLCLAUTH | Wright Express Local Auth Fee |
| FEE | FWEXWATSAUTH | Wright Express Wats Auth Fee |
| FEE | FYAHOOGTWY | Yahoo Gateway Fee |
| FEE | FBPBRNDMRKTRINCR | Bp Brand Marketer Incrmntl Fee |
| FEE | FTCKACCELERATRMNL | Telecheck Accelera Terminal |
| FEE | FAMXADJ | Amex Adjustment |
| FEE | FMANUALRLSEAMIACCT | Manual Release Ami Account |
| FEE | FTATKNENCRYPT3DESP2P | Transarmor Tkn Enc 3Des P2Pe |
| FEE | FTATKNENCRYPTONGUARD | Transarmor Tkn Encrypt Onguard |
| FEE | FTATKNENCRYPTVFP2P | Transarmor Tkn Encrypt Vf P2Pe |
| FEE | FTATKNENCRYPTRSAP2P | Ta Tkn Encrypt Rsa/Pki P2Pe |
| FEE | FCLVRMINIWIFI | Clover Mini Wi Fi |
| FEE | FCLVRMINI3GWIFI | Clover Mini 3G & Wi Fi |
| FEE | FHPBARCDSCNRUSB | Hp Barcode Scanner Usb |
| FEE | FBMLCHGBK | Bill Me Later Chargbk |
| FEE | FBLMRPRSNTMNT | Bill Me Later Reprsnt |
| FEE | FVIBPCARDIC | Bp Visa Bp Card Interchange |
| FEE | FETCCONFLTR | Etc Confirmation Letter |
| FEE | FJCBACCPT | Jcb Acceptance Fee |
| FEE | FVERISIGNFRAUDBASIC | Verisign Fraud Basic |
| FEE | FVERISIGNFRAUDPRO | Verisign Pro |
| FEE | FGCSVCMNTH | Gc Monthly Service Fee |
| FEE | FQKPGWDOMAIN | Quikpage With Domain |
| FEE | FVOLSMRTCLKSTIERI | Vol Smart Clicks Tier I |
| FEE | FVOLSMRTCLKSTIERIII | Vol Smart Clicks Tier Iii |
| FEE | FVOLLCL | Vol Local |
| FEE | FVISIBILITYONLN | Visibility Online |
| FEE | FQKPGTLDNTNLPKG | Quickpage Tld National Package |
| FEE | FEFSNETGTWYMNTH | Efsnet Monthly Gateway Fee |
| FEE | FMERCLUBTAXFREE | Merchant Club Tax Free Fee |
| FEE | FDBTCARDMNTH | Debit Card Monthly Fee |
| FEE | FHPCECALCE5700TRMNL | Hp Ceca Ice 5700 Term Fee |
| FEE | FHPICE5700TRMNL | Hc 5700 Ice 5700 Term Fee |
| FEE | FCELEREXTRMNLEDC | Celerex Terminal Edc |
| FEE | FHPCMGALCE5700TRMNL | Hp Cmgs Ice 5700 Term Fee |
| FEE | FNONDBTHANDLING | Non Debited Handling Fee |
| FEE | FCLVRMINI2LTEWIFI | Clover Mini 2 Lte & Wifi |
| FEE | FCRMTTRMNLBILLING | Crmt Terminal Billing Fee |
| FEE | FMRCHNTOWNEDTRMNLEDC | Merchant Owned Terminal Edc |
| FEE | FRPLCMNT | Replacement Fee |
| FEE | FEXPRSSHPINGHANDLING | Express Ship And Handling |
| FEE | FRPLCMNTSHIPANDHANDLING | Replacement Ship And Handle |
| FEE | FPOSSLSTAX | Pos Sales Tax |
| FEE | FPERIPHRLEXPRSSHIP | Peripheral Express Shipping |
| FEE | FCLVRCARE3YR | Clover Care 3 Year Plan |
| FEE | FCTZN200PRNTR | Citizen 200 Printer |
| FEE | FCLVR3GWIFI | Clover Mobile 3G & Wi Fi |
| FEE | FECPVICARCGCHK21 | Mth Fee Wd Ecp & Boc/Arc/Chk21 |
| FEE | FMNTHLYFWITHACCTPAYRCVBL | Mthly Fee With Acc Pay & Recv |
| FEE | FMNTHLYFLATB | Monthly Flat Fee B |
| FEE | FNDCBTCH | Ndc Batch Fee |
| FEE | FEQPPRCHS | Equipment Purchase |
| FEE | FEQPPRCHSINSTL | Equipment Purchase Installment |
| FEE | FEQPRETURNCRDT | Credit For Equipment Returned |
| FEE | FEQPEXPRSSHIP | Equipment Express Shipping |
| FEE | FEQPMNTNCMNTH | Equip Monthly Maintenance Fee |
| FEE | FEQPADJRVSL | Equipment Fee Adj/Rev |
| FEE | FSEMIANNUALSVC | Semi Annual Service Fee |
| FEE | FTECHSUPRTSVC | Technical Support Services Fee |
| FEE | FSUPPLYXPRSSHIPANDHNDLNG | Supply Express Ship & Handling |
| FEE | FSUPLYORDER | Supply Order |
| FEE | FSUPPLYSHIPANDHNDLNG | Supply Shipping & Handling |
| FEE | FSETUP | Set Up Fee |
| FEE | FNSF | Nsf Fee |
| FEE | FDBTCARDDEPOST | Debit Card Deposits |
| FEE | FICRJCTRSLVDTOMRCH | Intrchng Rej Resolved To Merch |
| FEE | FSLSTAXPAYBL | Sales Tax Payable |
| FEE | FTAXIDFINE | Taxid Fine |
| FEE | FREPRESENTEDDD | Represented Dd |
| FEE | FWRLSCOMMSETUP | Wireless Comm Set Up Fee |
| FEE | FEBTRBT | Ebt Rebate Fee |
| FEE | FEQPSFTWRPRCHS | Equipment & Software Purchase |
| FEE | FADVNCMEPRGM | Advanceme Pgm |
| FEE | FFIRSTFUNDS | First Funds |
| FEE | FRAPIDADVNC | Rapid Advance |
| FEE | FFDCLVRGONFCRDR | Fd Clovrgo Emv Nfc Rdr |
| FEE | FFUNDNTFCTNFAX | Funding Notification Fax Fee |
| FEE | F100TRMNLBILLING | F100 Terminal Billing Fee |
| FEE | FGTETRMNLB | Gte Terminal Billing |
| FEE | FGCTXNPROCESSING | Gift Card Transaction Process |
| FEE | FGCSTDCARDLT500 | Gc < 500 With Merchant Name |
| FEE | FGCCSTMCARD1000TO2499 | Gc Custom Cards 1000 2499 |
| FEE | FGCCSTMCARD2500TO4999 | Gc Custom Cards 2500 4999 |
| FEE | FGCCSTMCARD5000TO7499 | Gc Custom Cards 5000 7499 |
| FEE | FGCCSTMCARD7500TO9999 | Gc Custom Cards 7500 9999 |
| FEE | FGCCSTMCARD10KLT25K | Gc Custom Cards 10000 24999 |
| FEE | FGCCSTMCARD25KLT50K | Gc Custom Cards 25000 49999 |
| FEE | FGCCSTMCARD50KLT100K | Gc Custom Cards 50000 99999 |
| FEE | FGCCSTMCARD100KLESST200K | Gc Custom Cards 100000 199999 |
| FEE | FGCSTDCARD500LT1K | Gc Standard Cards < 1000 |
| FEE | FGCSTDCARD1000TO2499 | Gc Standard Cards 1000 2499 |
| FEE | FGCSTDCARD2500TO4999 | Gc Standard Cards 2500 4999 |
| FEE | FGCSTDCARD5000TO7499 | Gc Standard Cards 5000 7499 |
| FEE | FGCSTDCARD7500TO9999 | Gc Standard Cards 7500 9999 |
| FEE | FGCSTDCARD10KLT25K | Gc Standard Cards 10000 24999 |
| FEE | FGCSTDCARD25KLT50K | Gc Standard Cards 25000 49999 |
| FEE | FGCSTDCARD50KLT100K | Gc Standard Cards 50000 99999 |
| FEE | FGCSTDCARD100KLT200K | Gc Standard Card 100000 199999 |
| FEE | FGCCARDCARR500TO999 | Gc Card Carriers 500 999 |
| FEE | FGCCARDCARR1000TO2499 | Gc Card Carriers 1000 2499 |
| FEE | FGCCARDCARR2500TO4999 | Gc Card Carriers 2500 4999 |
| FEE | FGCCARDCARR5000TO7499 | Gc Card Carriers 5000 7499 |
| FEE | FGCCARDCARR7500TO9999 | Gc Card Carriers 7500 9999 |
| FEE | FGCCSTMCARDCRR10KLT25K | Gc Card Carriers 10000 24999 |
| FEE | FGCCSTMCARDCRR25KLT50K | Gc Card Carriers 25000 49999 |
| FEE | FGCCSTMCARDCRR50KLT100K | Gc Card Carriers 50000 99999 |
| FEE | FGCCSTMCARDCRR100KLT200K | Gc Card Carriers 100000 199999 |
| FEE | FGCDSPLYRACKPSTR | Gc Display Rack Poster |
| FEE | FGCDSTDSTOCKCRR | Gc Standard Stock Carrier |
| FEE | FGCDSPLYRACKWONEBX | Gc Display Rack W/ One Box |
| FEE | FGCDOORDECAL | Gc Door Decal |
| FEE | FGCTXNPRCSSNGSLSTAX | Gc Transaction Proc Sales Tax |
| FEE | FGCCARDPRDCTNSLSTAX | Gc Card Production Sales Tax |
| FEE | FGCTSHIPSLSTAX | Gc Shipping Sales Tax |
| FEE | FGCPSTRONLYDSPLY | Gc Poster Only Display |
| FEE | FGCGIFTCARDSTOGO | Gc Gift Cards To Go |
| FEE | FGCACCTSTUPGOLDPKG | 1Time Acct Setup Gold Pckg Fee |
| FEE | FGCACCTSTUPSLVRPKG | 1Time Acct Setup Slvr Pckg Fee |
| FEE | FGCSPCLORDR | Gc Special Order |
| FEE | FGCCSTMPSTRS | Gc Custom Posters |
| FEE | FGCOTHRMRKTNGMTRL | Gc Other Marketing Materials |
| FEE | FGCXCPTNDEVLPMNT | Gc Exception Development |
| FEE | FGCGIFTCARDINABOX | Gc Gift Card In A Box |
| FEE | FGCCRRENVLPS | Gc Carrier Envelopes |
| FEE | FGCWELCOMEKIT | Gc Welcome Kit |
| FEE | FPCPRDCTH | Pc Product H Fee |
| FEE | FTWINTRANUSGMNTH | Monthly Twintran Usage Fee |
| FEE | FICOTTRMNLBILLING | Icot Terminal Billing |
| FEE | FIPSETRMNLBILLING | Ipse Terminal Billing Fee |
| FEE | FI12TRMNLBILLING | I12 Terminal Billing Fee |
| FEE | FJ719TRMNLBILLING | J719 Terminal Billing Fee |
| FEE | FHPKEYBRDWITHMOUSEUSB | Hp Ketbrd W/Mouse Usb |
| FEE | FKTCHNRCPTPRNTR | Kitchen Receipt Printer |
| FEE | FVIPRTCPTN | Visa Participation Fee |
| FEE | FMCPRTCPTN | Mc Participation Fee |
| FEE | FVBVUSGMNTH | Vbv Monthly Usage |
| FEE | FTCKONLNSETUP | Tck Online Setup Fee |
| FEE | FLNKSHIELD3SETUP | Linkshield 3 Setup Fee |
| FEE | FLNKSHIELD3USGMNTH | Linkshield 3 Monthly Usage |
| FEE | F3DSGTWYTXN | Gateway 3D Secure Trx Fee |
| FEE | FFTRLNKPT4USGMNTH | Future Linkpt4 Monthly Usage |
| FEE | FFTRLNKPT4TXN | Future Linkpt4 Trans Fee |
| FEE | FGLBLGTYTXN | Global Gateway Trans Fee |
| FEE | FLYLTSTDCARDS250 | Loyalty Standard Cards 250 |
| FEE | FLYLTSTDCARDS500 | Loyalty Standard Cards 500 |
| FEE | FLYLTSTDCARDS750 | Loyalty Standard Cards 750 |
| FEE | FLYLTSTDCARDS1KPLUS | Loyalty Standard Cards 1000+ |
| FEE | FLYLTCSTMCARDS1K | Loyalty Custom Cards 1000 |
| FEE | FLYLTCSTMCARDS2500 | Loyalty Custom Cards 2500 |
| FEE | FLYLTCSTMCARDS5K | Loyalty Custom Cards 5000 |
| FEE | FLYLTCSTMCARDS10KPLUS | Loyalty Custom Cards 10000+ |
| FEE | FMRKTNGKITFREQBSEDMSGING | Marketing Kit Freq Messaging |
| FEE | FLYLTSTTLACHRET | Loyalty Settle Ach Return |
| FEE | FLYLTSTTLACHRJCT | Loyalty Settle Ach Reject |
| FEE | FLYLTDSCNTREDEEMD | Loyalty Discounts Redeemed |
| FEE | FLYLTDSCNTISSUED | Loyalty Discounts Issued |
| FEE | FLYLTDSCNT | Loyalty Discounts Fee |
| FEE | FMRCHNTCLUBTAX | Tax Of Merchant Club |
| FEE | FHPMAGSTRPRDRUSB | Hp Mag Stripe Rdr Usb |
| FEE | FMISCADJ | Msc Adjustment |
| FEE | FEBTCRDTADJ | Ebt Credit Adjustment |
| FEE | FEBTDBTADJ | Ebt Debit Adjustment |
| FEE | FEQPBILLING | Equipment Billing |
| FEE | FEQPCALLTAGORSWAP | Call Tag/Swap |
| FEE | FSTRNTWKANNUAL | Star Network Annual Fee |
| FEE | FPULSENTWKANNUAL | Pulse Network Annual Fee |
| FEE | FJNENTWKANNUAL | Jeanie Network Annual Fee |
| FEE | FNYCENTWKANNUAL | Nyce Network Annual Fee |
| FEE | FMSTRCHGBKDBT | Maestro Chargeback Debit |
| FEE | FPYMNT3 | Payment 3 |
| FEE | FTABILLING | Transarmor Billing |
| FEE | FTERM | Termination Fee |
| FEE | FTRMNLFEEADJ | Terminal Fee Adjustment |
| FEE | FCLIANCELOCANNUAL | Culiance Annual Location Fee |
| FEE | FAPMMISCADJDR | Apm Misc Adj Dr |
| FEE | FMCADJ | Mastercard Adjustments |
| FEE | FHNRADJREVCSTMRINQ | Honor Adj. Rev. Customer Inq. |
| FEE | FWEXUNPDMANUALADJ | Wex Unpaid & Manual Adjustment |
| FEE | FVOYUNPDMANUALADJ | Voyager Unpaid & Manual Adj |
| FEE | FLGLENTTYADMIN | Legal Entity Admin Fee |
| FEE | FLYLTSVCCALLMRCHNTFM4T | Loyalty Srv Call Merchant |
| FEE | FLYLTSVCCALLCSTMR | Loyalty Srv Call Customer |
| FEE | FMSTRADJCSTMRINQ | Maestro Adj. Customer Inquiry |
| FEE | FGTWY | Gateway Fee |
| FEE | FERLYCNCLTNRBT | Early Cancellation Fee Rebate |
| FEE | FMCDSCNTFEEADJRVSL | Mastercard Discount Fee Adj/Re |
| FEE | FVIDSCNTRBT | Visa Discount Rebates |
| FEE | FTXNFEEADJ | Transaction Fee Adjustment |
| FEE | FASSOCRBT | Association Rebate |
| FEE | FMCICFEEADJRVSL | Mc Interchange Fee Adj/Rev |
| FEE | FMCASSMTADJRVSL | Mc Assessment Fee Adj/Rev |
| FEE | FVIASSMTADJRVSL | Visa Interchange Fee Adj/Rev |
| FEE | FICFEEADJ | Interchange Fee Adjustment |
| FEE | FASSMTFEEADJ | Assessment Fee Adjustment |
| FEE | FBLBKADJ | Billback Adjustment |
| FEE | FSVLIVEAGNTMINUTE | Sv Live Agent Minute |
| FEE | FSVACHSTLMTSVC | Sv Ach Settlement Services Fee |
| FEE | FDBTFEEADJ | Debit Fee Adj/Rev |
| FEE | FPNDGINVSTGTN | Pending Investigation |
| FEE | FMCBLBKRBT | M/C Billback Rebates |
| FEE | FAUTHRBT | Authorization Rebates |
| FEE | FBTOBRRFRLRBT | B To B Referral Rebate |
| FEE | FDBTCARDRBT | Debit Card Rebates |
| FEE | FEQPRPLCMNTBILLING | Replacement Equipment Fee |
| FEE | FCONNECT | Connect Fees |
| FEE | FNCRTRMNLBILLING | Ncr Terminal Billing |
| FEE | FNT8TRMNLBILLING | Nt8 Termianl Billing Fee |
| FEE | FNURIT2085TRMNLBILLING | Nurit 2085 Terminal Billing |
| FEE | FNURIT3020TRMNLBILLING | Nurit 3020 |
| FEE | FDRCTDBAUSTSTL | Directdb Austria Stl |
| FEE | FUNPCHGBKADJ | Union Pay Chargbck & Adjustmnt |
| FEE | FODULTRMNLBILLING | Odul Terminal Billing Fee |
| FEE | FVISCLRSTTLINTER | Visa Clr & Settl Fee Inter |
| FEE | FMCOPENFXMCP | Openfx Mcp Mc Fee |
| FEE | FVIOPENFXMCP | Openfx Mcp Vi Fee |
| FEE | FFD130DUOTRMNLBILLING | Fd130 Duo Terminal Billing Fee |
| FEE | FOMRON250TRMNLEDC | Omron 250 Terminal Edc |
| FEE | FPCTRMNLBILLING | Pc Terminal Billing |
| FEE | FOPCITRMNLBILLING | 0Pci Terminal Billing |
| FEE | FPCPRDCT | Pc Product T Fee |
| FEE | FMSPOSCSTMROWNED | Ms Pos Customer Owned |
| FEE | FPEREGRINSCRIPTRMNLEDC | Peregrin Scrip Terminal Edc |
| FEE | FPISVTRMNLBILLING | Pisv Terminal Billing Fee |
| FEE | FPPSETRMNLBILLING | Ppse Terminal Billing Fee |
| FEE | FPLTNMSVCPLN | Platinum Service Plan |
| FEE | FSUPPLYSHIPPING | Supply/Shipping Fees |
| FEE | FP300TRMNLBILLING | P300 Terminal Billing Fee |
| FEE | FP900PRNTR | P900 Printer |
| FEE | FREMITBILL | Remit Bill |
| FEE | FSCHDLRLSERPPCASHACCT | Sched Release Rpp Cash Acct |
| FEE | FMANUALRLSRPPCASHACCT | Manual Release Rpp Cash Acct |
| FEE | FFUNDSXFERRPPTORSRV | Funds Trnsfer Rpp To Reserve |
| FEE | FRUSYTRMNLBILLING | Rusy Terminal Billing Fee |
| FEE | FVFENCRYPTSLEEVE | Verifone Encryption Sleeve |
| FEE | FSTNDFLUSHMNT | Stand Flush Mount |
| FEE | FSELECTSVCRSA | Select Service Rsa |
| FEE | FHYPRCOMS7 | Hypercom S7 |
| FEE | FFD130TRMNLBILLING | Fd130 Terminal Billing Fee |
| FEE | FTWFITRMNLBILLING | Twfi Terminal Billing Fee |
| FEE | FTCKTXNFT01 | Telecheck Transactions |
| FEE | FTCKMNTHMIN | Telecheck Monthly Minimum |
| FEE | FTCKCHKINQ | Telecheck Check Inquiries |
| FEE | FTCKCSTMREQOPERCALLS | Telecheck Cust Req Oper Calls |
| FEE | FTCKACCTADJ | Telecheck Account Adjustments |
| FEE | FHYPRCOMINONEBILLING | Hypercom In One Billing |
| FEE | FASSMTRVSL | Assessment Reversal |
| FEE | FTCKDBTADJ | Tck Debit Adjustment |
| FEE | FTCKCRDTADJ | Tck Credit Adjustment |
| FEE | FT202TRMNLBILLING | T202 Terminal Billing Fee |
| FEE | FTXNZ38X2TRMNL | Tranz 38X2 Terminal |
| FEE | FHYPRCOMT7P | Hypercom T7P |
| FEE | FCLVRSTN2018 | Clover Station 2018 |
| FEE | FNURIT30310ONUSWTRMNL | Nurit 3010 On Usw Terminal Fee |
| FEE | FLYLTTXNOTHR | Loyalty Transaction Other |
| FEE | FVERTRMNLBILING | Ver Terminal Billing |
| FEE | FICVUPGDDOSWINSM | Icv Upgd Dos Win M |
| FEE | FVFLOGPRNTR | Verifone Log Printer |
| FEE | FCLVRSSCALE | Clover Scale |
| FEE | FVIAPFUS | Visa Us Apf Fee |
| FEE | FTRUSTKPRSTDSVC | Trustkeeper Standard Service |
| FEE | FMNTHENDDSCNTBILLING | Month End Discount Billing |
| FEE | FGETFNDBSNSLST | Get Found Business Listings |
| FEE | FSVSUBSCRPTN | Sv Subscription Fee |
| FEE | FFRAUDDTCTMNGDSVC | Fraud Detect Mangd Service Fee |
| FEE | FVIRTVAYMNTH | Rtime Visa Acct Updtr Mnthly |
| FEE | FVIRTVAUSETUP | Rtime Visa Acct Updtr Setup |
| FEE | FCRDPNTEPRMUMSVC | Cardpointe Premium Services |
| FEE | FINTGRTDDVCRNTL | Integrated Device Rental |
| FEE | FMNTNCANNUAL | Annual Maintenance Fee |
| FEE | FPCILBLTYWVR | Pci & Liability Waiver |
| FEE | FINSGHTBASEMNTH | Ent Insights Base Mthly |
| FEE | FINSGHTDMGRPHCMNTH | Ent Insights Demographic Mthly |
| FEE | FINSGHTTXNMNTH | Tran Insights Monthly |
| FEE | FPLTFRMACCSSMNTHFY49 | Platform Access Setup Fee |
| FEE | FRAPIDDPSTFLAT | Rapid Deposit Flat Fee |
| FEE | FCRDPNTEGTWYMNTH | Cardpointe Gateway Monthly Fee |
| FEE | FINSTANTACCPT | Instant Accept |
| FEE | FSASSSRVC | Saas Services Fee |
| FEE | FPCICNCRGMNTH | Pci Concierge Monthly Fee |
| FEE | FCRDPNTEMICROSMNTH | Cardpointe Micros Monthly Fee |
| FEE | FUNATNDDVCLCNSE | Unattended Device License Fee |
| FEE | FZONJRTRMNLBILLING | Zon Jr Terminal Billing |
| FEE | FINTRLNKDISPUTIMG | Dispute Image Fee Interlink |
| FEE | FLACNWACCPTAUTH0TO20DMS | Nw Acpt 0 20 Auth Lac Dms |
| FEE | FLACNWACCPTAUTH21TO25DMS | Nw Acpt 21 25 Auth Lac Dms |
| FEE | FLACNWACCPTAUTH26TO30DMS | Nw Acpt 26 30 Auth Lac Dms |
| FEE | FLACNWNOACCPTAUTHDMS | Nw No Acpt Auth Lac Dms |
| FEE | FLACNWACCPTFCNP0TO20DMS | Nw Acpt 0 20 Frd Cnp Lac Dms |
| FEE | FLACNWACCPTFCNP21TO25DMS | Nw Acpt 21 25 Frd Cnp Lac Dms |
| FEE | FLACNWACCPTFCNP26TO30DMS | Nw Acpt 26 30 Frd Cnp Lac Dms |
| FEE | FLACNWNOACCPTFCNPDMS | Nw No Acpt Frd Cnp Lac Dms |
| FEE | FNWACCPTEXCSFRD0TO20DMS | Nw Acpt 0 20 Frd Excess Dms |
| FEE | FVIRDR | Visa Rdr Fee |
| FEE | FNWACCPTEXCSFRD21TO25DMS | Nw Acpt 21 25 Frd Excess Dms |
| FEE | FNWACCPTEXCSFRD26TO30DMS | Nw Acpt 26 30 Frd Excess Dms |
| FEE | FNWNOACCPTEXCSFRDDMS | Nw No Acpt Frd Excess Dms |
| FEE | FEBTFOODSTMPPRCHSUTAH | Ebt Food Stamp Purch Fee Utah |
| FEE | FEBTFDSTMPRETUTAH | Ebt Food Stamp Return Fee Utah |
| FEE | FEBTCASHBNFTPRCHSIDAHO | Ebt Cash Bene Purch Fee Idaho |
| FEE | FEBTCASHBNFTPRCHSICOLO | Ebt Cash Bene Purch Fee Colo |
| FEE | FEBTCASHBNFTPRCHSIALASKA | Ebt Food Stamp Pur Fee Alaska |
| FEE | FSIGBDBTCHGBKTXN | Sig Debit Chargeback Trans Fee |
| FEE | FSIGBDBTRVSLTXN | Sig Debit Reversal Trans Fee |
| FEE | FVIAUTHOPTAPPRVDRETRY | Auth Opt Visa Appvd Retry Fee |
| FEE | FSIGDBTVRUAUTH | Sig Debit Vru Auth Fee |
| FEE | FBATCHCLOSR | Batch Closure Fee |
| FEE | FAMXAUTHF0BE | Amex Auth |
| FEE | FVOYAUTHFOBI | Voyager Auth |
| FEE | FMCDCLN | Mastercard Decline |
| FEE | FVIDCLN | Visa Decline |
| FEE | FAMXDCLN | Amex Decline |
| FEE | FDSCVDCLN | Discover Decline |
| FEE | FDNRDCLN | Diners Decline |
| FEE | FWEXDCLN | Wex Decline |
| FEE | FVIPREAUTH | Visa Pre Auth |
| FEE | FPHONEAUTH | Phone Auth |
| FEE | FFLTONEAUTH | Fleet One Authorization Fee |
| FEE | FFLTCRVOICEAUTH | Fleetcor Voice Auth Fee |
| FEE | FSIGDBTAUTHFS | Sig Debit Authorization Fee Fs |
| FEE | FREGDBTAUTHFS | Reg Debit Authorization Fee Fs |
| FEE | FDBTAUTHF0CO | Debit Authorization Fee |
| FEE | FMCDCLNRSNCDSVCINT | Mc Decline Rsn Cd Sv Fee Int |
| FEE | FMCDCLNRSNCDSVCINTMIN | Mc Decline Rsn Cd Fee Int Min |
| FEE | FMCDCLNRSNCDSVCINTMAX | Mc Decline Rsn Cd Fee Int Max |
| FEE | FEBTONLNBLNCINQ | Ebt Online Bal Inquiry |
| FEE | FWEXVOICEAUTH | Wex Voice Authorization Fee |
| FEE | FGTWYAUTH | Gateway Authorization Fee |
| FEE | FEBTONLNGTWY | Ebt Online Gateway |
| FEE | FEBTONLNRVSL | Ebt Online Reversal |
| FEE | FCLVRAUTH | Clover Authorization Fee |
| FEE | FJIFFYLUBSLSTXN | Jiffy Lube Sales Trans Fee |
| FEE | FMCAUTHOMNIP | Mastercard Auth Fee Omnipay |
| FEE | FMCADDRESVRYOMNP | Mc Address Verifi Omnipay |
| FEE | FAVSCNPOMNP | Cnp Avs Fee Omnipay |
| FEE | FVIAUTHOMNP | Visa Auth Fee Omnipay |
| FEE | FVIADDRVRFYOMNP | Visa Address Verifi Omnipay |
| FEE | FTCKINPRSNWRNTYAUTH | Tck In Person Wrntd Auth Fee |
| FEE | FTCKINPRSNWRNTYINQ | Tck In Person Wrntd Inq Fee |
| FEE | FTCKPAPRWRNTYAUTH | Tck Paper Wrntd Auth Fee |
| FEE | FTCKPAPRWRNTYINQ | Tck Paper Wrntd Inq |
| FEE | FTCKPAPRNOWRNTYAUTH | Tck Paper Non Wrntd Auth Fee |
| FEE | FTCKPAPRNOWRNTYINQ | Tck Paper Non Wrntd Inq |
| FEE | FMCDBTMAILORDR | Mc Debit Mail Order |
| FEE | FSTRDVLTXN | Stored Value Transaction Fee |
| FEE | FPULSEDBTTXN | Pulse Debit Trans Fee |
| FEE | FBNKMATEDBTTXN | Bankmate Debit Trans Fee |
| FEE | FMSTRDBTTXN | Maestro Debit Trans Fee |
| FEE | FLYNXDBTTXN | Lynx Debit Trans Fee |
| FEE | FHNRDBTTXN | Honor Debit Transaction Fee |
| FEE | FCASHSTNDBTTXN | Cash Station Debit Tran Fee |
| FEE | F00GGTRMNLBILLING | 00Gg Terminal Billing Fee |
| FEE | FTYMEDBTTXN | Tyme Debit Tran Fee |
| FEE | FAFFNDBTTXN | Affn Debit Tran Fee |
| FEE | FNYCEDBTTXN | Nyce Debit Tran Fee |
| FEE | FMACDBTTXN | Mac Debit Tran Fee |
| FEE | FSTRDBTTXN | Star Debit Transaction Fee |
| FEE | FRFNDTXNCHRG | Refund Txn Charge |
| FEE | FAMXCHGBKRVSLTXN | Amex Chargeback Reversal Tran |
| FEE | FMCDRCTSND | Direct Send Fee Mc |
| FEE | FVIDRCTSND | Direct Send Fee Vi |
| FEE | FMACSPNSR | Mac Sponsor Fee |
| FEE | FMSTRSPNSR | Maestro Sponsor Fee |
| FEE | FAMXCHGBKTXNFO1P | Amex Chargebacks Trans Fee |
| FEE | FAMXRVSLTXN | Amex Reversals Trans Fee |
| FEE | FONUSDBTPRCHS | Onus Debit Purchase |
| FEE | FACCELPRCHS | Accel Purchase |
| FEE | FSTRDBTPRCHS | Star Debit Purchase |
| FEE | FINTRLNKDBTPRCHS | Interlink Debit Purchase |
| FEE | FMSTRDBTPRCHS | Maestro Debit Purchase |
| FEE | FONUSDBTPRCHSSNF | Onus Debit Purchase,Store/Fwd |
| FEE | FSTRDBTPRCHSSNF | Star Dbt Purchase,Store/Fwd |
| FEE | FINTRLNKDBTPRCHSSNF | Interlink Dbt Purchase,Str/Fwd |
| FEE | FMSTRDBTPRCHSSNF | Maestro Dbt Purchase,Store/Fwd |
| FEE | FWLMRTPVTLBLSLSTXN | Walmt Pl Sale Tran |
| FEE | FWLMRTPVTLBLRETTXN | Walmt Pl Rtrn Tran |
| FEE | FMCPRCNGUNDFNDAUTHLAC | Mc Proc Integ Undef Auth Lac |
| FEE | FMCPRCNGPREAUTHLACAP | Mc Proc Integ Pre Auth Lac/Ap |
| FEE | FDBTATMCARDRETTXN | Debit/Atm Card Return Tran Fee |
| FEE | FEBTFDSTMPPRCHS | Ebt Food Stamp Purchase Fee |
| FEE | FEBTCASHBNFTPRCHS | Ebt Cash Benefits Purchase Fee |
| FEE | FMCZERODLR | Zero Dollar Auth Fee Mc |
| FEE | FVITXNADVSRAFD | Visa Tran Advisor Afd |
| FEE | FVIRTMACCTUPDTRSVC | Rtime Visa Acct Updtr Srvc Fee |
| FEE | FVIZERODLRAUTH | Zero Dollar Auth Fee Visa |
| FEE | FDNRVOICEAUTHF05A | Diners Voice Addr Ver/Auth |
| FEE | FDNRAUTOADDRVRFY | Diners Auto Addr Verification |
| FEE | FDNRECRADDRVRFY | Diners Ecr Addr Verification |
| FEE | FDNRINTRNTAUTH | Diners Internet Auth Fee |
| FEE | FDNRARULCLAUTH | Diners Aru Local Auth Fee |
| FEE | FDNRARUWATSAUTH | Diners Aru Wats Auth Fee |
| FEE | FDNRCPUAUTH | Diners Cpu Authorization |
| FEE | FDNRVOICEAUTHISSRRFRL | Diners Voice Auth Issuer Ref |
| FEE | FDSCVHSTCPTR | Host Capture Fee Discover |
| FEE | FDSCVARULCLAUTH | Discover Aru Local Auth Fee |
| FEE | FDSCVARUWATSAUTH | Discover Aru Wats Auth Fee |
| FEE | FJCBINTRNTAUTH | Jcb Internet Auth Fee |
| FEE | FJCBARULCLAUTH | Jcb Aru Local Auth Fee |
| FEE | FJCBARUWATSAUTH | Jcb Aru Wats Auth Fee |
| FEE | FJCBCPUAUTH | Jcb Cpu Authorization |
| FEE | FJCBVOICEAUTHISSRRFRL | Jcb Voice Auth Issuer Referral |
| FEE | FSIGDBTCPTR | Sig Debit Capture Fee |
| FEE | FGENPIBESTPETROAUTH | Gen Pl Best Petroleum Auth Fee |
| FEE | FGENPIGASCARDAUTH | Gen Pl Gascard Auth Fee |
| FEE | FGENPISMRTCARTEAUTH | Gen Pl Smart Carte Auth Fee |
| FEE | FDNRDFLTAUTH | Diners Default Auth Fee |
| FEE | FPVTLBLVOICEAUTH | Private Label Voice Auth |
| FEE | FPVTLBLDFLTAUTH | Private Label Default Auth Fee |
| FEE | FVOYVOICEAUTH | Voyager Voice Auth Fee |
| FEE | FVIZEROACCTVRFYINTL | Visa Zero Acct Ver Intl Fee |
| FEE | F102ZTRMNLBILLING | 102Z Terminal Billing Fee |
| FEE | FRAMECTRMNLBILLING | Ram Ec Terminal Billing Fee |
| FEE | FCLVRMINI | Clover Mini |
| FEE | FROAMMBLRDR | Roam Mobile Reader |
| FEE | FMBLTOGO | Mobile To Go |
| FEE | FVX805TRMNLBILLING | Vx805 Terminal Billing |
| FEE | FCLVRFD40US | Clover Fd 40 Us |
| FEE | FVIACCSSPERMSGEU | Visa Eu Access Per Message Fee |
| FEE | FMCACCTSTTSINQSVCINTRRT | Mc Acct Status Inq Svc Intrare |
| FEE | FCLVRFLX3G | Clover Flex 3G |
| FEE | F2DHNDHELDBRCDSCNR | 2D Handheld Bc Scanner |
| FEE | FCLVRMRCHNTKEYPAD | Clover Merchant Keypad |
| FEE | F1112TRMNLBILLING | 1112 Terminal Billing Fee |
| FEE | FVOYEDCCPTR | Voyager Edc Capture Fee |
| FEE | FCLVRGOUNICLIP | Clovergo Uniclip |
| FEE | FCMPSFRAUDTXNPERTXNSC | Cmps Fraud Trns Per Txn Sc Fee |
| FEE | FTAONGUARDP2PE | Transarmor Onguard P2Pe |
| FEE | FFD150TRMNLBILLING | Fd150 Terminal Billing Fee |
| FEE | FDBTSLSDSCNTF120 | Debit Sales Discount Rate |
| FEE | FDBTRETDSCNT | Debit Returns Discount Rate |
| FEE | FMCPYMNTTXN | Mc Payment Transaction Fee |
| FEE | FVIPYMNTTXN | Vi Payment Transaction Fee |
| FEE | FDBTSLSTXN | Debit Sales Trans Fee |
| FEE | FDBTRETTXN | Debit Returns Trans Fee |
| FEE | FVIFNDTXN | Vi Funding Transaction Fee |
| FEE | F129GTRMNLBILLING | 129G Terminal Billing Fee |
| FEE | FCLVRDUOTRMNLWIFI | Clover Duo Terminal Wifi |
| FEE | FMCDBTCHGBKTXN | Mc Debit Chargeback Trans Fee |
| FEE | FMCDBTRVSLTXN | Mc Debit Reversals Trans Fee |
| FEE | FVIDBTCHGBKTXN | Vi Debit Chargeback Trans Fee |
| FEE | FVIDBTRVSLTXN | Vi Debit Reversal Trans Fee |
| FEE | FDNRMCSLSTXN | Diners (Mc)Sales Trans Fee |
| FEE | FDNRMCEFNDTXN | Diners (Mc)Credits Trans Fee |
| FEE | FMCDBTMQTXN | Mc Debit Mid Qual Trans Fee |
| FEE | FMCDBTMQRETTXN | Mc Debit Mid Qual Rtrn Trans |
| FEE | FMCDBTMQCHGBKTXN | Mc Deb Mid Qual Chrgbk Trans |
| FEE | FMCDBTMQRVSLTXN | Mc Debit Mid Qual Rev Trans |
| FEE | FVIDBTMQTXN | Vi Debit Mid Qual Trans Fee |
| FEE | FVIDBTMQRETTXN | Vi Debit Mid Qual Rtrn Trans |
| FEE | FVIDBTMQCHGBKTXN | Vi Debit Mid Qual Chrgbk Trans |
| FEE | FVIDBTMQRVSLTXN | Vi Debit Mid Qual Rev Trans |
| FEE | FMCDBTNQTXN | Mc Debit Non Qual Trans Fee |
| FEE | FMCDBTNQRETTXN | Mc Debit Non Qual Rtrn Trans |
| FEE | FMCDBTNQCHGBKTXN | Mc Debit Non Qual Chrgbk Trans |
| FEE | FMCDBTNQRVSLTXN | Mc Debit Non Qual Rev Trans |
| FEE | FVIDBTNQTXN | Vi Debit Non Qual Trans Fee |
| FEE | FVIDBTNQRETTXN | Vi Debit Non Qual Rtrn Trans |
| FEE | FVIDBTNQCHGBKTXN | Vi Debit Non Qual Chrgbk Trans |
| FEE | FVIDBTNQRVSLTXN | Vi Debit Non Qual Rev Trans |
| FEE | FMNTHLYADVNTGMCVDB | Monthly Advantage Fee Mcvdb |
| FEE | FDBTSNF | Debit Store And Fwd Fee |
| FEE | FDBTRESUBMSN | Debit Resubmission Fee |
| FEE | FDBTHSTCPTR | Host Capture Fee Debit |
| FEE | FAMXSLSDSCNT | Amex Sales Discount |
| FEE | FAMXSRCRG | Amex Surcharge Fee |
| FEE | FDSCVCHGBKDSCNT | Discover Chgbk Discount |
| FEE | FDSCVRVSLDSCNT | Discover Reversal Discount |
| FEE | FVIAUTHMCHNG | Visa Auth Matching |
| FEE | FPYPLSLSDSCNT | Paypal Sales Discount Fee |
| FEE | FMCCANTXN | Mastercard Canadian Tran Fee |
| FEE | FAUTHRQST | Authorisation Request |
| FEE | FDBTVOIDTXN | Debit Void Transaction Fee |
| FEE | FDBTMRCHDISERET | Debit Merchandise Return |
| FEE | FMNYTXFRDBTFUNDPTF | Money Transfer Debit Fund Ptf |
| FEE | FPINDBTCARDTXN | Pin Debit Card Transaction Fee |
| FEE | FEBTAUTHF18S | Ebt Auths |
| FEE | FEBTHSTCPTR | Host Capture Fee Ebt |
| FEE | FOUTSRCDTINVLDNRPRTNG | Outsrce Tin Validation Rprting |
| FEE | FOUTSRCD1099KRPRTNG | Outsrce 1099 K Reporting/File |
| FEE | FDBTMNYXFRDSCNTRATE | Money Transfer Debit Disc Rt |
| FEE | FVITXNCAN | Visa Canadian Tran Fee |
| FEE | FTINTFNBLNKORINVLD | Tin/Tfn Blank Or Invalid Fee |
| FEE | FTINTFNVLDTNSTRG | Tin/Tfn Validation/Storage Fee |
| FEE | FWEBSTUSAGE | Website Usage Fee |
| FEE | FIVRUSAGE | Ivr Usage Fee |
| FEE | FJBSCHKGRNTY | Check Guarantee Jbs Fee |
| FEE | FTCKCHKGRNTY | Check Guarantee Telecheck Fee |
| FEE | FCHKVRFYETC | Check Verification Etc |
| FEE | FCHKGRNTYTELECRDT | Check Guarantee Telecredit |
| FEE | FTAPEITEM | Tape Item Fee |
| FEE | FELTRNCITEM | Electronic Item Fee |
| FEE | FITEMIC | Items I/C Fee |
| FEE | FACCULNKDBTCARDAUTH | Acculynk Debit Card Auth Fee |
| FEE | FACCULNKPREAUTH | Acculynk Pre Auth Fee |
| FEE | FACCULNKVOIDAUTH | Acculynk Revrsal/Void Auth Fee |
| FEE | FDBTSLSDSCNT | Debit Sales Discount |
| FEE | FDBTAUTH | Debit Card Authorization Fee |
| FEE | FMCOTHRITMS | Mastercard Other Item Fee |
| FEE | FVIOTHRITM | Visa Other Item Fee |
| FEE | FVIAUTHSETTL | Visa Auth/Settle Fee |
| FEE | FEQPDLYDBILLING | Equipment Delay Billing |
| FEE | FTAAESDUKPTENCRYPTN | Transarmor Aes Dukpt Encryptio |
| FEE | FVIDMSTCAUTHFEET1LAC | Lac Vi Domestic Auth Fee T1 |
| FEE | FVIDMSTCAUTHFEET2LAC | Lac Vi Domestic Auth Fee T2 |
| FEE | FVIDMSTCAUTHFEET3LAC | Lac Vi Domestic Auth Fee T3 |
| FEE | FVIDMSTCAUTHFEET4LAC | Lac Vi Domestic Auth Fee T4 |
| FEE | FVIDMSTCAUTHFEET5LAC | Lac Vi Domestic Auth Fee T5 |
| FEE | FVIDMSTCCLRNCFEET1LAC | Lac Vi Domestic Clear Fee T1 |
| FEE | FVIDMSTCCLRNCFEET2LAC | Lac Vi Domestic Clear Fee T2 |
| FEE | FVIDMSTCCLRNCFEET3LAC | Lac Vi Domestic Clear Fee T3 |
| FEE | FVIDMSTCCLRNCFEET4LAC | Lac Vi Domestic Clear Fee T4 |
| FEE | FVIDMSTCCLRNCFEET5LAC | Lac Vi Domestic Clear Fee T5 |
| FEE | FCLVRSLSTAX | Clover Sales Tax |
| FEE | FVFONESVCMNTH | Verifone Monthly Service Fee |
| FEE | FVFONEESTTMGMT | Verifone Estate Mgt Fee |
| FEE | FDSCVUSXBRDRNONUSD | Ds Us Cross Border Fee, Nonusd |
| FEE | FDSVIASSMNTDB | Ds Visa Assessment Fee |
| FEE | FHDCVIASSMNTDB | Hdc Visa Assessment Fee |
| FEE | FCLVRDUOTRMNL | Clover Duo Terminal |
| FEE | FCLVRFLEX2NDGEN | Clover Flex 2Nd Gen |
| FEE | FMCDBTBLBK | Mc Debit Billback |
| FEE | FMCDBTCHIPBLBK | Mc Debit Chip Billback |
| FEE | FMCIRAMSVC | Mc Iram Service Fee |
| FEE | FINACTVTYMNTH | Monthly Inactivity Fee |
| FEE | FCHGBKRVSL | Chargeback Reversal Fee |
| FEE | FDSCVCASHADVNC | Discover Cash Advance |
| FEE | FDSCVCASHADVNCF21B | Ds Cash Advance |
| FEE | FQLDSCNT | Qual Discount |
| FEE | FFDMSLNKACCSS | Fdms Link Access Fee |
| FEE | FMCSIGCPTR | Mastercard Signature Capture |
| FEE | FVISIGCAPTR | Visa Signature Capture |
| FEE | FDNRSIGCPTR | Diners Signature Capture |
| FEE | FPINDBTADJ | Pin Debit Adjustment Fees |
| FEE | FBOACARDTXNRBT | Boa Card Transaction Rebate |
| FEE | FDSMCGLBLWHLSLTRAVB2B | Ds Mc Glbl Wsale Trav B2B Fee |
| FEE | FHDCMCGLBLWHLSLTRAVB2B | Hdc Mc Glbl Wsale Trav B2B Fee |
| FEE | FAMXSIGCAPTR | Amex Signature Capture |
| FEE | FDSCVSIGCPTR | Discover Signature Capture |
| FEE | FWARNGBLTN | Warning Bulletin Fee |
| FEE | FDEPSTCHANGENOTICE | Deposit Change Notice Fee |
| FEE | FBNKWR | Bankwire Fee |
| FEE | FBTCHSETLMNT | Batch Settlement Fee |
| FEE | FPVTLBLSIGCPTR | Private Lbl Signature Capture |
| FEE | FNONSWIPEDDSCNTRATE | Non Swiped Discount Rate |
| FEE | FSWIPEDDSCNT | Swiped Discount Rate |
| FEE | FNONSWIPEDTXNF23W | Non Swiped Transaction Fee |
| FEE | FDSCVASSMNT | Discover Assessment Fee |
| FEE | FICPLUSSRCHRG | Interchange Plus Surcharge |
| FEE | FMCASSMTTXNAMTGT1K | Mc Assessmnt Tran Amt >=$1K |
| FEE | FVITXNINTGRTY | Vi Transaction Integrity Fee |
| FEE | FREPRNTSTMT | Reprint Statement |
| FEE | FDSCVSRCHRGICPLUS | Discover Surcchg Intchg Plus |
| FEE | FFRAUDDTCTOVERTHRSHLD | Fraud Detect Over Threshhold |
| FEE | FMCMERCHLOCTNMNTH | Mc Merch Monthly Location |
| FEE | FMCASSMNTCRDTPR | Mc Pr Assessment Fee Cr |
| FEE | FMCASSMNTCRDTPRINT | Mc Pr Intl Assessment |
| FEE | FMCFRGNASSMNT | Mastercard Foreign Assessment |
| FEE | FVIFRGNASSMNT | Visa Foreign Assessment Fee |
| FEE | FADTNLLOCAPPL | Additional Loc Application Fee |
| FEE | FVIACCTUPDTXN | Visa Acct Upd Tran Fee |
| FEE | FAMXACCTUPDTRTXN | Amex Acct Upd Per Tran Fee |
| FEE | FTIRSFAXDLVRY | Tirs Fax Del Fee |
| FEE | FTIRSCSRRPTGEN | Tirs Csr Report Gen |
| FEE | FTIRSMAIL | Tirs Mail |
| FEE | FTIRSMAILPAGES | Tirs Mail Pages |
| FEE | FCSTMBROADCASTDLVRY | Custom Broadcast Del Fee |
| FEE | FRSKRPTNG | Risk Reporting Fee |
| FEE | FCSTMRPTACCTID1St | Custom Rpt Acc Id (1St) |
| FEE | FAMXACCSS | American Express Access Fee |
| FEE | FFRAUDDTCTPERTXN | Fraud Detect Per Tran Fee |
| FEE | FFRAUDDTCTLOGINRGSTRN | Fraud Detect Login & Registrtn |
| FEE | FMCFRGNHNDLNG | Mc Foreign Handling Fee |
| FEE | FVIFRGNHNDLNG | Visa Foreign Handling Fee |
| FEE | FRTVL | Retrieval Fee |
| FEE | FNONCHGBLACCSSMNTH | Nonbankcard Monthly Access Fee |
| FEE | FTRAILINGCHGBK | Trailing Chargeback |
| FEE | FTRAILINGCHGBKRVSL | Trailing Chargeback Reversal |
| FEE | FPRINTSTMT | Print Statement Fee |
| FEE | FEMAILSTMT | Email Statement Fee |
| FEE | FDFMSETUP | Setup Fee Data File Manager |
| FEE | FDFMMNTH | Mthly Fee Data File Manager |
| FEE | FDFMRUNNOWOVER8GB | Run Now File Over 8 Gb Dfm |
| FEE | FREGPINSIGCRDTRETDSCNT | Reg Pin/Sig/Credit Ret Disc |
| FEE | FVIWHLSLASSMNTCRDT | Visa Wholesale Assess Fee Cr |
| FEE | FEBTONLNCASHTXN | Ebt Online Cash Per Tran Fee |
| FEE | FEBTONLNSNAPTXN | Ebt Online Snap Per Tran Fee |
| FEE | FEBTONLNRFNDTXN | Ebt Online Refund Per Tran Fee |
| FEE | FETCMINMNTH | Etc Monthly Minimum |
| FEE | FBTCHSTMTCOMNCTN | Batch Stlmnt Communication Fee |
| FEE | FCARDLVLRESULTENHNCMNT | Card Level Result Enhancement |
| FEE | FMCWHLSLASSMNT | Mc Wholesale Assessment |
| FEE | FVIWHLSLASSMNTDBT | Visa Wholesale Assess Fee Db |
| FEE | FVIKBYTE | Visa Kilobyte Fee |
| FEE | FMCKBYTE | Mastercard Kilobyte Fee |
| FEE | FPYMNTPROSOFTWRMNTNC | Payment Pro Software Maint Fee |
| FEE | FREGPINSIGCRDTRETTXN | Reg Pin/Sig/Credit Ret Trn Fee |
| FEE | FCHKGRNTEAUTH | Check Guarantee Auth |
| FEE | FCHKGRNTEBLWMIN | Check Guarantee Below Min |
| FEE | FCHKGRNTERJCTD | Check Guarantee Rejected |
| FEE | FWSINFOMGRCONNECTTIME | Ws Info Mgr. Connect Time |
| FEE | FWSINFOMGRLINESTXMITED | Ws Info Mgr. Lines Transmitted |
| FEE | FIRTVL | Incoming Retrieval Fee |
| FEE | FAMXASSMNT | Amex Assessment Fee |
| FEE | FWSINFOMGRTXNSTORED | Ws Info Mgr. Trans Stored |
| FEE | FCHGBKRTVL | Chargeback & Retrieval Fee |
| FEE | FMCADVNCME | Advanceme.Com Fee Mastercard |
| FEE | FVIADVNCME | Advanceme.Com Fee Visa |
| FEE | FMMVMNTH | Mmv Monthly Fee |
| FEE | FDSCHGBKRTVL | Ds Chargeback & Retrieval Fee |
| FEE | FDNRCHGBK | Diners Chargeback Fee |
| FEE | FCNRCHGBKRVSL | Diners Chrgback Rev Fee |
| FEE | FVIDUES | Visa Dues |
| FEE | FSSNLACTVTN | Seasonal Activation Fee |
| FEE | FMMVACCSSMNTH | Mmv Monthly Access Fee |
| FEE | FMMVUSAGE | Mmv Usage Fee |
| FEE | FCASHBK | Cashback Fee |
| FEE | FTRMNL | Terminal Fee |
| FEE | FDISPTMGMTACCSSMNTH | Dispute Man. Mthly. Access Fee |
| FEE | FRSASLSPROMO3 | Rsa Sales Promo 3 |
| FEE | FRSASLSPROMO4 | Rsa Sales Promo 4 |
| FEE | FTADLYTKNFILE | Transarmor Daily Token File |
| FEE | F3DSVALUEADD | 3D Secure Value Add Fee |
| FEE | F3DSDECSN | 3D Secure Decision Fee |
| FEE | F3DSSETUP | 3D Secure Set Up Fee |
| FEE | F3DSMNTH | 3D Secure Monthly Fee |
| FEE | FFSTRSTLMNTLLOYDSBNK | Faster Settlement Lloyds Bank |
| FEE | FFSTRSTLMNT | Faster Settlement Fee |
| FEE | FCLVRSUPPRT | Clover Support Fee |
| FEE | FONETIMESETUP | Onetime Setup Fee |
| FEE | FACCTONFILE | Account On File Fee |
| FEE | FMCDISPTADMIN | Mastercard Dispute Admin Fee |
| FEE | FMCDISPTREFND | Mastercard Dispute Refund Fee |
| FEE | FHRPCAUMCSETUP | Hrp Cau Mc Set Up Fee |
| FEE | FAFSNVGTR | Afs Nvgtr Fee 8883729588 |
| FEE | FRWRDBLBKSRCHRG | Reward Billbk Srchrg |
| FEE | FSRCHRGTXN | Surcharge Trans Fee |
| FEE | FSVIVRUSAGECANMINT | Sv Ivr Usage Canadian Minute |
| FEE | FSVIVRUSAGEPAYPHNMINT | Sv Ivr Usage Pay Phone Minute |
| FEE | FHRPSETUP | Hrp Setup Fee |
| FEE | FPRCSRONLINEINQ | Processor Online Inquiry |
| FEE | FEDRRPTNG | Edr Reporting Fee |
| FEE | FAGNTBNKSTLMNTAUTO | Agent Bank Settlement Auto |
| FEE | FALTPAYPYMNTAPIACCSSMNTH | Mo. Alt Payment Api Access Fee |
| FEE | FCYBRCASHACCSS | Cybercash Access Fee |
| FEE | FVRTUALAPPLCTN | Virtual Application Fee |
| FEE | FMYBIZPERKS | My Biz Perks |
| FEE | FWEBHOSTING | Web Hosting Fee |
| FEE | FSUREPAYFRAUDSVCSETUP | Surepay Fraud Svc Setup Fee |
| FEE | FPRFTABLTYRECAPRPRT | Profitability Recap Report Fee |
| FEE | FPRFTABLTYANLYSISPRPRT | Profitability Analysis Rpt Fee |
| FEE | FACTVINACTVMRCHRPT | Active/Inactive Merchant Rept |
| FEE | FALPHANMRCLISTINGS | Alpha/Numeric Listings Fee |
| FEE | FEXCSVCHGBKRPT | Excessive Chargebacks Rept Fee |
| FEE | FTOPMRCHNTBYVOLRPT | Top Merchant By Volume Rpt Fee |
| FEE | FTOPBOTTOMMRCHNTRVNURPT | Top/Bottom Merchant By Revenue |
| FEE | FINACTVMRCHNTBYDAYSRPT | Inactive Merchants By Days Rpt |
| FEE | FAUTHMTHDSMRYRPT | Auth Method Summary Report Fee |
| FEE | FMMVSETUP | Mmv Set Up Fee |
| FEE | FVLMNTH | Valuelink Monthly Fee |
| FEE | FMASSCD | Mass Cd Fee |
| FEE | FSVCPRTCTNPRGM | Service Protection Program |
| FEE | FDLYXCPTNRPT | Daily Exception Report Fee |
| FEE | FDLYTELEMRKTNGRPT | Daily Telemarketing Report Fee |
| FEE | FNEWACCTTRCKINGRPT | New Account Tracking Rept Fee |
| FEE | FACTCLNTTRCKINGRPT | Active Client Tracking Rpt Fee |
| FEE | FTXNLOGRPT | Transaction Log Report Fee |
| FEE | FMRCHNTTOTALSRPT | Merchant Totals Report Fee |
| FEE | FRAWDATATAPERPT | Raw Data Tape Report Fee |
| FEE | FBERSREP | Bers Report Fee |
| FEE | FPOSPRTNR | Pos Partner |
| FEE | FSFTWRUPGRD | Software Upgrade |
| FEE | F1STYRANNUAL | First Year Annual Fee |
| FEE | FDSCVACCTUPDTMNTH | Discvr Acct Upd Mnthly Fee |
| FEE | FCLNTLNMNTHF32L | Clientline Monthly Fee |
| FEE | F32SETRMNLBILLING | 32Se Terminal Billing Fee |
| FEE | FMULTITXNRPT | Multi Trans Report Fee |
| FEE | FETCRPT | Etc Report Fee |
| FEE | FTRMNLSVC | Terminal Service Fee |
| FEE | FSTMTMNTH | Monthly Statement Fee |
| FEE | FEXPRSCNCTSVC | Express Connect Service Fee |
| FEE | FNDCDLYACTVTYRPT | Ndc Daily Activity Reports |
| FEE | FSCANPRCSNGMNTH | Monthly Scan Processing Fee |
| FEE | FPRCSNG | Processing Fee |
| FEE | FLLTYPRGMMNTH | Loyalty Pgm Mntly Fee |
| FEE | FGCSCARDMNTH | Gcs Card Mntly Fee |
| FEE | FAMXACCUPDTRMNTH | Amex Acct Upd Mnthly Fee |
| FEE | FANNUALPNC | Pnc Annual Fee |
| FEE | FSIGCLUB | Signature Club Fee |
| FEE | FBNFTPKG | Benefits Package Fee |
| FEE | FISDN | Isdn Fee |
| FEE | FISDNRBT | Isdn Rebate |
| FEE | FCPULNK | Cpu Link Fee |
| FEE | FMRCHNTADVNTGSVC | Merchant Advantage Service Chg |
| FEE | F3TIERSVCCRGMNTH | 3 Tier Monthly Service Charge |
| FEE | FACCTSETUP | Account Setup Fee |
| FEE | FMCBLBKAMT | Mc Billback Amount |
| FEE | FVIBLBKAMT | Visa Billback Amount |
| FEE | FMISCCRDTADJ | Misc Credit Adjustments |
| FEE | FMISCDBTADJ | Misc Debit Adjustments |
| FEE | FMISXCRDTADJ | Misx Credit Adjustments |
| FEE | FMISXDBTADJ | Misx Debit Adjustments |
| FEE | FCASHMGMTSVCCRGHMNTH | Cash Mgmt Monthly Service Chg |
| FEE | FALERTSVCCHRGMNTH | Alert Monthly Service Charge |
| FEE | FCASEMGMTSVGCHRGMNTH | Case Mgmt Monthly Service Chg |
| FEE | FMEMBRFEEBNK | Member Fee Bank Fee |
| FEE | FVIPOSACCSS | Visa Pos Access Fee |
| FEE | FDLYMNLRSTRT | Daily Manual Restart Fee |
| FEE | FTELECOM | Telecommunications Fee |
| FEE | FMNTNCMNTH | Monthly Maintenance Fee |
| FEE | FLINEMNTRNG | Line Monitoring Fee |
| FEE | FLINEMNTRNGF356 | Line Monitoring Fee |
| FEE | FWSDATADRCTRPT | Ws Data Direct Report Fee |
| FEE | FHRPMINMNTH | Hrp Monthly Minimum Fee |
| FEE | FWX110ONLNDBTDLYRPT | Wx 110 Online Debit Daily Rpt |
| FEE | FWS510DLYCPTRRPT | Ws 510 Daily Capture Reports |
| FEE | F560OR566MTHLYCPTRRPT | Ws 560/566 Mthly Capture Rpts |
| FEE | FONLNDBTLCTN | Online Debit Location Fee |
| FEE | FWSINFOMNGRMNTH | Ws Info Mgr. Monthly Fee |
| FEE | FHRPTXN | Hrp Transaction Fee |
| FEE | FENVYTRMNLLEASE | Envoy Terminal Lease |
| FEE | FEQPMNTNCDLR3PERTRMNL | Equip Maint @ $3.00/Terminal |
| FEE | FEQPMNTNCDLR3PERTRMNLF374 | Equip Maint @ $3.00/Printer |
| FEE | FTRMNLLEASE | Terminal Lease |
| FEE | FPINPADRNTL | Pin Pad Rental Fee |
| FEE | FPRNTRBILING | Printer Billing |
| FEE | FPOSEQPBILING | Pos Equipment Billing |
| FEE | FPCSSFTWRBILING | Pc Software Billing |
| FEE | FNDCLEASELINE | Ndc Lease Line Fee |
| FEE | FAMXCHRGS | Amex Charges |
| FEE | FSVCCHRG | Service Charge |
| FEE | FMRCHNTACTVACCT | Merchant Active Account Fee |
| FEE | FHLPDSK | Help Desk Fee |
| FEE | FDLYDPSTCNFM | Daily Deposit Confirmation |
| FEE | FWKLYDPSTCNFM | Weekly Deposit Confirmation |
| FEE | FMNTHLYRPT | Monthly Report Fee |
| FEE | FENVOYLEASELINE | Envoy Lease Line Fee |
| FEE | FINTRNTSVC | Internet Service Fee |
| FEE | FLEASEDLINECHRG | Leased Line Charge |
| FEE | FFDMOBLPAYMUSER | Fd Mobilepay M User |
| FEE | FFIXEDEXPNS | Fixed Expense |
| FEE | FFDMOBLPAYSUSER | Fd Mobilepay S User |
| FEE | FBNDLS | Bundles |
| FEE | FMISCCARDORDR | Card Order Misc |
| FEE | FCRANTHONYPVTLBL | C.R. Anthony Private Label |
| FEE | FGCPROMOSETUP | Gift Card Promo Setup Fee |
| FEE | FGCINTRNTTXN | Internet Gift Card Trnsactions |
| FEE | FGCSTNDPRJCTSETUP | Standard Gc Project Set Up Fee |
| FEE | FGCSTNDREPTSETUP | Standard Gc Report Set Up Fee |
| FEE | FGCSTNDRPTMNTH | Standard Gc Report Monthly Fee |
| FEE | FGCSTNDMISCSETUP | Standard Gc Misc Set Up Fee |
| FEE | FGCSTNDMISCMNTH | Standard Gc Misc Monthly Fee |
| FEE | FVRTLCARDRANGE | Virtual Card Range |
| FEE | FVRTLCARDRANGEFILE | Virtual Card Range File |
| FEE | FEXTNDEDRPT | Extended Reporting |
| FEE | FSVCARDTXN | Sv Card Transaction |
| FEE | FSVCARDINTRNTTXN | Sv Crd Tran Internet |
| FEE | FSVCARDBTCHTXN | Sv Card Trans Batch |
| FEE | FSVCARDACTVTN | Sv Card Activation |
| FEE | FSVCARDRDMPTN | Sv Card Redemption |
| FEE | FSVCARDRLOAD | Sv Card Reload |
| FEE | FSVCARDRDMPTNUNLCK | Sv Card Redemption Unlock |
| FEE | FSVCARDNOPOS | Sv Card Non Pos |
| FEE | FSVCARDBLNCINQ | Sv Card Balance Inquiry |
| FEE | F4WSUTRMNLBILLING | 4Wsu Terminal Billing Fee |
| FEE | FSVCARDINACTVCLSDTXN | Sv Card Tran Inactive Closed |
| FEE | FAUTOLOADRGSTRN | Auto Reload Registration |
| FEE | FAUTRLDTXNINITN | Auto Reload Trans Initiation |
| FEE | FCLPPRTDMMSG | Clpp Rtdm Message Fee |
| FEE | FCLPPRTDMMNTH | Clpp Rtdm Monthly Fee |
| FEE | F40PRTRMNLBILLING | 40Pr Terminal Billing Fee |
| FEE | FE4PAYITBUNDLE0TO5USR | E4Payit Bundle (0 5 Users) |
| FEE | FE4PAYITBUNDLE6TO10USR | E4Payit Bundle (6 10 Users) |
| FEE | FE4PAYITBNDL | E4Payit Bundle (Custom) |
| FEE | FCNFRMTNLTR | Confirmation Letter Fee |
| FEE | FEQPTOTLMNTH | Total Monthly Equipment Fee |
| FEE | FMOOREBSNSFRM | Moore Business Forms |
| FEE | FAVSLCLAUTH | Avs Local Authorization Fee |
| FEE | FAVSWATSAUTH | Avs Wats Authorization Fee |
| FEE | FAVSRGNLAUTH | Avs Regional Authorization Fee |
| FEE | FAVS950AUTH | Avs 950 Call Authorization Fee |
| FEE | FEMVAUTH | Emv Auth Fee |
| FEE | FDNRSPNSRSHP | Diners Sponsor Fee |
| FEE | FSFTWRSUPRTSNGL | Software Support(Single) |
| FEE | FMRCHNTCLUB | Merchant Club |
| FEE | FMRCHNTCLUBMULTI | Merchant ClubMulti |
| FEE | FINTRNTACCSSSUPRT | Internet Access/Support Fee |
| FEE | FGTWYF417 | Gateway Fee |
| FEE | FNETSCAPE | Netscape |
| FEE | FPCIDSSMNGMT | Pci Dss Management Fee |
| FEE | FPCIDSSMNGMTPRM | Pci Dss Management Pm |
| FEE | FPCIDSSNONCMPLNC | Pci Dss Non Compliance |
| FEE | FWEBLNCHR | Web Launcher Fee |
| FEE | FACCULNKONLNDBTDNL | Acculynk Online Debit Denial |
| FEE | FACCULNKPREAUTHDBTDNL | Acculynk Pre Auth Debit Denial |
| FEE | FACCULNKDBTRVSLDBTDNL | Acculynk Rvrsl/Void Dbt Denial |
| FEE | FNTWKACCSS | Network Access Fee(Debit) |
| FEE | F4210TRMNLBILLING | 4210 Terminal Billing Fee |
| FEE | FCSTMRSVC | Customer Service Fee |
| FEE | FHLMRKACH | Hallmark Ach Fee |
| FEE | FDBTLOCTN | Debit Location Fee |
| FEE | FTSYSLEASELN | Tsys Lease Line Fee |
| FEE | FJOINING | Joining Fee |
| FEE | FGLBLGTWYVRTLTRMNL | Global Gtway Virt Terminl Fee |
| FEE | FVRTLCHCK | Virtual Check Fee |
| FEE | FSTRLCLAUTH | Star Local Auth Fee |
| FEE | FSTRWATSAUTH | Star Wats Auth Fee |
| FEE | FHNRLCLAUTH | Honor Local Auth Fee |
| FEE | FHNRWATSAUTH | Honor Wats Auth Fee |
| FEE | FHNR950AUTH | Honor 950 Auth Fee |
| FEE | FINTRLNKLCLAUTH | Interlink Local Auth Fee |
| FEE | FINTRLNKWATSAUTH | Interlink Wats Auth Fee |
| FEE | FINTRLNK950AUTH | Interlink 950 Auth Fee |
| FEE | FMACLCLAUTH | Mac Local Auth Fee |
| FEE | FMACWATSAUTH | Mac Wats Auth Fee |
| FEE | FMAC950AUTH | Mac 950 Auth Fee |
| FEE | FMSTRWATSAUTH | Maestro Wats Auth Fee |
| FEE | FMSTR950AUTH | Maestro 950 Auth Fee |
| FEE | FNYCELCLAUTH | Nyce Local Auth Fee |
| FEE | FNYCEWATSAUTH | Nyce Wats Auth Fee |
| FEE | FNYCE950AUTH | Nyce 950 Auth Fee |
| FEE | FPULSE950AUTH | Pulse 950 Auth Fee |
| FEE | FBNKCARDAUTH | Bankcard Auths |
| FEE | FOTHRCARDAUTH | Other Card Auths |
| FEE | FWRLSCOMMTXN | Wireless Comm Transaction Fee |
| FEE | FAVSINTRNTAUTH | Internet Avs Auth Fee |
| FEE | FAVSBTCH | Batch Avs Fee |
| FEE | FAVSCPU | Cpu Avs Fee |
| FEE | FAUTHCMNCTN | Auth Communication Fee |
| FEE | FATMDBTCMNCTN | Atm/Debit Communication Fee |
| FEE | FVIKBYTETXN | Visa Kilobyte Transaction Fee |
| FEE | FMCKBYTETXN | Mastercard Kilobyte Trans Fee |
| FEE | FMOBLPOSPERUSR | Mobile Pos Per User Fee |
| FEE | FBMLRETDSCNT | Bml Discount Return Fee |
| FEE | FALIPAYSVC | Alipay Service Fee |
| FEE | FHOSTINGMNTH | Monthly Hosting Fee |
| FEE | FBMLRETTXN | Bml Transactions Return Fee |
| FEE | FMCAUTHONLY | Auth Only Fee Mc |
| FEE | FVIAUTHONLY | Auth Only Fee Vi |
| FEE | FMCHOSTCAPTRNONFUEL | Host Capture Fee Non Fuel Mc |
| FEE | FVIHOSTCAPTRNONFUEL | Host Capture Fee Non Fuel Vi |
| FEE | FMCHOSTCAPTRFUEL | Host Capture Fee Fuel Comp. Mc |
| FEE | FVIHOSTCAPTRFUEL | Host Capture Fee Fuel Comp. Vi |
| FEE | FPYPLRETDSCNT | Paypal Return Trans Fee |
| FEE | FPYPLASSMNT | Paypal Assessment Fee |
| FEE | FPYPLIINQSMS | Incoming Inquiry Sms Paypal |
| FEE | FVISPCLARLN | Visa Special Airline Fee |
| FEE | FGLBLGTWYWAZZU | Global Gateway Wazzu Gtway Fee |
| FEE | FPYPLICLAIMSMS | Incoming Claim Sms Paypal |
| FEE | FPYPLICHGBKSMS | Incoming Chargeback Sms Paypal |
| FEE | FPYPLOMRCHAPPLSMS | Out Merch Appeal Sms Paypal |
| FEE | FMCCNVNCADJ | Mc Conv Fee Adj % |
| FEE | FVICNVNCADJ | Visa Conv Fee Adj % |
| FEE | FGLBLGTWYAPI | Global Gateway Api Fee |
| FEE | FHPMLNMGTWY | Hp Millennium Gateway Fee |
| FEE | FWPCMINPRCSNG | Wpc Minimum Processing |
| FEE | FPYPLNQICHGBKSMS | Nw Incoming Chrgbck Paypal Sms |
| FEE | FCHGBKPRTCNPRGM | Chargeback Protection Program |
| FEE | FRSRCONLNMNTH | Re$Orce Online Monthly Fee |
| FEE | FUWRTNGRGSTRN | Underwriting/Registration Fee |
| FEE | FSCRTYFRAUDMNGMT | Security/Fraud Management Fee |
| FEE | FCLCTNRSRVFEE | Collections/Reserve Fee |
| FEE | FNONFLMNTRQST | Nonfulfillment Request Fee |
| FEE | FFUTUREPRJCT | Available For Future Project |
| FEE | FFAILURETOTRMNT | Failure To Terminate Fee |
| FEE | FVISPSNRSHPTXN | Sponsorship Trans Fee Visa |
| FEE | FMCSPSNRSHPTXN | Sponsorship Trans Fee Mc |
| FEE | FGLBLGTWYCART | Global Gateway Cart Fee |
| FEE | FFAXSTMTMNTH | Monthly Fax Statement Fee |
| FEE | FWRLSCMNCTN | Wireless Comm Monthly Fee |
| FEE | FSUREPAYFRAUDMNTH | Surepay Fraud Monthly Svc |
| FEE | FICEPACMNTH | Icepac Monthly Fee |
| FEE | FVOYTAXRPRTNG | Voyager Tax Reporting Fee |
| FEE | FMCNOAUTH1STCHGBK | No Auth 1St Cb Mc Fee |
| FEE | FMCNOAUTHRVSL | No Auth Reversal Of Mc Fee |
| FEE | FVIAUTHOPTAPPRVDRTRY | Auth Opt Visa Appvd Retry Perc |
| FEE | FVIAUTHOPTDCLNDRTRYPCT | Auth Opt Visa Decld Retry Perc |
| FEE | FDSCVPROMORBT | Discover Promo Rebate |
| FEE | FMCIDNTYCHK2DOT0 | Mc Identity Check 2.0 Fee |
| FEE | FMCIDNTYCHK2DOT0CAP | Mc Identity Check 2.0 Fee Cap |
| FEE | FAUTHOPTPTSLKUP | Auth Opt Pts Look Up Fee |
| FEE | FLLTYPERLCTNSETUP | Loyalty Per Location Set Up |
| FEE | FLLTYPROMOSETUP | Loyalty Promo Setup Fee |
| FEE | FLLTYVOIDRVSL | Loyalty Void/Reversal |
| FEE | FLLTYPERTXN | Loyalty Per Transaction Fee |
| FEE | FLLTYPERACCTRGSTRN | Loyalty Per Acct Registration |
| FEE | FLLTYPERLCTNMNTH | Loyalty Per Location Monthly |
| FEE | FLLTYMNTNC | Loyalty Maint Fee/Pos |
| FEE | FMMVEIDSHLPDSK | Mmv Eids Help Desk Fee |
| FEE | FNONBNKCARDCHGBK | Non Bankcard Chargeback Fee |
| FEE | FMCRLTMACCTUPDTRSVC | Rtime Mc Acct Updtr Srvc Fee |
| FEE | FMCAUTHOPTAPPRVDRTRY | Auth Opt Mc Appvd Retry Fee |
| FEE | FDSCVAUTHOPTAPPRVDRTRY | Auth Opt Disc Appvd Retry Fee |
| FEE | FMCAUTHOPTAPPRVDRTRYPCT | Auth Opt Mc Appvd Retry Percen |
| FEE | FDSCVAUTHOPTAPPRVDRTRYPCT | Auth Opt Disc Appvd Retry Perc |
| FEE | FMCAUTHOPTDCLNDRTRYPCT | Auth Opt Mc Decld Retry Percen |
| FEE | FDSCVAUTHOPTDCLNDRTRYPCT | Auth Opt Disc Decld Retry Perc |
| FEE | F490NTRMNLBILLING | 490N Terminal Billing Fee |
| FEE | FPREARBORCOMP | Pre Arb/Pre Comp Fee |
| FEE | FPREARBORCOMPCASE | Arb/Comp Case Filing Fee |
| FEE | FDSCVFILEDARB | Discover Filed Arb Fee |
| FEE | FDSCVPCTOFSLS | Discover Percent Of Sales Fee |
| FEE | FSTRDVLCARDACTVN | Stored Val Crd Activation % |
| FEE | FSTRDVLCARDRELOAD | Stored Val Crd Reload % |
| FEE | FIPGMNTH | Ipg Monthly Fee |
| FEE | FIPGSETUP | Ipg Setup Fee |
| FEE | FIPGAUTH | Ipg Authorization Fee |
| FEE | FFUELMANFULLSVCIC | Fuelman Full Srvc Intrchng Fee |
| FEE | FTRMNLUSG | Terminal Usage Fee |
| FEE | FTRMNLMNTNCCHRG | Terminal Maintenance Charge |
| FEE | FTRMNLBILLINGTAX | Terminal Billing Tax |
| FEE | FMCDBTICPLUS | Mc Debit Interchange Plus |
| FEE | FMCDBTICPLUSSLS | Mc Debit Ic Plus Sales |
| FEE | FMCDBTCHIPICPLUS | Mc Debit Chip Interchange Plus |
| FEE | FMCDBTCHIPICPLUSSLS | Mc Debit Chip Ic Plus Sales |
| FEE | FMONDEXIC | Mondex Interchange Fee |
| FEE | FUOFPAIC | U Of Pa Interchange Fee |
| FEE | FVLIC | Value Link Interchange Fee |
| FEE | FDSCVACCSS | Discover Access Fee |
| FEE | FDSCVICSLSONLY | Discover Interchng Sales Only |
| FEE | FEMESSOIC | Em Esso Interchange |
| FEE | FEMCARCAREONEIC | Em Car Care One Interchange |
| FEE | FEMFLEETIC | Em Fleet Interchange |
| FEE | FEMPLCCIC | Em Plcc Interchange |
| FEE | FVIICF549 | Visa Interchange |
| FEE | FICH | Interchange Fee |
| FEE | FAGNTIC | Agent Interchange Fee |
| FEE | FVIIC | Visa Interchange Fee |
| FEE | FVIWHLSLIC | Wholesale Visa Interchange Fee |
| FEE | FMCICF560 | Mastercard Interchange Fee |
| FEE | FMCICF563 | Mc Interchange Fee |
| FEE | FMCICF564 | Mc Interchange |
| FEE | FMCWHLSLIC | Wholesale Mc Interchange Fee |
| FEE | FAMXWHLSLIC | Wholesale Amex Interchange Fee |
| FEE | FACCELDBTATMNTWK | Dbt/Atm Accel Ntwk Fees |
| FEE | FALSKDBTATMNTWK | Dbt/Atm Alsk Optn Ntwk Fees |
| FEE | FAFFNDBTATMNTWK | Dbt/Atm Affn Ntwk Fees |
| FEE | FHONORDBTATMNTWK | Dbt/Atm Honor Ntwk Fees |
| FEE | FNYCEDBTATMNTWK | Dbt/Atm Nyce Ntwk Fees |
| FEE | FCU24DBTATMNTWK | Dbt/Atm Cu24 Ntwk Fees |
| FEE | FPULSEDBTATMNTWK | Dbt/Atm Pulse Ntwk Fees |
| FEE | FDNRWHLSLIC | Wholesale Diners Interchg Fee |
| FEE | FDBTPREAUTH | Debit Pre Auth |
| FEE | FPYMNTPASSTHRU | Payment Pass Thru Fees |
| FEE | FPYMNTDCLNPASSTHRU | Payment Decline Pass Thru Fees |
| FEE | FFDMSDBTGTWYIC | Fdms Debit Gateway Interchange |
| FEE | FDBTDCLNIC | Debit Decline Interchange Fee |
| FEE | FDBTWHLSLINT | Wholesale Debit Int Fee |
| FEE | FSTRIC | Star Interchange Fee |
| FEE | FINTRLNKIC | Interlink Interchange Fee |
| FEE | FSZMDBTATMNTWK | Dbt/Atm Shazam Ntwk Fees |
| FEE | F5991TRMNLBILLING | 5991 Terminal Billing |
| FEE | FVIRSK | Visa Risk Fee |
| FEE | FAMXOTHRITMS | Amex Other Items Fee |
| FEE | FDSCVOTHRITMS | Discover Other Items Fee |
| FEE | FMACDBTOTHRITMS | Mac Debit Other Items |
| FEE | FMSTRDBTOTHRITMS | Maestro Debit Other Items Fee |
| FEE | FINTLNKDBTOTHRITMS | Interlink Debit Other Items |
| FEE | FNYCEDBTOTHRITMS | Nyce Debit Other Items Fee |
| FEE | FEXPLRDBTOTHRITMS | Explore Debit Other Items Fee |
| FEE | FHNRDBTOTHRITMS | Honor Debit Other Items Fee |
| FEE | FPULSEDBTOTHRITMS | Pulse Debit Other Items Fee |
| FEE | FCASHSTNDROTHRITEMS | Cash Station Dr Oth Items Fee |
| FEE | FAFFNDBTOTHRITMS | Affn Debit Other Items Fee |
| FEE | FAMXOTHRVOL | Amex Other Volume Fee |
| FEE | FMACNETDSCNT | Mac Net Discount Fee |
| FEE | FINTRLNKDSCNT | Interlink Net Discount Fee |
| FEE | FNYCENETDSCNT | Nyce Net Discount Fee |
| FEE | FEXPLRNETDSCNT | Explore Net Discount Fee |
| FEE | FHNRNETDSCNT | Honor Net Discount Fee |
| FEE | FINTRNTJOINING | Internet Joining Fee |
| FEE | FINTRNTSFTWR | Internet Software Fee |
| FEE | FSFTWRVAT20PCTINT | Vat On Int Software Fee 20.0% |
| FEE | FINTGRTDVATMNTH | Mnth Integrated Fee Vat |
| FEE | FADTNLTXNCHRGVAT20PCTINT | Vat Int Addl Trans Chgs 20.0% |
| FEE | FTRMNLRNTL20PCTVAT | Vat Terminal Rental Fee 20.0% |
| FEE | FMRCHNTPAPERSTMTVAT | Merchant Paper Statement Vat |
| FEE | FSCRTYMNGDSVCVAT | Security Managed Service Vat |
| FEE | FFLATMNTH | Flat Monthly Fee |
| FEE | FGTWYTXN | Gateway Transaction Fee |
| FEE | FGTWYTXN20PCTVAT | Vat Gateway Tran Fee 20.0% |
| FEE | FGTWYTXNMIN | Min Gateway Tran Fee |
| FEE | FGTWYTXN20PCTVATF6JZ | Vat Min Gateway Tran Fee 20.0% |
| FEE | FVIECOMMOTOUKANDEU | Visa Uk & Eu E Comm/Moto Fee |
| FEE | FVIECOMMOTOTXNUKANDEU | Vi Uk&Eu E Comm/Moto Per Item |
| FEE | FVIECOMMOTOINT | Visa Int E Comm/Moto Fee |
| FEE | FVIECOMMOTOINTITM | Vi Int E Comm/Moto Per Item |
| FEE | FMSTRECOMEU | Mcard/Maestro Eu E Comm Fee |
| FEE | FMCECOMPERITMEU | Mcard/Maes Eu E Com P Item Fee |
| FEE | FMSTRECOMEUINT | Mcard/Maestro Int.E Comm Fee |
| FEE | FMCECOMPERITMINT | Mcard/Maes Int.Ecom P Item Fee |
| FEE | FMCCRDTASSMNTEU | Mcard Cr Eu Assessment Fee |
| FEE | FMCCRDTASSMNTEUITM | Mcard Cr Eu Assess Item Fee |
| FEE | FVICRDTASSMNTEU | Visa Cr Eu Assmt Fee |
| FEE | FVICRDTASSMNTEUITM | Visa Cr Eu Assmt Per Item Fee |
| FEE | FMCCRDTASSMNTEUF6KM | Mcard Dr / Maes Eu Assess Fee |
| FEE | FMCDRASSMNTTXNEU | Mcard Dr/Maes Eu Assmt Itm Fee |
| FEE | FVIDRVPAYASSMNT | Visa Dr / V Pay Assessment Fee |
| FEE | FVIDRVPAYASSMNTF6KP | Visa Dr / Vpay Assmt Item Fee |
| FEE | FDNRASSMNTEU | Diners Eu Assessment Fee |
| FEE | FDNRASSMNTEUITM | Diners Eu Assmt Per Item Fee |
| FEE | FMCASSMNTINT | Mcard Int.Assessment Fee |
| FEE | FMCASSMNTINTITM | Mcard Int.Assmt Item Fee |
| FEE | FVIASSMNTITMINT | Visa Int.Assmt Per Item Fee |
| FEE | FMSTRINTASSMNT | Maestro Int. Assmt Fee |
| FEE | FMSTRINTASSMNTITM | Maestro Int.Assmt Item Fee |
| FEE | FDNRASSMNTINT | Diners Int. Assessment Fee |
| FEE | FDNRASSMNTINTITM | Diners Int. Assmt Per Item Fee |
| FEE | FVINONSECRCHGBK | Non Secure Visa Chargeback Fee |
| FEE | FPCIDSSMGMTNET | Pci Dss Management Net Fee |
| FEE | FLCLXBRDR2LAC | Lac Cross Border Fee 2, Local |
| FEE | FVIISAAP | Visa Isa Fee Ap |
| FEE | FVNDGLANACTVN | Vending Lan Activation Fee |
| FEE | FVNDGLANNONMOBLMNTH | Vend Lan Non Mobil Mnth Fee |
| FEE | FVNDGLANDNLD | Vending Lan Download Fee |
| FEE | FWRLSDATAPLAN30MG | Wireless Data Plan 30Mg Fee |
| FEE | FVOYSLSTXN | Voyager Sales Transaction Fee |
| FEE | FVOYRETTXN | Voyager Credit Transaction Fee |
| FEE | FVOYCHGBKTXN | Voyager Chgbk Transaction Fee |
| FEE | FVOYRTVL | Voyager Retrieval Fee |
| FEE | FUSXBRDR | Us Cross Border Fee |
| FEE | FUSXBRDRNONUSD | Us Cross Border Fee, Nonusd |
| FEE | FAPXBRDR | Ap Cross Border Fee |
| FEE | FLACXBRDR2 | Lac Cross Border Fee 2 |
| FEE | FMCCOBRNDSLSTXN | Mc Cobrand Sales Trans Fee |
| FEE | FMCCATSLSTXN | Mc Cat Sales Trans Fee |
| FEE | FMCCATRETTXN | Mc Cat Returns Trans Fee |
| FEE | FMCCOBRNDRETTXN | Mc Cobrand Return Trans Fee |
| FEE | FMCMQSLSTXN | Mc Mid Qual Sales Trans Fee |
| FEE | FMCMQCRDTTXN | Mc Mid Qual Credits Trans Fee |
| FEE | FMCMQCHGBKTXN | Mc Mid Qual Chrgebck Trans Fee |
| FEE | FMCMQRVSLTXN | Mc Mid Qual Reversals Trns Fee |
| FEE | FVIMQSLSTXN | Visa Mid Qual Sales Trans Fee |
| FEE | FVIMQSRETTXN | Visa Mid Qual Credits Trns Fee |
| FEE | FVIMQSCHGBKTXN | Visa Mid Qual Chrgbck Trns Fee |
| FEE | FVIMQSRVSLTXN | Visa Mid Qual Reversal Trn Fee |
| FEE | FMCPRCSNGIC | Mc Proc Lvl Interchange Fee |
| FEE | FAMXMQCHGBKTXN | Amex Mid Qual Chrgbck Trns Fee |
| FEE | FAMXMQRVSLTXN | Amex Mid Qual Reversal Trn Fee |
| FEE | FMCNQCRDTTXN | Mc Non Qual Credits Trans Fee |
| FEE | FMCNQCHGBKTXN | Mc Non Qual Chrgebck Trans Fee |
| FEE | FMCNQRVSLTXN | Mc Non Qual Reversals Trns Fee |
| FEE | FVINQSRETTXN | Visa Non Qual Credits Trns Fee |
| FEE | FVINQSCHGBKTXN | Visa Non Qual Chrgbck Trns Fee |
| FEE | FVINQSRVSLTXN | Visa Non Qual Reversal Trn Fee |
| FEE | FSIGDBTMQRVSLTXN | Sig Debit Mid Qual Rev Tran |
| FEE | FVICATSLSTXN | Vi Cat Sales Trans Fee |
| FEE | FVICATRETTXN | Vi Cat Returns Trans Fee |
| FEE | FSIGDBTNQRVSLTXN | Sig Debit Non Qual Rev Trans |
| FEE | FMCWRLDSLSTXN | Mc World Sales Trans Fee |
| FEE | FMCWRLDRETTXN | Mc World Return Trans Fee |
| FEE | FMCWRLDCHGBKTXN | Mc World Chrgbk Trans Fee |
| FEE | FMCWRLDRVSLTXN | Mc World Reversal Trans Fee |
| FEE | FVIRWRDSLSTXN | Vi Reward Sales Trans Fee |
| FEE | FVIRWRDRETTXN | Vi Reward Return Trans Fee |
| FEE | FVIRWRDCHGBKTXN | Vi Reward Chrgbk Trans Fee |
| FEE | FVIRWRDRVSLTXN | Vi Reward Reversal Trans Fee |
| FEE | FDSCVCHGBKTXN | Discover Chargeback Trans |
| FEE | FDSCVRVSLTXN | Discover Reversal Trans |
| FEE | FSTRCLRNGTXNCAP | Star Clearing Trans Fee Cap |
| FEE | FMCWRLDMQTXN | Mc World Mid Qual Trans Fee |
| FEE | FMCWRLDMQRETTXN | Mc World Mid Qual Rtrn Trans |
| FEE | FMCWRLDMQCHGBKTXN | Mc World Mid Qual Chrgbk Trans |
| FEE | FMCWRLDMQRVSLTXN | Mc World Mid Qual Rev Trans |
| FEE | FVIRWRDMQTXN | Vi Reward Mid Qual Trans Fee |
| FEE | FVIRWRDMQRETTXN | Vi Reward Mid Qual Rtrn Trans |
| FEE | FVIRWRDMQCHGBKTXN | Vi Reward Midqual Chrgbk Trans |
| FEE | FVIRWRDMQRVSLTXN | Vi Reward Mid Qual Rev Trans |
| FEE | FMCDBTSVCCHRG | Mc Debit Service Charge |
| FEE | FMCDBTRFND | Mc Debit Refunds |
| FEE | FMCDBTSLSTXNF65C | Mc Debit Sales Transaction Fee |
| FEE | FMCDBTRFNDTXN | Mc Debit Refund Transaction |
| FEE | FMCDBTNQSVCCHRG | Mc Debit Nq Service Charge |
| FEE | FMCDBTNQRFND | Mc Debit Nq Refunds |
| FEE | FMCDBTNQSLSTXN | Mc Debit Nq Sales Trans Fee |
| FEE | FMCDBTNQRFNDTXN | Mc Debit Nq Refund Transaction |
| FEE | FMCDBTCHIPSVCCHRG | Mc Debit Chip Service Charge |
| FEE | FMCDBTCHIPRFND | Mc Debit Chip Refunds |
| FEE | FMCDBTCHIPSLSTXN | Mc Debit Chip Sales Trans Fee |
| FEE | FMCDBTCHPRFNDTXN | Mc Debit Chip Refund Trans Fee |
| FEE | FMCDBTCHIPNQSVCCHRG | Mc Debit Chip Nq Service Chrg |
| FEE | FMCDBTCHIPNQRFND | Mc Debit Chip Nq Refunds |
| FEE | FMCDBTCHIPNQSLSTXN | Mc Dbt Chp Nq Sales Trans |
| FEE | FMCDBTCHIPNQRFNDTXN | Mc Debit Chip Nq Refund Trans |
| FEE | FAMXNQCHGBKTXN | Amex Non Qual Chrgbck Tran Fee |
| FEE | FMCWRLDNQTXN | Mc World Non Qual Trans Fee |
| FEE | FMCWRLDNQRETTXN | Mc World Non Qual Rtrn Trans |
| FEE | FMCWRLDNQCHGBKTXN | Mc World Non Qual Chrgbk Trans |
| FEE | FMCWRLDNQRVSLTXN | Mc World Non Qual Rev Trans |
| FEE | FVIRWRDNQTXN | Vi Reward Non Qual Trans Fee |
| FEE | FVIRWRDNQRETTXN | Vi Reward Non Qual Rtrn Tran |
| FEE | FVIRWRDNQCHGBKTXN | Vi Reward Nonqual Chrgbk Trans |
| FEE | FVIRWRDNQRVSLTXN | Vi Reward Non Qual Rev Trans |
| FEE | FMNTHLYADVNTGAMDS | Monthly Advantage Fee Amds |
| FEE | FMCWRLDSLSDSCNT | Mc World Sales Discount |
| FEE | FMCWRLDRETDSCNT | Mc World Return Discount |
| FEE | FVIRWRDSLSDSCNT | Vi Reward Sales Discount |
| FEE | FVIRWRDRETDSCNT | Vi Reward Return Discount |
| FEE | FVIRWRDRVSLDSCNT | Vi Reward Reversal Discount |
| FEE | FMCWRLDMQSLSDSCNT | Mc World Mid Qual Sales Disc |
| FEE | FMCWRLDMQRETDSCNT | Mc World Mid Qual Return Disc |
| FEE | FVIRWRDMQSLSDSCNT | Vi Reward Mid Qual Sales Disc |
| FEE | FVIRWRDMQRETDSCNT | Vi Reward Mid Qual Return Disc |
| FEE | FTXNKBYTE | Transaction Kilobyte Fee |
| FEE | FBSNSQPERITM | Business Qual Per Item |
| FEE | FBSNSMQPERITM | Business Mid Qual Per Item |
| FEE | FBSNSNQPERITM | Business Non Qual Per Item |
| FEE | FMCWRLDNQSLSDSCNT | Mc World Non Qual Sales Disc |
| FEE | FMCWRLDNQRETDSCNT | Mc World Non Qual Return Disc |
| FEE | FMCWRLDNQRVSLDSCNT | Mc World Non Qual Rev Disc |
| FEE | FVIRWRDNQSLSDSCNT | Vi Reward Non Qual Sales Disc |
| FEE | FVIRWRDNQRETDSCNT | Vi Reward Non Qual Return Disc |
| FEE | FMSTRDBTCARD | Maestro Debit Card Fee |
| FEE | FINTRLNKDBTCARD | Interlink Debit Card Fee |
| FEE | FEXPLRDBTCARD | Explore Debit Card Fee |
| FEE | FHNRDBTCARD | Honor Debit Card Fee |
| FEE | FIRTVLSMSFISVGTWY | Incoming Rtvl Sms Fisv Gtwy |
| FEE | FICHGBKMSFISVGTWY | Incoming Cb Sms Fisv Gtwy |
| FEE | FIMRCHRESPSMSFISVGTWY | In Merch Resp Sms Fisv Gtwy |
| FEE | FIOEXCPTNSMSFISVGTWY | In/Out Except Sms Fisv Gtwy |
| FEE | FNWINCCBFISVGTWSMS | Nw Inc Cb Fisv Gtwy Sms |
| FEE | FNWCBRPFISVGTWSMS | Nw Cb Repres Fisv Gtwy Sms |
| FEE | FDSCVPRMNQRVSLDSCNT | Ds Prem Nonqual Revrsal Discnt |
| FEE | F70DCTRMNLBILLING | 70Dc Terminal Billing Fee |
| FEE | FALERT | Alert Fee |
| FEE | FALERTBNDL | Alert Bundled Fee |
| FEE | FVIXBRDREEA | Vi Eea Crossborder Fee |
| FEE | FVIXBRDREEAITM | Vi Eea Crossborder Fee Item |
| FEE | FVIXBRDREEACNP | Vi Eea Crossborder Fee Cnp |
| FEE | FVIEEAXBRDRCNPITM | Vi Eea Crossborder Fee Cnp Itm |
| FEE | FVIXBRDRITMINT | Vi Int Crossborder Fee Item |
| FEE | FVIXBRDRCNPINT | Vi Int Crossborder Fee Cnp |
| FEE | FVIXBRDRCNPITMINT | Vi Int Crossborder Fee Cnp Itm |
| FEE | FVISTNDRDIC | Visa Standard Interchange Fee |
| FEE | FVIICRATEEIRF | Visa Eirf Interchange Fee |
| FEE | FDSCVMQSLSTXN | Discover Midqual Sale Trans |
| FEE | FDSCVMQRETTXN | Discover Midqual Rtn Trans |
| FEE | FDSCVMQCHGBKTXN | Discover Midqual Cb Trans |
| FEE | FDSCVMQRVSLTXN | Discover Midqual Rev Trans |
| FEE | FDSCVNQSLSTXN | Discover Nonqual Sale Trans |
| FEE | FDSCVNQRETTXN | Discover Nonqual Rtn Trans |
| FEE | FDSCVNQCHGBKTXN | Discover Nonqual Cb Trans |
| FEE | FDSCVNQRVSLTXN | Discover Nonqual Rev Trans |
| FEE | FVISTNDRDICRATE | Visa Standard Interchange Rate |
| FEE | FVINQCNP | Visa Non Qual Cnp |
| FEE | FDSCVNQCNP | Discover Non Qual Cnp |
| FEE | FICCLRNG | Interchange Clearing Fee |
| FEE | FMCELECBCARD | Mastercard Elec. Bcard Rate |
| FEE | FMCNQCNP | Mastercard Non Qual Cnp |
| FEE | FWCPRETDSCNT | Wcp Return Discount Fee |
| FEE | FDNRSLSDSCNT | Diners Sales Discount |
| FEE | FDNRRETDSCNT | Diners Return Discount |
| FEE | FDNRCHGBKDSCNT | Diners Chargeback Discount |
| FEE | FDNRRVSLDSCNT | Diners Reversal Discount |
| FEE | FJCBSLSDSCNT | Jcb Sales Discount |
| FEE | FJSBRETDSCNT | Jcb Return Discount |
| FEE | FJCBCHGBKDSCNT | Jcb Chargeback Discount |
| FEE | FJCBRVSLDSCNT | Jcb Reversal Discount |
| FEE | FPVTLVLSLSDSCNT | Private Label Sales Discount |
| FEE | FPVTLVLRETDSCNT | Private Label Returns Discount |
| FEE | FGENPICHGBKDSCNT | Gen Pl Chg Back Disc |
| FEE | FGENPIRVSLDSCNT | Gen Pl Reversal Disc |
| FEE | FVOYCHGBKDSCNT | Voyager Chgbk Discount Fee |
| FEE | FVISVCCHRG | Visa Service Charge |
| FEE | FVIRFND | Visa Refunds |
| FEE | FVIDBTSVCCHRG | Visa Debit Service Charge |
| FEE | FVIDBTRFND | Visa Debit Refunds |
| FEE | FVIELCTRNDRSVCCHRG | Visa Electron Dr Serv Charge |
| FEE | FVIELCTRNDRRFND | Visa Electron Dr Refunds |
| FEE | FMSTRSRVCCHRG | Maestro Service Charge |
| FEE | FMSTRRFND | Maestro Refunds |
| FEE | FSOLOSVCCHRG | Solo Service Charge |
| FEE | FSOLORFND | Solo Refunds |
| FEE | FVICHIPSVCCHRG | Visa Chip Service Charge |
| FEE | FVICHIPRFND | Visa Chip Refunds |
| FEE | FVIDBTCHIPSVCCHRG | Visa Debit Chip Service Charge |
| FEE | FVIDBTCHIPRFND | Visa Debit Chip Refunds |
| FEE | FVPAYQSLSSVCCHRG | Vpay Qual Sales Service Chg |
| FEE | FVPAYQRFNDSVCCHRG | Vpay Qual Rfnd Service Chg |
| FEE | FMSTRSVCCHRGINT | Intl Mstro Service Charge |
| FEE | FMSTRRFNDINT | Intl Mstro Refunds |
| FEE | FVIPCARDSVCCHRG | Visa Purchase Card Serv Chrg |
| FEE | FVIPCARDRFND | Visa Purchase Card Refunds |
| FEE | FMCPVTLBLSLSTXN | Mc Private Lbl Sales Tran Fee |
| FEE | FMCPVTLBLRETTXN | Mc Pvt Lbl Returns Tran Fee |
| FEE | FMCPVTLBLCHGBKTXN | Mc Pvt Lbl Chrgbck Tran Fee |
| FEE | FMCPVTLBLRVSLTXN | Mc Pvt Lbl Reversal Tran Fee |
| FEE | FDSCVDBTCHGBKTXN | Discover Debit Cb Trans |
| FEE | FDSCVDBTRVSLTXN | Discover Debit Rev Trans |
| FEE | FDSCVDBTMQSLSTXN | Discover Dbt Midqual Sale Tran |
| FEE | FDSCVDBTMQRETTXN | Discover Dbt Midqual Rtn Trans |
| FEE | FDSCVDBTMQCHGBKTXN | Discover Dbt Midqual Cb Trans |
| FEE | FDSCVDBTMQRVSLTXN | Discover Dbt Midqual Rev Trans |
| FEE | FDSCVDBTNQSLSTXN | Discover Dbt Nonqual Sale Tran |
| FEE | FDSCVDBTNQRETTXN | Discover Dbt Nonqual Rtn Trans |
| FEE | FDSCVDBTNQCHGBKTXN | Discover Dbt Nonqual Cb Trans |
| FEE | FDSCVDBTNQRVSLTXN | Discover Dbt Nonqual Rev Trans |
| FEE | FEUAMRCNEDC | European American Edc |
| FEE | FEUAMRCNMOTO | European American Moto |
| FEE | FEUAMERPAPERVOICECPTR | European Amer Paper Voice Capt |
| FEE | FB2CSWIPEDVRBLGRID | B2C Swipe Variable Grid |
| FEE | FB2CNONSWIPEDVRBLGRID | B2C Nonswipe Variable Grid |
| FEE | FB2BSWIPEDVRBLGRID | B2B Swipe Variable Grid |
| FEE | FB2BNONSWIPEDVRBLGRID | B2B Nonswipe Variable Grid |
| FEE | FMCCHGBKDSCNT | Mastercard Chargeback Discount |
| FEE | FMCRVSLDSCNT | Mastercard Reversal Discount |
| FEE | FVICHGBKDSCNT | Visa Chargeback Discount |
| FEE | FVIRVSLDSCNT | Visa Reversal Discount |
| FEE | FDNRMCSLSDSCNT | Diners (Mc)Sales Discount |
| FEE | FAMXMQCHGBKDSCNT | Amex Mid Qual Chargeback Disc |
| FEE | FAMXMQRVSLDSCNT | Amex Mid Qual Reversl Discount |
| FEE | FDSCVKBYTE | Discount Kilobyte Fee |
| FEE | FBSNSQDSCNT | Business Qual Discount |
| FEE | FBSNSMQDSCNT | Business Mid Qual Discount |
| FEE | FBSNSNQDSCNT | Business Non Qual Discount |
| FEE | FMCMQSLSDSCNT | Mastercard Mid Qual Sales Disc |
| FEE | FMCMQRETDSCNT | Mastercard Mid Qual Retn Disc |
| FEE | FMCMQCHGBK | Mastercard Mid Qual Chrgebck |
| FEE | FMCMQRVSLDSCNT | Mastercard Mid Qual Revrsl Dis |
| FEE | FVIMQSLSDSCNT | Visa Mid Qual Sales Discount |
| FEE | FVIMQRETDSCNT | Visa Mid Qual Returns Discount |
| FEE | FVIMQCHGBKDSCNT | Visa Mid Qual Chrgeback Disc |
| FEE | FVIMQRVSLDSCNT | Visa Mid Qual Reversal Disc |
| FEE | FMCLCNSEVOL | Mc License Volume Fee |
| FEE | FAMXNQCHGBKDSCNT | Amex Non Qual Chargeback Disc |
| FEE | FAMXNQRVSLDSCNT | Amex Non Qual Reversal Discnt |
| FEE | FMCNQSLSDSCNT | Mastercard Non Qual Sales Disc |
| FEE | FMCNQRETDSCNT | Mastercard Non Qual Retn Disc |
| FEE | FMCNQCHGBK | Mastercard Non Qual Chrgebck |
| FEE | FMCNQRVSLDSCNT | Mastercard Non Qual Revrsl Dis |
| FEE | FVINQSLSDSCNT | Visa Non Qual Sales Discount |
| FEE | FVINQRETDSCNT | Visa Non Qual Returns Discount |
| FEE | FVINQCHGBKDSCNT | Visa Non Qual Chrgeback Disc |
| FEE | FVINQRVSLDSCNT | Visa Non Qual Reversal Disc |
| FEE | FSIGDBTRETDSCNTF83B | Sig Debit Returns Discount |
| FEE | FSIGDBTCHGBKDSCNT | Sig Debit Chargeback Discount |
| FEE | FSIGDBTRVSLDSCNT | Sig Debit Reversal Discount |
| FEE | FSIGDBTMQRETDSCNT | Sig Debit Mid Qual Return Disc |
| FEE | FSIGDBTMQRVSLDSCNT | Sig Debit Mid Qual Rev Disc |
| FEE | FSIGDBTNQRETDSCNT | Sig Debit Non Qual Return Disc |
| FEE | FSIGDBTNQRVSLDSCNT | Sig Debit Non Qual Rev Disc |
| FEE | FRAPIDDPST | Rapid Deposit Fee |
| FEE | FVIVOLMTIERA | Visa Volume Tier Fee (A) |
| FEE | FDBTRETDSCNTF831 | Debit Returns Discount |
| FEE | FVICHKCARDSLSDSCNT | Visa Check Card Sales Disc |
| FEE | FVICHKCARDRETDSCNT | Visa Check Card Returns Disc |
| FEE | FWEXPLSLSDSCNT | Wright Express (P/L) Sales Dsc |
| FEE | FWEXPLRETDSCNT | Wright Express (P/L) Returns D |
| FEE | FWEXCHGBKDSCNT | Wex Chargeback Discount |
| FEE | FWEXCHGBKRVSLDSCNT | Wex Chrgbk Reversal Discount |
| FEE | FMCPYMNTDSCNT | Mc Payment Discount Rate |
| FEE | FMCFNDNGDSCNT | Mc Funding Discount Rate |
| FEE | FMCDBTCHGBKDSCNT | Mastercard Debit Chrgbck Disc |
| FEE | FMCDBTRVSLDSCNT | Mastercard Debit Reversal Disc |
| FEE | FVIDBTCHGBKDSCNT | Visa Debit Chrgbck Discount |
| FEE | FVIDBTRVSLDSCNT | Visa Debit Reversal Discount |
| FEE | FMCCATSLSDSCNT | Mc Cat Sales Discnt |
| FEE | FVICATSLSDSCNT | Vi Cat Sales Discnt |
| FEE | FVIDBTNQSLSDSCNT | Vi Debit Non Qual Sales Disc |
| FEE | FVIDBTNQRETDSCNT | Vi Debit Non Qual Return Disc |
| FEE | FVIDBTNQCHGBKDSCNT | Vi Debit Non Qual Chrgbk Disc |
| FEE | FVIDBTNQRVSLDSCNT | Vi Debit Non Qual Rev Disc |
| FEE | FMCDBTMQSLSDSCNT | Mc Debit Mid Qual Sales Disc |
| FEE | FMCDBTMQRETDSCNT | Mc Debit Mid Qual Returns Disc |
| FEE | FMCDBTMQCHGBKDSCNT | Mc Debit Mid Qual Chrgbck Disc |
| FEE | FMCDBTMQRVSLDSCNT | Mc Debit Mid Qual Rev Disc |
| FEE | FVIDBTMQSLSDSCNT | Vi Debit Mid Qual Sales Disc |
| FEE | FVIDBTMQRETDSCNT | Vi Debit Mid Qual Return Disc |
| FEE | FVIDBTMQCHGBKDSCNT | Vi Debit Mid Qual Chrgbk Disc |
| FEE | FVIDBTMQRVSLDSCNT | Vi Debit Mid Qual Rev Disc |
| FEE | FTOUCHTONE1001CNV | Touchtone 10/01 Conv |
| FEE | FMCDBTNQSLSDSCNT | Mc Debit Non Qual Sales Disc |
| FEE | FMCDBTNQRETDSCNT | Mc Debit Non Qual Returns Disc |
| FEE | FMCDBTNQCHGBKDSCNT | Mc Debit Non Qual Chrgbck Disc |
| FEE | FMCDBTNQRVSLDSCNT | Mc Debit Non Qual Rev Disc |
| FEE | FWACHOVIAGRID006 | Wachovia Grid 006 |
| FEE | FMCGLBLEPRCNGSVC | Mc Global Epricing Service Fee |
| FEE | FVIGLBLEPRCNGSVC | Vi Global Epricing Service Fee |
| FEE | FSNTRUST09160493 | Suntrust 0916/0493 |
| FEE | FSNTRUST09160594 | Suntrust 0916/0594 |
| FEE | FSNTRUST09520018 | Suntrust 0952/0018 |
| FEE | FPPRTRMNL | Paper/Terminal |
| FEE | FPROVIGO | Provigo |
| FEE | FPAPER | Paper |
| FEE | FWELSSPAPERGRID | Wells Paper Grid |
| FEE | FSRVCSTRNONCORPDEPST | Servistar Non/Corp Deposits |
| FEE | FBOHGRID | Bank Of Hawaii Grid |
| FEE | FBOHPAPER | Boh Paper |
| FEE | FBOHEDC | Boh Edc |
| FEE | FWESTAMRCBANKPAPR | Westamerica Bank Paper |
| FEE | FWESTAMRCBANKEDC | Westamerica Bank Edc |
| FEE | FNAPAVLLCEDC | Napa Valley/Lc Edc |
| FEE | FWFBMOTO | Wfb Moto |
| FEE | FBOHGRIDF942 | Bank Of Hawaii Grid |
| FEE | FHUNTNGTNGRID2PAPR | Huntington Grid #2 Paper |
| FEE | FMINMCVIDSCV | Mc/Vi/Disc Minimum Fee |
| FEE | FEBTONLNMNTH | Ebt Online Monthly Min |
| FEE | FACCTMINF950 | Account Minimum Fee |
| FEE | FACCTMINF952 | Account Minimum Fee |
| FEE | FACCTMINF953 | Account Minimum Fee |
| FEE | FACCTMINF954 | Account Minimum Fee |
| FEE | FACCTMINF955 | Account Minimum Fee |
| FEE | FACCTMINF956 | Account Minimum Fee |
| FEE | FMNTHLYMIN | Monthly Minimum Fee |
| FEE | FTAMINMNTH | Transarmor Monthly Min Fee |
| FEE | FDBTMIN | Debit Minimum Fee |
| FEE | FMINMCVI | Mc/Visa Minimum |
| FEE | FFEERBT | Fee Rebate |
| FEE | FDSCVDBTCHGBKDSCNT | Discover Debit Cb Discount |
| FEE | FDSCVDBTRVSLDSCNT | Discover Debit Rev Discount |
| FEE | FDSCVDBTMQSLSDSCNT | Discover Dbt Midqual Sale Disc |
| FEE | FDSCVDBTMQRETDSCNT | Discover Dbt Midqual Rtn Disc |
| FEE | FDSCVDBTMQCHGBKDSCNT | Discover Dbt Midqual Cb Disc |
| FEE | FDSCVDBTMQRVSLDSCNT | Discover Dbt Midqual Rev Disc |
| FEE | FDSCVDBTNQSLSDSCNT | Discover Dbt Nonqual Sale Disc |
| FEE | FDSCVDBTNQRETDSCNT | Discover Dbt Nonqual Rtn Disc |
| FEE | FDSCVDBTNQCHGBKDSCNT | Discover Dbt Nonqual Cb Disc |
| FEE | FDSCVDBTNQRVSLDSCNT | Discover Dbt Nonqual Rev Disc |
| FEE | FDSCVMQSLSDSCNT | Discover Midqual Sales Disc |
| FEE | FDSCVMQRETDSCNT | Discover Midqual Rtn Disc |
| FEE | FDSCVMQCHGBKDSCNT | Discover Midqual Cb Discount |
| FEE | FDSCVMQRVSLDSCNT | Discover Midqual Rev Discount |
| FEE | FDSCVNQSLSDSCNT | Discover Nonqual Sales Disc |
| FEE | FDSCVNQRETDSCNT | Discover Nonqual Rtn Discount |
| FEE | FDSCVNQCHGBKDSCNT | Discover Nonqual Cb Discount |
| FEE | FDSCVNQRVSLDSCNT | Discover Nonqual Rev Discount |
| FEE | FDIRECTDBFRANCEREF | Directdb France Ref |
| FEE | FRTBTGRMNYREF | Rtbt Germany Ref |
| FEE | FRTBTNTHLNDSREF | Rtbt Netherlands Val |
| FEE | FMCAVS | Mastercard Avs Fee |
| FEE | FVIDBTCHIPBTCHAUTH | Visa Debit Chip Batch Auth Fee |
| FEE | FVICHIPVOICEAUTH | Visa Chip Voice Auth Fee |
| FEE | FPOLLING | Polling Fee |
| FEE | FSTMTINSERT | Statement Insert Fee |
| FEE | FSTMTMSG | Statement Message Fee |
| FEE | FEXPRSFNDING | Express Funding Fee |
| FEE | FVICRDT | Visa Credit |
| FEE | FVIDBT | Visa Debit |
| FEE | FVIPRCHS | Visa Purchasing |
| FEE | FVIDBTCHIP | Visa Debit Chip |
| FEE | FVICRDCHIP | Visa Credit Chip |
| FEE | FMCCRDTCHIP | Mc Credit Chip |
| FEE | FMCPCARD | Mastercard Purchasing Card |
| FEE | FMSTRBLBKINT | Intl Mstro Billback Fee |
| FEE | FMSTRSLSICF518 | Maestro Sales Ic Fee |
| FEE | FVPAYCHIPSLSIC | Vpay Chip Sales Ic Fee |
| FEE | FMSTRIC | Maestro Interchange Fee |
| FEE | FVPAYCHIPIC | Vpay Chip Interchange Fee |
| FEE | FSOLOIC | Solo Interchange Fee |
| FEE | FMSTROICINT | Intl Mstro Interchange Fee |
| FEE | FSOLOSLSIC | Solo Sales Ic Fee |
| FEE | FMSTRSLSICINT | Intl Mstro Sales Ic Fee |
| FEE | FVISLSIC | Visa Sales Ic Fee |
| FEE | FVIELCTRNSLSIC | Visa Electron Sales Ic Fee |
| FEE | FVICHIPSLSIC | Visa Chip Sales Ic Fee |
| FEE | FVIPCARDSLSIC | Visa Purch Card Sales Ic Fee |
| FEE | FVIDBTSLSIC | Visa Debit Sales Ic Fee |
| FEE | FVIDBTCHIPSLSIC | Visa Debit Chip Sales Ic Fee |
| FEE | FVIELCTRNIC | Visa Electron Interchange Fee |
| FEE | FVICHIPIC | Visa Chip Interchange Fee |
| FEE | FVIPCARDIC | Visa Purch Card Intrchg Fee |
| FEE | FVIDBTICH | Visa Debit Interchange Fee |
| FEE | FVIDBTCHIPIC | Visa Debit Chip Interchg Fee |
| FEE | FMCSLSIC | Mastercard Sales Ic Fee |
| FEE | FMCCHIPIC | Mc Chip Interchange Fee |
| FEE | FMCPCARDIC | Mc Purch Card Interchange Fee |
| FEE | FMCCHIPSLSIC | Mc Chip Sales Ic Fee |
| FEE | FMCPCARDSLSIC | Mc Purch Card Sales Ic Fee |
| FEE | FVIPCARDNQSLSTXNCNTLSXBRDR | Vi Pur Nq Sl Tx C/Les(Ex B Dr) |
| FEE | FVIPCARDNQRFNDTXNCNTLSXBRDR | Vi Pur Nq Ref Tx C/Ls(Ex B Dr) |
| FEE | FVIPRCARDNQRFNDCNTLSXBRDR | Vi Prch Nq Ref C/Less(Ex B Dr) |
| FEE | FVIPCARDNQSVCCHRGXBRDR | Visa Prch Nq Srvchg(Ex Bus Dr) |
| FEE | FVIPCARDNQRFNDXBRDR | Visa Prch Nq Ref (Ex Bus Dr) |
| FEE | FDNRRFNDSVCCHRG | Diners Refund Service Charge |
| FEE | FDNRSLSSVCCHRG | Diners Sales Service Charge |
| FEE | FDNRRETTXN | Diners Return Trans Fee |
| FEE | FVINQSLSTXNEXPRM | Visa Nqsalestrans Fee Ex.Prem |
| FEE | FVICHIPNQSLSTXNEXPRM | Visa Chip Nqsales T/F Ex.Prem |
| FEE | FVIBSNSDRCARDSVCCHRGCNTLS | Vi Bus Dr Cd Srv Chg C/Less |
| FEE | FVIBSNSDRCARDRFNDCNTLS | Vi Bus Dr Crd Rfnd Cnt Less |
| FEE | FVIBSNSDRCARDNQSVCCHRGCNTLS | Vi Bus Dr Cd Nq Srv Chg C/Less |
| FEE | FVIBSNSDRCARDRFNDTXNCNTLS | Vi Bus Dr Cd Refund Trn C/Less |
| FEE | FVIBSNSDRCARDNQSLSTXN | Visa Bus Dr Card Nq Sale T/Fee |
| FEE | FVIBSNSDRCARDNQRFNDTXN | Visa Bus Dr Card Nq Rfnd T/Fee |
| FEE | FVIPCARDSVCCHRGCNTLSXBRDR | Vi Pur Srv Chg C/Less(Ex B Dr) |
| FEE | FVIPCARDRFNDCNTLSXBRDR | Vi Purch Ref C/Less(Ex Bus Dr) |
| FEE | FVIPCARDNQSVCCHRGCNTLSXBRDR | Vi Pur Nq S/Chg C/Les(Ex B Dr) |
| FEE | FVIPCARDRFNDTXNCNTLSXBRDR | Vi Pur Refund Tx C/Ls(Ex B Dr) |
| FEE | FVIPCARDNQSLSTXNXBRDR | Visa Prch Nq Sls Tx(Ex Bus Dr) |
| FEE | FVIPCARDNQRFNDTXNXBRDR | Visa Prch Nq Ref Tx(Ex Bus Dr) |
| FEE | FVIBSNSDRCARDNQSLSTXNCNTLS | Vi Bus Dr Cd Nq Sls Trn C/Less |
| FEE | FVIBSNSDRCARDNQRFNDTXNCNTLS | Vi Bus Dr Cd Nq Rfd Trn C/Less |
| FEE | FVIBSNSDRCARDSLSTXNCNTLS | Vi Bus Dr Cd Sales Trn C/Less |
| FEE | FVIBSNSDRCARDNQRFNDCNTLS | Vi Bus Dr Crd Nq Rfnd C/Less |
| FEE | FVIBSNSDRCARDNQSVCCHRG | Visa Bus Dr Card Nq Srv Chg |
| FEE | FVIBSNSDRCARDNQRFND | Visa Bus Dr Card Nq Refunds |
| FEE | FMCNQSVCCHRGPREM | Mc Nq Service Charge (Prem) |
| FEE | FMCNQREFNDPREM | Mc Non Qual Refunds (Prem) |
| FEE | FMCCHIPNQSVCCHRGPREM | Mc Chip Nq Srv Chrg (Prem) |
| FEE | FMCCHIPNQRETPREM | Mc Chip Nq Refunds (Prem) |
| FEE | FMCNQSLSTXNPREM | Mc Nq Sales Trans Fee (Prem) |
| FEE | FMCCHIPNQSLSTXNPREM | Mc Chip Nq Sales T/Fee (Prem) |
| FEE | FVIPCARDSLSTXNCNTLS | Vi Pur Sales Tx C/Les(Ex B Dr) |
| FEE | FINTRNTADDTNLTXNCHRG | Internet Additional Trans Chgs |
| FEE | FTRMNLRNTL | Terminal Rental Fee |
| FEE | FVINQSLSTXNPREM | Visa Nq Sales Trans Fee(Prem) |
| FEE | FVINQRFNDTXNPREM | Visa Nqrefundt/Fee (Prem) |
| FEE | FVICHIPNQSLSTXNPREM | Visachip Nq Sales T/Fee(Prem) |
| FEE | FVINQSVCCHRGPREM | Visa Nqservice Chg (Prem) |
| FEE | FVINQRFNDPREM | Visa Non.Qualrefunds(Prem) |
| FEE | FVICHIPNQSVCCHRGPREM | Visa Chip Nq Service Chg(Prem) |
| FEE | FVICHIPNQRFNDPREM | Visachip Nqrefunds(Prem) |
| FEE | FVINQSVCCHRGEXPREM | Visa Non Qual Srv Chg Ex.Prem |
| FEE | FVINQRFNDEXPREM | Visa Non Qual Refunds Ex.Prem |
| FEE | FVICHIPNQSVCCHRGEXPREM | Visa Chip Nq Srv Chg Ex.Prem |
| FEE | FVICHIPNQRFNDEXPREM | Visa Chip Nq Refund Ex.Prem |
| FEE | FMCNQSVCCHRGEXPREM | Mc Nq Service Charge Ex. Prem |
| FEE | FMCNQREFNDEXPREM | Mc Non Qual Refunds Ex. Prem |
| FEE | FMCCHIPNQSVCCHRGEXPREM | Mc Chip Nq Srv Chrg Ex. Prem |
| FEE | FMCCHIPNQSVCREFNDEXPREM | Mc Chip Nq Refunds Ex. Prem |
| FEE | FMCNQSLSTXNEXPREM | Mc Nq Sales Trans Fee Ex.Prem |
| FEE | FMCCHIPNQSLSTXNEXPREM | Mc Chip Nq Sale T/Fee Ex.Prem |
| FEE | FVICOMMSVCCHRGCNTLSXBDR | Vi Comm S/Chg C/Les(Ex Bus Dr) |
| FEE | FVICOMMRFNDCNTLSXBDR | Vi Comm Rfnd C/Less(Ex Bus Dr) |
| FEE | FMSTRACCPTEU | M/C+Maestro Eu Acceptance Fee |
| FEE | FMCRETLACCPTNCINT | M/C Int. Retail Acceptance Fee |
| FEE | FMCCASHACCPTNCINT | M/C Int. Cash Acceptance Fee |
| FEE | FMSTRACCPTINT | Maestro Int. Acceptance Fee |
| FEE | FMCCHIPSRVCCHRGCNTLS | Mc Chip Srv Chrg Cnt Less |
| FEE | FMCCHIPREFNDCNTLS | Mc Chip Rfund Cnt Less |
| FEE | FMCCHIPNQSVCCHRGCNTLS | Mc Chip Nq Srv Chrg Cnt Less |
| FEE | FMCDBTCHIPSVCCHRGCNTLS | Mc Db Chip Srv Chrg Cnt Less |
| FEE | FMCDBTCHIPRFNDCNTLS | Mc Db Chip Rfnd Cnt Less |
| FEE | FMCDBTCHIPSNQSVCCCHRGCNTLS | Mc Db Chip Nq Srv Chg Cnt Less |
| FEE | FMCDBTCHIPNQRFNDCNTLS | Mc Db Chip Nq Rfnd Cnt Less |
| FEE | FMCPRCHCRDNQSVCCHRGCNTLS | Mc Prch Cd Nq Srv Chg Cnt Less |
| FEE | FMCCOMCARDSVCCHRGCNTLS | Mc Comm Crd Srv Chrg Cnt Less |
| FEE | FMCCOMCARDREFNDCNTLS | Mc Comm Crd Rfnd Cnt Less |
| FEE | FVPAYQRETSVCCHRGCNTLS | Vpay Qual Rfd Srv Chg Cnt Less |
| FEE | FVPAYNQSLSSVCCHRGCNTLS | Vpay Nq Sls Srv Chg Cnt Less |
| FEE | FVPAYNQRETSVCCHRGCNTLS | Vpay Nq Rfnd Srv Chg Cnt Less |
| FEE | FVICHIPSVCCHRGCNTLS | Vi Chip Srv Chrg Cnt Less |
| FEE | FVICHIPRFNDCNTLS | Vi Chip Rfnd Cnt Less |
| FEE | FVICHIPNQSVCCHRGCNTLS | Vi Chip Nq Srv Chrg Cnt Less |
| FEE | FVICHIPNQRFNDCNTLS | Vi Chip Nq Rfnd Cnt Less |
| FEE | FVIDBTCHIPSVCCHRGCNTLS | Vi Db Chip Srv Chrg Cnt Less |
| FEE | FVIDBTRFNDVCCHRGCNTLS | Vi Db Chip Rfnd Cnt Less |
| FEE | FVIDBTCHIPNQSVCCHRGCNTLS | Vi Db Chip Nq Srv Chg Cnt Less |
| FEE | FVIDBTCHIPNQRFNDCNTLS | Vi Db Chip Nq Rfnd Cnt Less |
| FEE | FVIPCARDSVCCHRGCNTLS | Vi Purch Crd Srv Chrg Cnt Less |
| FEE | FVIPCARDRFNDCNTLS | Vi Purch Crd Rfnd Cnt Less |
| FEE | FVIPCARDNQSVCCHRGCNTLS | Vi Prch Cd Nq Srv Chg Cnt Less |
| FEE | FVIPCARDNQRFNDCNTLS | Vi Purch Crd Nq Rfnd Cnt Less |
| FEE | FVICOMCARDSVCCHRGCNTLS | Vi Comm Crd Serv Chrg Cnt Less |
| FEE | FMCCOMCARDRFNDCNTLS | Vi Comm Crd Rfnd Cnt Less |
| FEE | FVIELCTRNDRSVCCHRGCNTLS | Vi Electrn Dr Srv Chg Cnt Less |
| FEE | FVIELCTRNDRRFNDCNTLS | Vi Electron Dr Rfnd Cnt Less |
| FEE | FVIELCTRNDRNQSVCCHRGCNTLS | Vi Elect Nq Dr Sv Chg Cnt Less |
| FEE | FVIELCTRNDRNQRFNDCNTLS | Vi Electron Nq Dr Rfd Cnt Less |
| FEE | FMCCHIPSLSTXNCNTLS | Mc Chip Sls Trn Cnt Less |
| FEE | FMCCHIPNQSLSTXNCNTLS | Mc Chip Nq Sls Trn Cnt Less |
| FEE | FMCDBTCHIPSLSTXNCNTLS | Mc Db Chip Sls Trn Cnt Less |
| FEE | FMCDBTCHIPSRFNDTXNCNTLS | Mc Db Chip Rfnd Trn Cnt Less |
| FEE | FMCDBTCHIPSNQSLSTXNCNTLS | Mc Db Chip Nq Sls Trn Cnt Less |
| FEE | FMCDBTCHIPNQRFNDCNTLSF63H | Mc Db Chip Nq Rfd Trn Cnt Less |
| FEE | FMCCOMCARDRFNDTXNCNTLS | Mc Comm Crd Rfnd Trn Cnt Less |
| FEE | FVPAYNQRETTXNCHRGCNTLS | Vpay Nq Rfnd Trn Chg Cnt Less |
| FEE | FVICHIPSLSTXNCNTLS | Vi Chip Sls Trn Cnt Less |
| FEE | FVICHIPNQSLSTXNCNTLS | Vi Chip Nq Sls Trn Cnt Less |
| FEE | FVIDRCHIPSLSTXNCNTLS | Vi Dr Chip Sls Trn Cnt Less |
| FEE | FVIDRCHIPRFNDCNTLS | Vi Dr Chip Rfnd Trn Cnt Less |
| FEE | FVIDRCHIPNQSLSTXNCNTLS | Vi Dr Chip Nq Sls Trn Cnt Less |
| FEE | FVIDRCHIPNQRFNDCNTLS | Vi Dr Chip Nq Rfd Trn Cnt Less |
| FEE | FVINQRFNDTXN | Visa Non Qual Refunds Tran Fee |
| FEE | FVIDBTNQSLSTXN | Visa Debit Nq Sales Trans Fee |
| FEE | FVIDBTNQRFNDTXN | Visa Debit Nq Refund Trans Fee |
| FEE | FVIELCTRNDRNQSLSTXN | Visa Elect Dr Nq Sale Tran Fee |
| FEE | FVIELCTRNDRNQRFNDTXN | Visa Elect Dr Nq Rfd Trans Fee |
| FEE | FSOLONQRETTXN | Solo Non Qual Refunds Trns Fee |
| FEE | FVICHIPNQSLSTXN | Visa Chip Nq Sales Trans Fee |
| FEE | FVICHIPNQRFNDTXN | Visa Chip Nq Refunds Trans Fee |
| FEE | FVIDRCHIPNQSLSTXN | Visa Dr Chip Nq Sales Tran Fee |
| FEE | FVIDRCHIPNQRFNDTXN | Visa Dr Chip Nq Rfnd Trans Fee |
| FEE | FVPAYNQSLSCHRG | Vpay Non Qual Sls Chg |
| FEE | FVPAYNQRETCHRG | Vpay Non Qual Rfnd Charge |
| FEE | FMSTRNQSLSTXNINT | Intl Mstro Nq Sls Trans Fee |
| FEE | FMSTRNQRETTXNINT | Intl Mstro Nq Rfnd Trans Fee |
| FEE | FVIPCARDNQSLSTXN | Visa Purch Card Nq Sale T/Fee |
| FEE | FVINQSVCCHRG | Visa Non Qual Service Charge |
| FEE | FVINQRFND | Visa Non Qual Refunds |
| FEE | FVINQDBTSVGCHRG | Visa Nq Debit Service Charge |
| FEE | FVINQDBTRFND | Visa Non Qual Debit Refunds |
| FEE | FVIELCTRNDRNQSVCCHRG | Visa Electron Nq Dr Serv Chg |
| FEE | FVIELCTRNDRNQRFND | Visa Electron Nq Dr Refunds |
| FEE | FMSTRNQSVCCHRG | Maestro Non Qual Service Charg |
| FEE | FVICHIPNQSVCCHRG | Visa Chip Nq Service Charge |
| FEE | FVICHIPNQRFND | Visa Chip Non Qual Refunds |
| FEE | FVIDBTCHIPNQSVCCHRG | Visa Debit Chip Nq Service Chg |
| FEE | FVIDBTCHIPNQSRFND | Visa Debit Chip Nq Refunds |
| FEE | FVPAYNQSLSSVCHRG | Vpay Non Qual Sls Srv Chg |
| FEE | FVPAYNQRETSVCHRG | Vpay Non Qual Rfnd Srv Chrg |
| FEE | FMSTRNQSVCCHRGINT | Intl Mstro Nq Service Charge |
| FEE | FMSTRNQRETINT | Intl Mstro Non Qual Refunds |
| FEE | FMCNQSVCCHRG | Mastercard Nq Service Charge |
| FEE | FMCNQRFNDTXN | Mastercard Non Qual Refunds |
| FEE | FMCCHIPNQSVCCHRG | Mastercard Chip Nq Srv Chrg |
| FEE | FMCCHIPNQRFND | Mastercard Chip Nq Refunds |
| FEE | FMCPCARDNQSVCCHRG | Mc Purchase Card Nq Srv Chrg |
| FEE | FMCNQRFNDTXNF68H | Mastercard Nq Rfnd Trans Fee |
| FEE | FMCCHIPNQSLSTXN | Mastercard Chip Nq Sales T/Fee |
| FEE | FMCCHIPNQRFNDTXN | Mastercard Chip Nq Rfnd T/Fee |
| FEE | FMCPCARDNQSLSTXN | Mc Purchase Card Nq Sale T/Fee |
| FEE | FMSTRNQSLSTXNCNTLSINT | Intl Mstro Nq Sls Trn Cnt Less |
| FEE | FMSTRNQRETTXNCNTLSINT | Intl Mstro Nq Rfnd Cnt Less |
| FEE | FMSTRNQSLSSVCCHRGCNTLSINT | Intl Mstro Nq Srv Chg Cnt Less |
| FEE | FMSTRNQRETSVCCHRGCNTLSINT | Intl Mstro Nq Rfd Trn Cnt Less |
| FEE | FVIPCARDSVCCHRGXBRDR | Visa Prch Srv Chg(Ex Bus Dr) |
| FEE | FVIPCARDRFNDXBRDR | Visa Prch Refund (Ex Bus Dr) |
| FEE | FVIBSNSDRCARDSVCCHRG | Visa Bus Dr Card Serv Chrg |
| FEE | FVIBSNSDRCARDRFND | Visa Bus Dr Card Refunds |
| FEE | FVISVCCHRGEXPREM | Visa Service Charge Ex.Prem |
| FEE | FVIRFNDEXPREM | Visa Refunds Ex.Prem |
| FEE | FVICHIPSVCCHRGEXPREM | Visa Chip Service Chg Ex.Prem |
| FEE | FVICHIPRFNDEXPREM | Visa Chip Refunds Ex.Prem |
| FEE | FVIBSNSDRCARDSLSTXN | Visa Bus Dr Card Sale T/Fee |
| FEE | FVIBSNSDRCARDRFNDTXN | Visa Bus Dr Card Rfnd T/Fee |
| FEE | FVIPCARDSLSTXNXBRDR | Visa Prch Sls T/Fee(Ex Bus Dr) |
| FEE | FVIPCARDRFNDTXNXBRDR | Visa Prch Ref T/Fee(Ex Bus Dr) |
| FEE | FMCSVCCHRGPREM | Mc Service Charge (Prem) |
| FEE | FMCREFNDPREM | Mc Refunds (Prem) |
| FEE | FMCCHIPSVCCHRGPREM | Mc Chip Service Charge (Prem) |
| FEE | FMCCHIPREFNDPREM | Mc Chip Refunds (Prem) |
| FEE | FMCSLSTXNPREM | Mc Sales Trans Fee (Prem) |
| FEE | FMCSCHIPSLSTXNPREM | Mc Chip Sale Trans Fee (Prem) |
| FEE | FVISVCCHRGPREM | Visa Service Charge(Prem) |
| FEE | FVIRFNDPREM | Visa Refunds(Prem) |
| FEE | FVICHIPSVCCHRGPREM | Visa Chip Service Charge(Prem) |
| FEE | FVICHIPRFNDPREM | Visa Chip Refunds(Prem) |
| FEE | FVISLSTXNPREM | Visa Sales Trans Fee(Prem) |
| FEE | FVICHIPSLSTXNPREM | Visa Chip Salestrans Fee(Prem) |
| FEE | FVICHIPRFNDTXNPREM | Visa Chip Refunds T/Fee(Prem) |
| FEE | FVISLSTXNEXPREM | Visa Sales Trans Fee Ex.Prem |
| FEE | FVICHIPSLSTXNEXPREM | Visa Chip Sales Trans Ex.Prem |
| FEE | FVICHIPRFNDTXNEXPREM | Visa Chip Refund T/Fee Ex.Prem |
| FEE | FMCSVCCHRGEXPREM | Mc Service Charge Ex. Prem |
| FEE | FMCREFNDEXPREM | Mc Refunds Ex. Prem |
| FEE | FMCCHIPSVCCHRGEXPREM | Mc Chip Service Chg Ex. Prem |
| FEE | FMCCHIPREFNDEXPREM | Mc Chip Refunds Ex. Prem |
| FEE | FMCSLSTXNEXPREM | Mc Sales Trans Fee Ex. Prem |
| FEE | FMCCHIPSLSTXNEXPREM | Mc Chip Sale Tran Fee Ex.Prem |
| FEE | FVICOMMRFRLTXNXBRDR | Visa Comm Ref T/Fee(Ex Bus Dr) |
| FEE | FVICOMMSVCCHRGXBRDR | Visa Comm Serv Chrg(Ex Bus Dr) |
| FEE | FVICOMMRFNDXBRDR | Visa Comm Refunds (Ex Bus Dr) |
| FEE | FVIACCPTNCINT | Visa Int Acceptance Fee |
| FEE | FMSTRSVCCHRGCNTLSINT | Intl Mstro Srv Chrg Cnt Less |
| FEE | FMSTRSLSTXNCNTLSINT | Intl Mstro Sls Trn Cnt Less |
| FEE | FMSTRRETCNTLSINT | Intl Mstro Rfnd Cnt Less |
| FEE | FMSTRRETTXNCNTLSINT | Intl Mstro Rfnd Trn Cnt Less |
| FEE | FVICOMMCARDSVCCHRG | Visa Commercial Card Serv Chrg |
| FEE | FVICOMMCARDRFND | Visa Commercial Card Refunds |
| FEE | FVIRFNDTXN | Visa Refunds Trans Fee |
| FEE | FVIDBTSLSTXN | Visa Debit Sales Trans Fee |
| FEE | FVIDBTRFNDTXN | Visa Debit Refunds Trans Fee |
| FEE | FVIELCTRNDRSLSTXN | Visa Electron Dr Sale Tran Fee |
| FEE | FVIELCTRNDRRFNDTXN | Visa Electron Dr Rfd Trans Fee |
| FEE | FMSTRSLSTXN | Maestro Sales Trans Fee |
| FEE | FMSTRRFNDTXN | Maestro Refunds Trans Fee |
| FEE | FSOLOSLSTXN | Solo Sales Trans Fee |
| FEE | FSOLORFNDTXN | Solo Refunds Trans Fee |
| FEE | FVICHIPSLSTXN | Visa Chip Sales Trans Fee |
| FEE | FVICHIPRFNDTXN | Visa Chip Refunds Trans Fee |
| FEE | FVIDRCHIPSLSTXN | Visa Dr Chip Sale Trans Fee |
| FEE | FVIDRCHIPRFNDTXN | Visa Dr Chip Refunds Trans Fee |
| FEE | FVPAYQSLSTXN | Vpay Qual Sales Trn Chg |
| FEE | FVPAYQRFNDTXN | Vpay Qual Rfnd Trn Charge |
| FEE | FMSTRSLSTXNINT | Intl Mstro Sales Trans Fee |
| FEE | FMSTRRETTXNINT | Intl Mstro Refunds Trans Fee |
| FEE | FVIPCARDSLSTXN | Visa Purchase Card Sale T/Fee |
| FEE | FMCSVCCHRG | Mastercard Service Charge |
| FEE | FMCRFND | Mastercard Refunds |
| FEE | FMCCHIPSVCCHRG | Mastercard Chip Service Charge |
| FEE | FMCCHIPRFND | Mastercard Chip Refunds |
| FEE | FMCPCARDSVCCHRG | Mc Purchase Card Serv Chrg |
| FEE | FMCPCARDRFND | Mc Purchase Card Refunds |
| FEE | FMCRFNDTXN | Mastercard Refunds Trans Fee |
| FEE | FMCCHIPSLSTXN | Mastercard Chip Sale Trans Fee |
| FEE | FMCCHIPRFNDTXN | Mastercard Chip Rfnd Trans Fee |
| FEE | FMCPCARDSLSTXN | Mc Purchase Card Sale T/Fee |
| FEE | FMCPCARDRFNDTXN | Mc Purchase Card Rfnd T/Fee |
| FEE | FMCCOMCARDSVCCHRG | Mc Commercial Card Serv Chrg |
| FEE | FMNTHLYMINF958 | Minimum Monthly Charge |
| FEE | FADDRVRFY | Address Verification |
| FEE | FAMXASSMNTF26D | Amex Assessment Fee |
| FEE | FAMXASSMNTF25A | Amex Assessment Fee |
| FEE | FAMXAUTH | Amex Auth Fee |
| FEE | FAMXAUTHF06D | Amex Authorizations |
| FEE | FAMXPRGRMPRCNG | Amex Program Pricing |
| FEE | FAMXPRGRMPRCNGF57S | Amex Program Pricing |
| FEE | FAMXVOICEAUTH | Amex Voice Auth Fee |
| FEE | FANNUALCMPLNCSUPRT | Annual Compliance Support Fee |
| FEE | FANNUALCMPLNCSUPRTF33K | Annual Compliance Support Fee |
| FEE | FANNUALCMPLNCSVCF32Q | Annual Compliance Svc Fee |
| FEE | FANNUALCMPLNCSVCF33A | Annual Compliance Svc Fee |
| FEE | FANNUALCMPLNCSVCF33D | Annual Compliance Svc Fee |
| FEE | FANNUALCMPLNCSVCF33G | Annual Compliance Svc Fee |
| FEE | FANNUALCMPLNCSVCF33B | Annual Compliance Svc Fee |
| FEE | FANNUALCMPLNCSVCF33C | Annual Compliance Svc Fee |
| FEE | FANNUALCMPLNCSVCF33E | Annual Compliance Svc Fee |
| FEE | FANNUALCMPLNCSVCF33F | Annual Compliance Svc Fee |
| FEE | FANNUALCMPLNCSVCF33H | Annual Compliance Svc Fee |
| FEE | FANNUALCMPLNCSVCF33I | Annual Compliance Svc Fee |
| FEE | FANNUALCMPLNCSVCF33J | Annual Compliance Svc Fee |
| FEE | FANNUALFEE | Annual Fee |
| FEE | FAPPLCTNFEE | Application Fee |
| FEE | FAUTH | Auth Fee |
| FEE | FCNCLTNFEE | Cancellation Fee |
| FEE | FCRDPNTEPLTFRM | Cardpointe Platform Fee |
| FEE | FCRDPNTEPLTFRMFY11 | Cardpointe Platform Fee |
| FEE | FCLVRSVC | Clover Services |
| FEE | FCLVRSVCF2ST | Clover Services Fee |
| FEE | FDSCNT | Discount |
| FEE | FDSCNTF80B | Discount |
| FEE | FDSCVAUTH | Discover Auth Fee |
| FEE | FDSCVAUTHF07D | Discover Authorizations |
| FEE | FINOUTEXCPTNSMS | Incoming/Outgoing Except Sms |
| FEE | FINOUTEXCPTNSMSFZ03 | Incoming/Outgoing Except Sms |
| FEE | FMAINSTRTINSGHT | Main Street Insights |
| FEE | FMAINSTRTINSGHTF49I | Main Street Insights |
| FEE | FMCVOICEAUTH | Mastercard Voice Auth Fee |
| FEE | FMCACCTSTTSINQSVCINTER | Mc Acct Status Inq Svc Interre |
| FEE | FMCACCTSTTSINQSVCINTRA | Mc Acct Status Inq Svc Intrare |
| FEE | FMISCADJFM74 | Misc Adjustment |
| FEE | FMISCFEE | Miscellaneous Fee |
| FEE | FACCESSMNTH | Monthly Access |
| FEE | FPCIVLDTNNONRECIPT | Non Receipt Of Pci Validation |
| FEE | FNQDSCNT | Non Qual Discount |
| FEE | FNQDSCNTF80R | Non Qual Discount |
| FEE | FPCIVLDTNNONRECIPTF60L | Non Receipt Of Pci Validation |
| FEE | FPINDBTAUTH | Pin Debit Auth Fee |
| FEE | FPINDBTAUTHF0CC | Pin Debit Auth Fee |
| FEE | FPRMTNLRBT | Promotional Rebate |
| FEE | FPRMTNLRBTF96S | Promotional Rebate |
| FEE | FQDSCNT | Qual Discount |
| FEE | FQDSCNTRATE | Qual Discount |
| FEE | FQDSCNTRATEF80P | Qual Discount |
| FEE | FQRTRLYCMPLNC | Quarterly Compliance Fee |
| FEE | FRPRGMING | Reprogramming Fees |
| FEE | FSLSDSCNT | Sales Discount Rate |
| FEE | FSLSDSCNTF80S | Sales Discount Rate |
| FEE | FSIGDBTAUTH | Sig Debit Auth Fee |
| FEE | FSIGDBTRETTXNF0A2 | Sig Debit Return Trans Fee |
| FEE | FSIGDBTRETTXN | Sig Debit Returns Trans Fee |
| FEE | FSIGDBTSLSDSCNTF27G | Sig Debit Sales Discount |
| FEE | FSIGDBTSLSDSCNT | Sig Debit Sales Discount |
| FEE | FSIGDBTSLSTXN | Sig Debit Sales Trans Fee |
| FEE | FSIGDBTSLSTXNF0A2 | Sig Debit Sales Trans Fee |
| FEE | FSWIPEDTXN | Swiped Transaction Fee |
| FEE | FTAMNTH | Transarmor Monthly Fee |
| FEE | FTAMNTHF4TA | Transarmor Monthly Fee |
| FEE | FVIASSMNTFEECRDT | Visa Assessment Fee Cr |
| FEE | FVIASSMNTFEECRDTF27K | Visa Assessment Fee Cr |
| FEE | FVINTWKFEECNPXXXX | Visa Network Fee Cp Xx Xx |
| FEE | FVINTWKFEECNPXXXXFNF5 | Visa Network Fee Cp Xx Xx |
| FEE | FWEXAUTHF0D4 | Wex Authorization Fee |
| FEE | FEQPMNTH | Monthly Equipment |
| FEE | FVOYIC | Voyager Interchange |
| FEE | FEQPMNTHFCRU | Monthly Equipment |
| FEE | FPERIPHRLBILLING | Peripheral Billing |
| FEE | FPERIPHRLSHPINGANDHNDLNG | Peripheral Ship And Handling |
| FEE | FEQPSHIPANDHANDLEFD15 | Equipment Shipping & Handling |
| FEE | FACHRJCT | Ach Reject |
| FEE | FDBTADJ | Debit Card Adjustments |
| FEE | FFTP3TRMNLBILLING | Ftp3 Terminal Billing Fee |
| FEE | FFTJ3TRMNLBILLING | Ftj3 Terminal Billing Fee |
| FEE | FTRMNLBILLING | Terminal Billing Fee |
| FEE | FIMPRNTR | Imprinter |
| FEE | FIMPRNTRFIPR | Imprinter Fee |
| FEE | FSTLMNTADJ | Settlement Adjustment |
| FEE | FPRPHRLSHIPANDHANLDE | Peripheral Shipping & Handling |
| FEE | FREVDUPLCTCRDT | Reverse Deuplicate Credit |
| FEE | FDBTCARDADJ | Debit Card Adjustment |
| FEE | FADJ | Adjustment |
| FEE | FSVIVRUSAGEMIN | Sv Ivr Usage Minute |
| FEE | FSVTELECOMNCTN | Sv Telecommunications Fee |
| FEE | FEQPMNTHFPRT | Monthly Equipment |
| FEE | FVFNTRMNLBILLING | Verifone Terminal Billing |
| FEE | FSVTELECOMNCTNFY18 | Sv Telecommunications Fee |
| FEE | FANNUALSCRTYBNDL | Annual Fee Security Bundle |
| FEE | FEBTTXN | Ebt Transaction |
| FEE | FDSCVAUTHF0BF | Discover Auth |
| FEE | FJCBAUTHF0BG | Jcb Auth |
| FEE | FDNRAUTHF0BH | Diners Auth |
| FEE | FWEXAUTHF0BJ | Wex Auth |
| FEE | FMCPREAUTH | Mc Pre Auth |
| FEE | FSIGDBTAUTHF0CI | Sig Debit Authorization Fee |
| FEE | FGCAUTH | Gift Card Authorizarion Fee |
| FEE | FFUTUREF03D | Future |
| FEE | FFUTUREF03F | Future |
| FEE | FFUTUREF04D | Future |
| FEE | FDNRAUTHF05D | Diners Authorizations |
| FEE | FFUTUREF05N | Future |
| FEE | FDNRAUTHF05S | Diners Auths |
| FEE | FDNRBTCHAUTH | Diners Batch Authorization |
| FEE | FJCBBTCHAUTHF08W | Jcb Batch Authorization |
| FEE | FMCDBTSLSTXNF1B0 | Mc Sales Debit Trans Fee |
| FEE | FVIDBTSLSTXNF1B4 | Vi Sales Debit Trans Fee |
| FEE | FDNRAUTH | Diners Auth Fee |
| FEE | FDNRVOICEAUTH | Diners Voice Auth Fee |
| FEE | FJCBAUTH | Jcb Auth Fee |
| FEE | FJSCBVOICEAUTH | Jcb Voice Auth Fee |
| FEE | FMCDBTSLSTXN | Mc Sales Debit Trans Fee |
| FEE | FMCDBTRETTXN | Mc Debit Returns Trans Fee |
| FEE | FVIDBTSLSTXNF134 | Vi Sales Debit Trans Fee |
| FEE | FVIDBTRETTXN | Vi Debit Returns Trans Fee |
| FEE | FAMXRETDSCNT | Amex Returns Discount |
| FEE | FAMXCHGBKDSCNT | Amex Chargeback Discount |
| FEE | FAMXRVSLDSCNT | Amex Reversal Discount |
| FEE | FDSCVSLSDSCNTF170 | Discover Sales Discount |
| FEE | FDSCVRETDSCNTF171 | Discover Returns Discount |
| FEE | FMCPCTOFSLSF195 | Mc Percent Of Sales Fee |
| FEE | FVIPCTOFSLS | Visa Percent Of Sales Fee |
| FEE | FMCACCSSF197 | Mastercard Access Fee |
| FEE | FSDS | Sds |
| FEE | FANNUALMMBRSHP | Annual Membership Fee |
| FEE | FMINPRCSNGFEE | Minimum Processing Fee |
| FEE | FMINPRCSNGFEEF202 | Minimum Processing Fee |
| FEE | FIMPRNTRF203 | Imprinter Fee |
| FEE | FCHGBK | Chargeback Fee |
| FEE | FSTLMNT | Settlement Statement Fee |
| FEE | FADJF207 | Adjustment Fee |
| FEE | FFDMSDBTTXN | Fdms Debit Transaction Fee |
| FEE | FMCCASHADVNCF210 | Mastercard Cash Advance |
| FEE | FVICASHADVNC | Visa Cash Advance |
| FEE | FMCCASHADVNC | Mc Cash Advance |
| FEE | FVICASHADVNCF213 | Visa Cash Advance |
| FEE | FFDMSLNKMNTH | Fdms Link Monthly Fee |
| FEE | FSVCCHRGMNTH | Monthly Service Charge |
| FEE | FACH | Ach Fee |
| FEE | FIMPRNTRRNTL | Imprinter Rental Fee |
| FEE | FSWIPEDTXNF23X | Swiped Transaction Fee |
| FEE | FIMPRNTRRNTLF230 | Imprinter Rental Fee |
| FEE | FIMPRNTRF231 | Imprinter |
| FEE | FVIASSMNTINTL | Visa International Assessment |
| FEE | FMCASSMNTF233 | Mastercard Assessment Fee |
| FEE | FVIASSMNTDBT | Visa Assessment Fee Db |
| FEE | FVIASSMNTCRDT | Visa Assessment Fee Cr |
| FEE | FPAPERSTMT | Paper Statement Fee |
| FEE | FVIACCESS | Visa Access Fee |
| FEE | FMCASSMNTF242 | Mastercard Assessment Fee |
| FEE | FVIASSMNTDBTF244 | Visa Assessment Fee Db |
| FEE | FAPPLCTNFEEF247 | Application Fee |
| FEE | FFAXSTMT | Fax Statement Fee |
| FEE | FARBTRTN | Arbitration Fee |
| FEE | FFAXSTMTF269 | Fax Statement Fee |
| FEE | FMCASSMNTF273 | Mastercard Assessment Fee |
| FEE | FVIASSMNTDBTF274 | Visa Assessment Fee Db |
| FEE | FADDRVRFYF288 | Address Verification Fee |
| FEE | FANNUALMMBRSHPF294 | Annual Membership Fee |
| FEE | FPLTNMSVCPKG | Platinum Service Package |
| FEE | FPLTNMSVCPKGF3AE | Platinum Service Package |
| FEE | FSVIVRUSAGEMINF3V1 | Sv Ivr Usage Minute |
| FEE | FGLBLGTWY | Global Gateway Fee |
| FEE | FTCKSETUP | Tck Set Up Fee |
| FEE | FICVRFYVAL | Ic Verify Val Code |
| FEE | FIMPRNTRF32D | Imprinter Fee |
| FEE | FRSKPRM | Risk Premium Fee |
| FEE | FFDMSLNKMNTHF32S | Fdms Link Monthly Fee |
| FEE | FSVCCHRGMNTHF329 | Monthly Service Charge |
| FEE | FMISCFEEF332 | Miscellaneous Fee |
| FEE | FSVCCHRGMNTHF335 | Monthly Service Charge |
| FEE | FPAPERSTMTF358 | Paper Statement Fee |
| FEE | FTRMNLMNTNCF372 | Terminal Maintenance Fee |
| FEE | FTRMNLMNTNCF379 | Terminal Maintenance Fee |
| FEE | FTRMNLBILLINGF380 | Terminal Billing |
| FEE | FMNTHLYACCSS | Monthly Access Fee |
| FEE | FPLTNMSVCPKGF40E | Platinum Service Package |
| FEE | FACHRJCTF401 | Ach Reject Fee |
| FEE | FSCRTYMNGDSVC | Security Managed Service |
| FEE | FACHF423 | Ach Fee |
| FEE | FMSTRLCLAUTH | Maestro Local Auth Fee |
| FEE | FMCSLSDSCNTF440 | Mastercard Sales Discount |
| FEE | FMCRETDSCNTF441 | Mastercard Returns Discount |
| FEE | FANNUALFEEF442 | Annual Fee |
| FEE | FFIXEDFEEMNTH | Monthly Fixed Fee |
| FEE | FVISLSDSCNTF444 | Visa Sales Discount |
| FEE | FVIRETDSCNTF445 | Visa Returns Discount |
| FEE | FDSCVCHGBKF446 | Discover Chargeback Fee |
| FEE | FTXNPRCSNG | Transaction Processing Fee |
| FEE | FTXNPRCSNGF453 | Transaction Processing Fee |
| FEE | FGLBLGTWYF463 | Global Gateway Fee |
| FEE | FMCNOAUTH2NDCHGBK | No Auth 2Nd Cb Mc |
| FEE | FLLTYACCTSONFILE | Loyalty Accounts On File |
| FEE | FMCPCTOFSLS | Mc Percent Of Sales Fee |
| FEE | FVIPCTOFSLSF496 | Visa Percent Of Sales Fee |
| FEE | FANNUALFEEF497 | Annual Fee |
| FEE | FFIXEDFEEMNTHF498 | Monthly Fixed Fee |
| FEE | FVIACCESSF504 | Visa Access Fee |
| FEE | FMCACCSS | Mastercard Access Fee |
| FEE | FPREPDCASHCARDIC | Pre Paid Cash Card Intrchg Fee |
| FEE | FAMEXIC | American Express Interchange |
| FEE | FDSCVIC | Discover Interchange |
| FEE | FDSCVICF529 | Discover Interchange Fee |
| FEE | FDSCVIC530 | Discover Interchange Fee |
| FEE | FJCBIC | Jcb Interchange Fee |
| FEE | FSIGDBTIC | Sig Debit Interchange |
| FEE | FSIGDBTICF57G | Sig Debit Interchange |
| FEE | FAMXIC | Amex Interchange Fee |
| FEE | FDNRIC | Diners Interchange Fee |
| FEE | FDBTICF590 | Debit Interchange Fee |
| FEE | FDBTIC | Debit Interchange Fee |
| FEE | FEBTIC | Ebt Interchange Fee |
| FEE | FADJF597 | Adjustment Fee |
| FEE | FSCRTYMNGDSVCF6JN | Security Managed Service |
| FEE | FVIASSMNTINTLF6KU | Visa Int Assessment Fee |
| FEE | FRSKPRMMINIMUM | Risk Premium Fee |
| FEE | FMCNQSLSTXN | Mc Non Qual Sales Trans Fee |
| FEE | FVINQSLSTXN | Visa Non Qual Sales Trans Fee |
| FEE | FMCDBTSLSDSCNTF690 | Mc Debit Sales Discount |
| FEE | FMCDBTRETDSCNTF691 | Mc Debit Returns Discount |
| FEE | FVIDBTSLSDSCNTF694 | Visa Debit Sales Discount |
| FEE | FVIDBTRETDSCNTF695 | Visa Debit Returns Disc |
| FEE | FDSCVDBTSLSTXNF7B2 | Discover Debit Sale Trans |
| FEE | FDSCVCHGBK | Discover Chargeback Fee |
| FEE | FVOYSLSDSCNTF766 | Voyager Sales Discount Fee |
| FEE | FVOYRETDSCNTF767 | Voyager Credit Discount Fee |
| FEE | FDSCVDBTSLSTXN | Discover Debit Sale Trans |
| FEE | FDSCVRETTXN | Discover Debit Returns Trans |
| FEE | FMCCOMCARDREFNDTXN | Mc Commercial Card Rfnd T/Fee |
| FEE | FMCSLSDSCNT | Mastercard Sales Discount |
| FEE | FMCRETDSCNT | Mastercard Returns Discount |
| FEE | FVISLSDSCNT | Visa Sales Discount |
| FEE | FVIRETDSCNT | Visa Returns Discount |
| FEE | FAMXCHGBKDSCNTF81A | Amex Chargeback Discount |
| FEE | FAMXRVSLDSCNTF81B | Amex Reversal Discount |
| FEE | FAMXRETDSCNTF84B | Amex Returns Discount |
| FEE | FVOYSLSDSCNT | Voyager Sales Discount Fee |
| FEE | FVOYRETDSCNT | Voyager Credit Discount Fee |
| FEE | FMCDBTSLSDSCNT | Mastercard Debit Sales Disc |
| FEE | FMCDBTRETDSCNT | Mastercard Debit Returns Disc |
| FEE | FVIDBTSLSDSCNT | Visa Debit Sales Discount |
| FEE | FVIDBTRETDSCNT | Visa Debit Return Discount |
| FEE | FVOLDSCNT | Vol. Discount 9L1 |
| FEE | FVOLDSCNTF9L2 | Vol. Discount 9L2 |
| FEE | FDSCVDBTSLSDSCNT | Discover Debit Sales Discount |
| FEE | FMCCARD | Mastercard Card Fee |
| FEE | FDSCVDBTSLSDSCNTF964 | Discover Debit Sales Discount |
| FEE | FDSCVDBTRETDSCNTF965 | Discover Debit Return Discount |
| FEE | FDSCVSLSDSCNT | Discover Sales Discount |
| FEE | FDSCVRETDSCNT | Discover Returns Discount |
| FEE | FDSCVDBTRETDSCNT | Discover Debit Returns Disc |
| FEE | FEQPSHIPANDHANDLE | Equipment Ship And Handling |
| FEE | FJCBBTCHAUTH | Jcb Batch Authorization Fee |
| FEE | FCHGBKF236 | Chargeback Fee |
| FEE | FMCCRDT | Mc Credit |
| FEE | FCJCBIC | Jcb Interchange Fee |
| FEE | FVIICF552 | Visa Interchange Fee |
| FEE | FMCIC | Mastercard Interchange Fee |
| FEE | FAMXICF572 | Amex Interchange Fee |
| FEE | FDNRICF582 | Diners Interchange Fee |
| FEE | FDNRSLSTXNF6DT | Diners Sales Trans Fee |
| FEE | FMCPCARDSVCCHRGCNTLS | Mc Purch Crd Srv Chrg Cnt Less |
| FEE | FVINQSLSTXNF66A | Visa Non Qual Sales Trans Fee |
| FEE | FMCNQSLSTXNF68G | Mastercard Nq Sales Trans Fee |
| FEE | FVISLSTXNF78A | Visa Sales Trans Fee |
| FEE | FMCSLSTXNF79G | Mastercard Sales Trans Fee |
| FEE | FMCCOMCARDREFND | Mc Commercial Card Refunds |
| FEE | FMTHLYACCT | Monthly Account Fee |
| FEE | FGCCNTRTOPSTNDFG42 | Gc Counter Top Stand |
| FEE | FDBTOTHRDCLN | Other Debit Decline |
| FEE | FDBTPTHRSLS | Other Debit Sale |
| FEE | FDBTPTHRVOID | Other Debit Void |
| FEE | FDBTPTHRBLNCINQ | Other Debit Bal Inq |
| FEE | FDBTPTHRERR | Other Debit Error |
| FEE | FMCSLSTXN | Mastercard Sales Trans Fee |
| FEE | FMCCRDTTXN | Mastercard Credits Trans Fee |
| FEE | FMCCHGBKTXN | Mastercard Chrgbcks Trans Fee |
| FEE | FMCRVSLTXN | Mastercard Reversals Trans Fee |
| FEE | FVISLSTXN | Visa Sales Trans Fee |
| FEE | FVICRDTTXN | Visa Credits Trans Fee |
| FEE | FVICHGBKTXN | Visa Chargebacks Trans Fee |
| FEE | FVIRVSLTXN | Visa Reversals Trans Fee |
| FEE | FDNRSLSTXN | Diners Sales Trans |
| FEE | FDNRCRDTTXN | Diners Credits Trans |
| FEE | FDNRCHGBKTXN | Diners Chrgbcks Trans |
| FEE | FDNRRVSLTXN | Diners Reversals Trans |
| FEE | FAMXSLSTXN | Amex Sales Trans Fee |
| FEE | FAMXCRDTTXN | Amex Credits Trans Fee |
| FEE | FDSCVSLSTXN | Discover Sales Trans Fee |
| FEE | FDSCVCRDTTXN | Discover Credits Trans Fee |
| FEE | FFDMSDBTTXNF017 | Fdms Debit Transaction Fee |
| FEE | FDBTATMCARDTXN018 | Debit/Atm Card Transaction Fee |
| FEE | FPVTLBLSLSTXN | Private Label Sales Trans Fee |
| FEE | FVICHKCARDSLS | Private Label Returns Tran Fee |
| FEE | FVISCHKCARDRET | Visa Check Card Sales Fee |
| FEE | FVICHKRETTXN | Visa Check Card Returns Fee |
| FEE | FVICHKCHGBKTXN | Visa Check Card Chargeback Fee |
| FEE | FVICHKCARDCHGBKRVSL | Visa Check Card Chgbk Reversal |
| FEE | FJCBSLSTXN | Jcb Sales Transaction Fee |
| FEE | FJCBCRDTTXN | Jcb Credit Transaction Fee |
| FEE | FJCBCHGBKTXN | Jcb Chargeback Transaction Fee |
| FEE | FJCBRVSLTXN | Jcb Reversal Transaction Fee |
| FEE | FEBTPRCHSRETTXN | Ebt Purchase/Return Trans Fee |
| FEE | FMCLCLAUTH | Mastercard Local Auth Fee |
| FEE | FMCWATSAUTH | Mastercard Wats Auth Fee |
| FEE | FMCLOCALWATSAUTH | Mastercard Local/Wats Auth Fee |
| FEE | FMCECRAUTH | Mastercard Ecr Auth Fee |
| FEE | FMCDRCTSOLNAUTH | Mastercard Direct Solutions |
| FEE | FMCVOICEAUTH035 | Mastercard Voice Auth Fee |
| FEE | FMCVRUAUTH | Mastercard Vru Auth Fee |
| FEE | FMCVRUVOICEAUTH | Mastercard Vru/Voice Auth Fee |
| FEE | FMCEDCCPTR | Mastercard Edc Capture Fee |
| FEE | FMCVOICEADDRVRFY | Mastercard Voice Addr Verif |
| FEE | FVILCLAUTH | Visa Local Auth Fee |
| FEE | FVIWATSAUTH | Visa Wats Auth Fee |
| FEE | FVILCLWATSAUTH | Visa Local/Wats Auth Fee |
| FEE | FVIECRAUTH | Visa Ecr Auth Fee |
| FEE | FVIDRCTSOLN | Visa Direct Solutions Auth Fee |
| FEE | FVIVOICEAUTH045 | Visa Voice Auth Fee |
| FEE | FVIVRUAUTH | Visa Vru Auth Fee |
| FEE | FVIVRUVOICEAUTH | Visa Vru/Voice Auth Fee |
| FEE | FVIEDCCPTR | Visa Edc Capture Fee |
| FEE | FVIVOICEADDRVRFY | Visa Voice Address Verif |
| FEE | FDNRLCLAUTH | Diners Local Auth Fee |
| FEE | FDNRWATSAUTH | Diners Wats Auth Fee |
| FEE | FDNRLCLAWATSAUTH | Diners Local/Wats Auth |
| FEE | FDNRECRAUTH | Diners Ecr Auth Fee |
| FEE | FDNRDRCTSOLNAUTH | Diners Direct Solutions Auth |
| FEE | FDNRVOICEAUTH055 | Diners Voice Auth Fee |
| FEE | FDNRVRUAUTH | Diners Vru Auth Fee |
| FEE | FDNRVRUVOICEAUTH | Diners Vru/Voice Auth |
| FEE | FDNREDCCPTR | Diners Edc Capture Fee |
| FEE | FDNRVOICEADDRVRFY | Diners Voice Addr Verification |
| FEE | FAMXSLS | Amex Sales |
| FEE | FAMXVOID | Amex Voids |
| FEE | FAMXAUTH06H | Amex Authorizations |
| FEE | FAMXCRDTRET | Amex Credits/Returns |
| FEE | FAMXCPTRONLNTXN | Amex Capture Online Trans |
| FEE | FAMXFDCINTGTWYAUTH | Amex Fdc Int Gw Auth Fee |
| FEE | FAMXLCLAUTH | Amex Local Auth Fee |
| FEE | FAMXWATSAUTH | Amex Wats Auth Fee |
| FEE | FAMXLCLWATSAUTH | Amex Local/Wats Auth Fee |
| FEE | FAMXECRAUTH | Amex Ecr Auth Fee |
| FEE | FAMXDRCTSOLNAUTH | Amex Direct Solutions Auth Fee |
| FEE | FAMXVOICEAUTH065 | Amex Voice Auth Fee |
| FEE | FAMXVRUAUTH | Amex Vru Auth Fee |
| FEE | FAMXVRUVOICEAUTH | Amex Vru/Voice Auth Fee |
| FEE | FAMXEDCCPTR | Amex Edc Capture Fee |
| FEE | FAMXVOICEADDRVRFY | Amex Voice Addr Verification |
| FEE | FDSCVSLS | Discover Sales |
| FEE | FDSCVAUTH07H | Discover Authorizations |
| FEE | FDSCVONLNCPTR | Discover Online Capture |
| FEE | FDSCVLCLAUTH | Discover Local Auth Fee |
| FEE | FDSCVWATSAUTH | Discover Wats Auth Fee |
| FEE | FDSCVLOCALWATSAUTH | Discover Local/Wats Auth Fee |
| FEE | FDSCVECRAUTH | Discover Ecr Auth Fee |
| FEE | FDSCVDRCTSOLN | Discover Direct Solutions Auth |
| FEE | FDSCVVOICEAUTH075 | Discover Voice Auth Fee |
| FEE | FDSCVVRUAUTH | Discover Vru Auth Fee |
| FEE | FDSCVVRUVOICEAUTH | Discover Vru/Voice Auth Fee |
| FEE | FDSCVEDCCPTR | Discover Edc Capture Fee |
| FEE | FDSCVVOICEADDRVRFY | Discover Voice Addr Verif |
| FEE | FJCBINTRNTLIAUTH | Jcb Internet Ll Auth Fee |
| FEE | FJCBINTGWTYAUTH | Jcb Fdc Int Gw Auth Fee |
| FEE | FJCBINTRNTDIALAUTH | Jcb Internet Dial Auth Fee |
| FEE | FJCBAUTH08H | Jcb Authorizations |
| FEE | FJCBLCLAUTH | Jcb Local Auth Fee |
| FEE | FJCBWATSAUTH081 | Jcb Wats Auth Fee |
| FEE | FJCBLCLWATSAUTH | Jcb Local/Wats Auth Fee |
| FEE | FJCBECRAUTH | Jcb Ecr Auth Fee |
| FEE | FJCBDRCTSOLNAUTH | Jcb Direct Solutions Auth Fee |
| FEE | FJCBVOICEAUTH | Jcb Voice Auth Fee |
| FEE | FJCBVRUAUTH | Jcb Vru Auth Fee |
| FEE | FJCBVRUVOICEAUTH | Jcb Vru/Voice Auth Fee |
| FEE | FJCBEDCCPTR | Jcb Edc Capture Fee |
| FEE | FPVTLBLLCLAUTH | Private Label Local Auth Fee |
| FEE | FPVTLBLWATSAUTH | Private Label Wats Auth Fee |
| FEE | FPVTLBLLCLWATSAUTH | Private Label Local/Wats Auth |
| FEE | FPVTLBLECRAUTH | Private Label Ecr Auth Fee |
| FEE | FPVTLBLDRCTSOLNAUTH | Private Label Direct Solutions |
| FEE | FPVTLBLVRUAUTH | Private Label Vru Auth Fee |
| FEE | FPVTLBLVRUVOICE | Private Label Vru/Voice Auth |
| FEE | FPVTLBLEDCCPTR | Private Label Edc Capture Fee |
| FEE | FENRTVOICEAUTH | Enroute Voice Auth Fee |
| FEE | FSTRDCLNTXN | Star Decline Trans Fee |
| FEE | FSTRAPPRVDTXN | Star Approved Trans Fee |
| FEE | FSTRVOIDTXN | Star Void Trans Fee |
| FEE | FSTRBLNCINQ | Star Balance Inquiry Fee |
| FEE | FSTRERRTXN | Star Error Trans Fee |
| FEE | FINTRLNKDCLNTXN | Interlink Decline Trans Fee |
| FEE | FINTRLNKAPPRVDTXN | Interlink Approved Trans Fee |
| FEE | FINTRLNKVOIDTXN | Interlink Void Trans Fee |
| FEE | FINTRLNKBLNCINQ | Interlink Balance Inquiry Fee |
| FEE | FINTRLNKERRTXN | Interlink Error Trans Fee |
| FEE | FPINDBTTXN | Pin Debit Transaction Fee |
| FEE | FBUYPSCHKAUTH | Buypass Check Authorizations |
| FEE | FINTRLNKDCLN | Interlink Decline Fee |
| FEE | FMACDCLN | Mac Decline Fee |
| FEE | FMSTRDCLN | Maestro Decline Fee |
| FEE | FMAGICLINEDCLN | Magicline Decline Fee |
| FEE | FNYCEDCLN | Nyce Decline Fee |
| FEE | FPULSEDCLN | Pulse Decline Fee |
| FEE | FSZMDCLN | Shazam Decline Fee |
| FEE | FTYMEDCLN | Tyme Decline Fee |
| FEE | FTXDCLN | Tx Decline Fee |
| FEE | FCU24DCLN | Cu 24 Decline Fee |
| FEE | FMPACTDCLN | Mpact Decline Fee |
| FEE | FAFFNDCLN | Affn Decline Fee |
| FEE | FALASKADCLN | Alaska Option Decline Fee |
| FEE | FINSTNTTELLERDCLN | Instant Teller Decline Fee |
| FEE | FSTART950AUTH | Star 950 Auth Fee |
| FEE | FDBTATMMACNTWK | Dbt/Atm Mac Ntwk Fees |
| FEE | FBANCONEMATRX601 | Banc One Matrix 601 |
| FEE | FBANCONEMATRX749 | Banc One Matrix 749 |
| FEE | FPVTLBLAUTH | Private Label Auth Fee |
| FEE | FGCFOBCNTLS | Gc Contactless Gift Card Fob |
| FEE | FGCDECENTRACHSETUP | Gc Decentr Ach Set Up Fee |
| FEE | FGCDECNTRACHTXNSRCHRG | Gc Decentr Ach Trans Surcharge |
| FEE | FMCCHIPSRVCHRGCNTED | Mc Chip Srv Chrg Cnt Ed |
| FEE | FMCCHIPRFNDCNTED | Mc Chip Rfnd Cnt Ed |
| FEE | FMCCHIPNQSVCCHRGCNTED | Mc Chip Nq Srv Chrg Cnt Ed |
| FEE | FMCDRCHIPSRVCHRGCNTED | Mc Dr Chip Srv Chrg Cnt Ed |
| FEE | FMCDRCHIPRFNDCNTED | Mc Dr Chip Rfnd Cnt Ed |
| FEE | FMCDRCHIPNQSVCCHRGCNTED | Mc Dr Chip Nq Srv Chrg Cnt Ed |
| FEE | FMCDRCHIPNQRFNDCNTED | Mc Dr Chip Nq Rfnd Cnt Ed |
| FEE | FMCPCARDSVCCHRGCNTED | Mc Purch Crd Srv Chrg Cnt Ed |
| FEE | FMCPCARDNQSVCCHRGCNTED | Mc Purch Crd Nq Srv Chg Cnt Ed |
| FEE | FVPAYQSLSSVCCHRGCNTLS | Vpay Qual Sls Srv Chrg Cnt Les |
| FEE | FMCCOMCARDSVCCHRGCNTED | Mc Comm Crd Srv Chrg Cnt Ed |
| FEE | FMCCOMCRDRFNDCNTED | Mc Comm Crd Rfnd Cnt Ed |
| FEE | FVPAYQSLSSVCCHRGCNTED | Vpay Qual Sls Srv Chrg Cnt Ed |
| FEE | FVPAYQRFNDSVCCHRGCNTED | Vpay Qual Rfnd Srv Chg Cnt Ed |
| FEE | FVPAYNQSLSSVCCHRGCNTED | Vpay Nq Sls Srv Chg Cnt Ed |
| FEE | FVPAYNQRFNDSCVCCHRGCNTED | Vpay Nq Rfnd Srv Chg Cnt Ed |
| FEE | FVICHIPSRVCHRGCNTED | Vi Chip Srv Chrg Cnt Ed |
| FEE | FVICHIPRFNDCNTED | Vi Chip Rfnd Cnt Ed |
| FEE | FVICHIPNQSVCCHRGCNTED | Vi Chip Nq Srv Chrg Cnt Ed |
| FEE | FVICHIPNQRFNDCNTED | Vi Chip Nq Rfnd Cnt Ed |
| FEE | FVIDBCHIPSVCCHRGCNTED | Vi Db Chip Srv Chrg Cnt Ed |
| FEE | FVIDBCHIPRFNDCNTED | Vi Db Chip Rfnd Cnt Ed |
| FEE | FVIDBCHIPNQRFNDCNTED | Vi Db Chip Nq Srv Chrg Cnt Ed |
| FEE | FVIDBCHPNQRFNDCNTED | Vi Db Chip Nq Rfnd Cnt Ed |
| FEE | FVIPRCARDSVCCHRGCNTED | Vi Purch Crd Srv Chrg Cnt Ed |
| FEE | FVIPRCARDRFNDCNTED | Vi Purch Crd Rfnd Cnt Ed |
| FEE | FVIPCARDNQSVCCHRGCNTED | Vi Purch Crd Nq Srv Chg Cnt Ed |
| FEE | FVIPCARDNQRFNDCNTED | Vi Purch Crd Nq Rfnd Cnt Ed |
| FEE | FVIELCTRNDRSVCCHRGCNTED | Vi Electrn Dr Srv Chrg Cnt Ed |
| FEE | FVIELCTRNDRRFNDCNTED | Vi Electron Dr Rfnd Cnt Ed |
| FEE | FVIELCTRNQDRSVCCHRGCNTED | Vi Elect Nq Dr Srv Chrg Cnt Ed |
| FEE | FVIELCTRNNQDRRFNDCNTED | Vi Electron Nq Dr Rfnd Cnt Ed |
| FEE | FMCCHIPSLSTXNCNTED | Mc Chip Sls Trn Cnt Ed |
| FEE | FMCCHIPNQSLSTXNCNTED | Mc Chip Nq Sls Trn Cnt Ed |
| FEE | FMCCHIPNQRFNDTXNCNTED | Mc Chip Nq Rfnd Trn Cnt Ed |
| FEE | FMCDRCHIPSLSTXNCNTED | Mc Dr Chip Sls Trn Cnt Ed |
| FEE | FMCDRCHIPRFNDTXNCNTED | Mc Dr Chip Rfnd Trn Cnt Ed |
| FEE | FMCDRCHIPNQSLSDTXNCNTED | Mc Dr Chip Nq Sls Trn Cnt Ed |
| FEE | FMCDRCHIPNQRFNDTXNCNTED | Mc Dr Chip Nq Rfnd Trn Cnt Ed |
| FEE | FVICHIPRFNDSLSTXCNTED | Vi Chip Rfnd Trn Cnt Ed |
| FEE | FVICHIPNQSLSTXNCNTED | Vi Chip Nq Sls Trn Cnt Ed |
| FEE | FVIDRCHIPSLSTXNCNTED | Vi Dr Chip Sls Trn Cnt Ed |
| FEE | FVIDRCHIPRFNDTXNCNTED | Vi Dr Chip Rfnd Trn Cnt Ed |
| FEE | FVIDRCHIPNQSLSTXNCNTED | Vi Dr Chip Nq Sls Trn Cnt Ed |
| FEE | FVIDRCHIPNQRFNDTXNCNTED | Vi Dr Chip Nq Rfnd Trn Cnt Ed |
| FEE | FVIPRCARDSLSTXNCNTED | Vi Purch Crd Sls Trn Cnt Ed |
| FEE | FVIZEROACCTVERCR | Visa Zero Acct Ver Cr Fee |
| FEE | FMCNTWKACCESSSTLMT | Mc Ntwrk Access Settlement Fee |
| FEE | FTATKNENCRPT | Transarmor Token & Encrypt |
| FEE | FJCBHOSTCPTR | Host Capture Fee Jcb |
| FEE | FPVTLBLHOSTCPTR | Host Capture Fee Privte Labl |
| FEE | FEQSRVCCNTRCT | Equipment Service Contract |
| FEE | FMSTROINQSLSTXNCNTED | Intl Mstro Nq Sls Trn Cnt Ed |
| FEE | FMSTROINQRFNDCNTED | Intl Mstro Nq Rfnd Cnt Ed |
| FEE | FMSTROINQRFNDTXNCNTED | Intl Mstro Nq Rfnd Trn Cnt Ed |
| FEE | FMSTROINQSRVCHRGCNTED | Intl Mstro Nq Srv Chrg Cnt Ed |
| FEE | FVIPURSCHGCNTEDEXBUSDR | Vi Pur S/Chg Cnt Ed(Ex Bus Dr) |
| FEE | FVIPURRFNDCNTEDEXBUSDR | Vi Pur Ref Cnt Ed (Ex Bus Dr) |
| FEE | FVIPURNQSCHGCNTEDEXBUSDR | Vi Pur Nq Schg Cnt Ed(Ex B Dr) |
| FEE | FVIPURNQRFNDCNTEDEXBUSDR | Vi Pur Nq Ref Cnt Ed(Ex B Dr) |
| FEE | FVIBUSDRCRDSCHGCNTED | Vi Bus Dr Crd Srv Chrg Cnt Ed |
| FEE | FVIBUSDRCRDRFNDCNTED | Vi Bus Dr Crd Rfnd Cnt Ed |
| FEE | FVIBUSDRCRDNQSCHGCNTED | Vi Bus Dr Cd Nq Srv Chg Cnt Ed |
| FEE | FVIBUSDRCRDNQRFNDCNTED | Vi Bus Dr Crd Nq Rfnd Cnt Ed |
| FEE | FVIBUSDRCRDSLSTXNCNTED | Vi Bus Dr Crd Sls Trn Cnt Ed |
| FEE | FVIBUSDRCRDRFNDTXNCTNED | Vi Bus Dr Crd Rfnd Trn Cnt Ed |
| FEE | FVIBUSDRCRDNQTXNCNTED | Vi Bus Dr Crd Nq Trn Cnt Ed |
| FEE | FVIBUSDRCRDNQRFNDTCNTED | Vi Bus Dr Crd Nq Rfnd T/Cnt Ed |
| FEE | FVIPURSLSTXNCNTEDEXBUSDR | Vi Pur Sl Tx Cnt Ed(Ex Bus Dr) |
| FEE | FVIPURRFNDTXNCNTEDEXBUSDR | Vi Pur Ref Trn Cnt Ed(Ex B Dr) |
| FEE | FVIPURNQTXNCNTEDEXBUSDR | Vi Pur Nq Tx Cnt Ed(Ex Bus Dr) |
| FEE | FVIPURNQRFNDTCNTEDEXBUSDR | Vi Pur Nq Ref T/Cnt D(Ex B Dr) |
| FEE | FVICOMMSCHGCNTEDEXBUSDR | Vi Comm S/Chg Cnt Ed(Ex B Dr) |
| FEE | FVICOMMRFNDCNTEDEXBUSDR | Vi Comm Rfnd Cnt Ed(Ex Bus Dr) |
| FEE | FMSTROINSLSTXNCNTED | Intl Mstro Sls Trn Cnt Ed |
| FEE | FMSTROINRFNDCNTED | Intl Mstro Rfnd Cnt Ed |
| FEE | FMSTROINRFNDTXNCNTED | Intl Mstro Rfnd Trn Cnt Ed |
| FEE | FMSTROINSCHGCNTED | Intl Mstro Srv Chrg Cnt Ed |
| FEE | FTATKNENCRPTVF | Transarmor Token & Encrypt Vf |
| FEE | FSTRNTWKINTGRTY | Star Network Integrity Fee |
| FEE | FMCLACNTVKEXPASSMT | Lac Mc Netw Exp Assessment |
| FEE | FPCIQRTRLYSVC | Pci Quarterly Svc Fee |
| FEE | FNWINTRLNKPARBCNPRMDYSMS | Nw Intrlnk Prearb Cnp Rmdy Sms |
| FEE | FINTRLNKFRAUDRMDYUPFRNTSMS | Intrlnk Fraud Rmdy Upfront Sms |
| FEE | FINTRLNKFRAUDRMDYSMS | Intrlnk Fraud Rmdy Mrchant Sms |
| FEE | FVIACCTNMINQ | Vi Account Name Inquiry Fee |
| FEE | FVIMISUSEOFAUTHNONUS | Visa Misuse Of Auth Fee Non Us |
| FEE | FVIUNMTCHCLRNONUS | Visa Unmatched Clear Fee Nonus |
| FEE | FVIDGTLACCTUPDATER | Visa Digital Acct Updater Fee |
| FEE | FMNTHLYSCRTYBNDL | Monthly Security Bundle |
| FEE | FDEXMNTHLYSUPPRT | Dex Monthly Support Fee |
| FEE | FMCAUTHOPTMZRNSF | Mc Auth Optimizer Nsf Fee |
| FEE | FMCPREAUTHCP | Mc Pre Auth Fee Cp |
| FEE | FMCPREAUTHFEECNP | Mc Pre Auth Fee Cnp |
| FEE | FMCPREAUTHCPMIN | Mc Pre Auth Fee Cp Min |
| FEE | FMCPREAUTHFEECNPMIN | Mc Pre Auth Fee Cnp Min |
| FEE | FMCLACPREAUTHDOMMIN | Mc Lac Preauth Fee Dom Min |
| FEE | FMCLACPREAUTHXBORMIN | Mc Lac Preauth Fee Xbor Min |
| FEE | FMCTPEMCHPDPLYMNTPRG | Mc Tpe M/Chip Deployment Prg |
| FEE | FNWDISCINQREQNONRESPDMS | Nw Disc Inq Req Non Resp Dms |
| FEE | FNWDISCRPRSNTMNTDMS | Nw Disc Representment Fee Dms |
| FEE | FVIDGTLCOMMERCESVC | Vi Digital Commerce Svcs Fee |
| FEE | FVIDGTLCOMMERCESVCMN | Vi Digital Commerce Svc Fee Mn |
| FEE | FCMPLYALLYMNGDSVC | Complyally Managed Services |
| FEE | FANNENDOFSUPPRTDVC | Ann End Of Support Device Fee |
| FEE | FEOLDVC | Eol Device Fee |
| FEE | FANNUALMMBRSHP2023 | Annual Membership Fee 2023 |
| FEE | FMCINCRFNDREQDMS | Inc Refund Req Mc Dms |
| FEE | FMCRFNDREQRSPDMS | Refund Req Rsp Mc Dms |
| FEE | FMCNWRFNDREQDMS | Nw Refund Request Mc Dms |
| FEE | FMCRFNDREQRSPTIER1 | Refund Req Rsp Mc Tier 1 |
| FEE | FMCRFNDREQRSPTIER2 | Refund Req Rsp Mc Tier 2 |
| FEE | FMCCOLLABADJDMS | Collaboration Adj Mc Dms |
| FEE | FLYLTACCTUPD | Loyalty Account Update Fee |
| FEE | FLYLTADDACCT | Loyalty Add Account Fee |
| FEE | FLYLTCUSTMRPLTFPRG | Loyalty Custom Platform Pgming |
| FEE | FLYLTCUSTMRRPT | Loyalty Custom Reporting |
| FEE | FLYLTDATAANALTC | Loyalty Data Analytics |
| FEE | FLYLTDATAEXTRCT | Loyalty Data Extracts |
| FEE | FLYLTGRPHDSGN | Loyalty Graphic Design |
| FEE | FLYLTINQ | Loyalty Inquiry Fee |
| FEE | FLYLTYPRTCPTN | Loyalty Participation Fee |
| FEE | FLYLTYPRGMCONSLTN | Loyalty Program Consultation |
| FEE | FLYLTYRDMPTN | Loyalty Redemption Fee |
| FEE | FLYLTYWEBDEV | Loyalty Website Dev/Graphics |
| FEE | FLYLTYWEBHOST | Loyalty Website Hosting |
| FEE | FMCANNUALLICAPR | Mc Annual License Fee April |
| FEE | FMCANNUALLICAUG | Mc Annual License Fee Aug |
| FEE | FMCANNUALLICDEC | Mc Annual License Fee Dec |
| FEE | FMCANNUALLICJAN | Mc Annual License Fee Jan |
| FEE | FMCANNUALLICJUL | Mc Annual License Fee July |
| FEE | FMCANNUALLICJUN | Mc Annual License Fee June |
| FEE | FMCANNUALLICMAR | Mc Annual License Fee March |
| FEE | FMCANNUALLICMAY | Mc Annual License Fee May |
| FEE | FMCANNUALLICNOV | Mc Annual License Fee Nov |
| FEE | FMCANNUALLICOCT | Mc Annual License Fee Oct |
| FEE | FMIDWESTCLUBPRGM | Midwest Club Program |
| FEE | FMNTHMINDBT | Monthly Minimum Debit Fee |
| FEE | FNQDSCNTF21E | Non Qual Discount |
| FEE | FACSNWCHGBKRPSMNTSMS | Nw Cb Representment Acs Sms |
| FEE | FAFFNNWCHGBKRPSMNTSMS | Nw Cb Representment Affn Sms |
| FEE | FATHNWCHGBKRPSMNTSMS | Nw Cb Representment Ath Sms |
| FEE | FCU24NWCHGBKRPSMNTSMS | Nw Cb Representment Cu24 Sms |
| FEE | FEFNDSNWCHGBKRPSMNTSMS | Nw Cb Representment Efunds Sms |
| FEE | FINTLNKNWCHGBKRPSMNT | Nw Cb Representment Interlink |
| FEE | FJEANIENWCHGBKRPSMNTSMS | Nw Cb Representment Jeanie Sms |
| FEE | FMASTRONWCHGBKRPSMNTSMS | Nw Cb Representment Maestro |
| FEE | FSTARNWCHGBKRPSMNTSMS | Nw Cb Representment Star Sms |
| FEE | FSTARNWXCPTNRESPSMS | Nw Exception Resp Fee Star Sms |
| FEE | FINTLNKRETRFLFLMNT | Nw Retr Fulfillment Interlink |
| FEE | FONERTOPEN | Onerate Open |
| FEE | FPZYAPIFRDMNTH | Payeezy Api Fraud Monthly Fee |
| FEE | FPZYAPIFRDSTUP | Payeezy Api Fraud Setup Fee |
| FEE | FPZYAPIFRDTXN | Payeezy Api Fraud Trans Fee |
| FEE | FPCARDLVLIIIACTVTN | Pcard Level Iii Activation Fee |
| FEE | FPCARDLVLIIIMOPRMID | Pcard Level Iii Mo Fee Per Mid |
| FEE | FPINSIGCRDRETTXN | Pin/Sig/Credit Ret Trans Fee |
| FEE | FRBTPROMO | Rebate Promo |
| FEE | FROUTERMMNTH | Router Monthly Fee |
| FEE | FSARATOGAENDPT | Saratoga Endpoint |
| FEE | FSBA | Sba Fee |
| FEE | FSTLMNTADJM3O | Settlement Adjustment |
| FEE | FSMOUTLET | Sm Outlet Fee |
| FEE | FSSTSUPRT | Sst Support Fee |
| FEE | FSVCARDLOCTNSETUP | Sv Card Location Set Up Fee |
| FEE | FSVCARDPERLOCTN | Sv Card Per Location |
| FEE | FTCHPYACTVTN | Touchpay Activation Fee |
| FEE | FTCHPYAUTH | Touchpay Auth Fee |
| FEE | FTCHPYMNTHPERMID | Touchpay Monthly Fee Per Mid |
| FEE | FUPIAUTH | Upi Authorization Fee |
| FEE | FUPIRTNDSCNT | Upi Return Discount Fee |
| FEE | FUPIRTNTXN | Upi Return Transaction Fee |
| FEE | FUPISLSDSCNT | Upi Sales Discount Fee |
| FEE | FUPISLSTXN | Upi Sales Transaction Fee |
| FEE | FUPISVC | Upi Service Fee |
| FEE | FVLTACTVTN | Vault Activation Fee |
| FEE | FVLTMNTHPERCRDHLDR | Vault Monthly Fee Per Cardhldr |
| FEE | FVIRPYMNTH | Virtualpay Monthly Fee |
| FEE | FACRETRMNLBILLING | Acre Terminal Billing Fee |
| FEE | FACSETRMNLBILLING | Acse Terminal Billing Fee |
| FEE | FADAPTRMNLBILLING | Adap Terminal Billing Fee |
| FEE | FADDLTRMNLBILLING | Addl Terminal Billing Fee |
| FEE | FAMXAPRVLCDNONNUM | Amex Approval Code Nonnum |
| FEE | FAMXAPRVLCDWRNGLNG | Amex Approval Code Wrong Lng |
| FEE | FAMXTXNINVLD | Amex Transaction Invalid |
| FEE | FAMXEXCSVCHGBK | Amex Excessive Charbk Fee |
| FEE | FTELNMACAUTHHDC | Tellan Mac Auth Hdc |
| FEE | FADJPAYTOAMI | Adjustment Pay To Ami |
| FEE | FADJPAYFRMRCH | Adjustment Pay From Merchant |
| FEE | FANSTRMNLBILL | Anst Terminal Billing Fee |
| FEE | FCLVRSTN | Clover Station |
| FEE | FAPMINIT | Apm Initiation |
| FEE | FAPMTXNSUCC | Apm Trxnsuccess |
| FEE | FAPMMIN | Apm Minimum Fee |
| FEE | FAPMRFND | Apm Refund Fee |
| FEE | FAPMCHGBK | Apm Chgbk Fee |
| FEE | FAPMEXTCHGBK | Apm Ext Chgbk |
| FEE | FAPMMNTH | Apm Monthly Fee |
| FEE | FAPMCHGBKADJ | Apm Chgbk Adj |
| FEE | FPAPITRMNLBILLING | Papi Terminal Billing Fee |
| FEE | FAPMFNDMISS | Apm Funds Miss |
| FEE | FAPMREJRFND | Apm Rej Refunds |
| FEE | FAPMFNDREC | Apm Funds Rec |
| FEE | FPAPYTRMNLBILLING | Papy Terminal Billing Fee |
| FEE | FSMLPMINIT | Sm Lpm Initiation |
| FEE | FSMLPMSUCC | Sm Lpm Success |
| FEE | FSMLPMRFND | Sm Lpm Refund |
| FEE | FSMLPMCHGBK | Sm Lpm Chgbk |
| FEE | FSMLPMEXTCB | Sm Lpm Ext Cb |
| FEE | FSMLPMPRC | Sm Lpm Process |
| FEE | FAQUATRMNLBILLING | Aqua Terminal Billing Fee |
| FEE | FCOGNBARCDPRNT | Cognitive Barcode Printer |
| FEE | FARGRTRMNLBILLING | Argr Terminal Billing Fee |
| FEE | FRESBMTACH | Resubmitted Ach |
| FEE | FTBLTPOSSYS | Tablet Point Of Sale System |
| FEE | FAUTOUPFRNTBILLING | Automated Upfront Billing |
| FEE | FFD40CLVRUS | Fd40 Clover Us |
| FEE | FCLVRSCALE | Clover Weight Scale |
| FEE | FKCHNPPRNTRASNCHR | Kitchen Prtr Asian Chr |
| FEE | FA421TRMNLBILLING | A421 Terminal Billing Fee |
| FEE | FBATPTRMNLBILLING | Batp Terminal Billing Fee |
| FEE | FCLVRGOEMVNFCRDR | Clovrgo Emv Nfc Rdr |
| FEE | FBEMSTRMNLBILLING | Bems Terminal Billing Fee |
| FEE | FBERSTRMNLBILLING | Bers Terminal Billing Fee |
| FEE | FBLDRTRMNLBILLING | Bldr Terminal Billing Fee |
| FEE | FBLR2TRMNLBILLING | Blr2 Terminal Billing Fee |
| FEE | FBTNLSSHNDSTBILLING | Buttonless Handset Billing |
| FEE | FBYPSMSTRKEY | Bypass Masterkey |
| FEE | FBYPSMSTRKEYCD | Bypass Masterkey Cd |
| FEE | FBYPSPREACTVD | Bypass Preactivated |
| FEE | FAMXICMBL | Amer Exp Interchange Mobile |
| FEE | FFLEETCORIC | Fleetcor Intrchg Fee |
| FEE | FMCICMOB | Mc Interchange Fee Mobile |
| FEE | FBPIITRMNLBILLING | Bpii Terminal Billing Fee |
| FEE | FDISCICMOB | Discover Interchange Mobile |
| FEE | FUNFNDPREPDCASHCARDIC | Unfund Prepd Cash Card Intrchg |
| FEE | FBPMRTRMNLBILLING | Bpmr Terminal Billing Fee |
| FEE | FFUELMNADJ | Fuelman Adjustment |
| FEE | FFUELMNIC | Fuelman Interchange Fee |
| FEE | FVIBPICMOB | Bp Visa Interchange Mobile |
| FEE | FBPCARDICMOB | Bp Card Interchange Mobile |
| FEE | FVIICMOB | Visa Interchange Fee Mobile |
| FEE | FLNKPTWRLSPDA7 | Linkpoint Wireless Pda 7 |
| FEE | FPFRPLCMTBRNZ | Preferred Placement Brnz |
| FEE | FVERISIGNGTWY | Verisign Gateway Fee |
| FEE | FPFLLNKRECBILL | Payflow Link Rec Bill |
| FEE | FPFLPRORECBILL | Payflow Pro Rec Bill |
| FEE | FVERISIGNFRAUDADV | Verisign Fraud Adv |
| FEE | FVERISIGNFRAUDBA | Verisign Fraud Ba |
| FEE | FVERISIGNFRAUDAM | Verisign Fraud Am |
| FEE | FVERISIGNLNK | Verisign Link |
| FEE | FEWRKSXLSMTCLKTI | Eworks!Xl Smartclicks Tier I |
| FEE | FEWRKSXLSMTCLKTII | Eworks!Xl Smartclicks Tier Ii |
| FEE | FEWRKSXLSMTCLKTIII | Eworks!Xl Smartclicks Tier Iii |
| FEE | FVOLNTNL | Vol National |
| FEE | FQKPGTLDLCLPKG | Quickpage Tld Local Package |
| FEE | FEWRKSXLECOM | Eworks!Xl W/Ecomm |
| FEE | FEWRKSXLECOMSCLKI | Eworks!Xl W/Ecomm S Clicks I |
| FEE | FEWRKSXLECOMSCLKII | Eworks!Xl W/Ecomm S Clicks Ii |
| FEE | FEWRKSXLECOMSCLKIII | Eworks!Xl W/Ecomm S Clicks Iii |
| FEE | FEFSNETGTWYSETUP | Efsnet Gateway Set Up Fee |
| FEE | FCSTMVOLNTNL | Custom Vol National |
| FEE | FCSTMVOLLCL | Custom Vol Local |
| FEE | FEWRKSXLSMTCLK50 | Eworks! Xl Smartclicks50 |
| FEE | FEWRKSXLSMTCLKII50 | Eworks! Xl Smartclicksii 50 |
| FEE | FVOLSMTCLK50 | Vol Smartclicks50 |
| FEE | FVOLSMTCLKII50 | Vol Smartclicksii 50 |
| FEE | FB8ANTRMNLBILLING | B8An Terminal Billing Fee |
| FEE | FDATACARD640 | Datacard 640 |
| FEE | FCSHRGSTRBILLING | Cash Register Billing |
| FEE | FHPCASHTRAYXTRA | Hp Cash Tray Extra |
| FEE | FCBCYTRMNLBILLING | Cbcy Terminal Billing Fee |
| FEE | FCBHVTRMNLBILLING | Cbhv Terminal Billing Fee |
| FEE | FCBOOTRMNLBILLING | Cboo Terminal Billing Fee |
| FEE | FSPLTPRINPRTTRNZ232 | Splitter Prin Prt Trnz232 |
| FEE | FCB25TRMNLBILLING | Cb25 Terminal Billing Fee |
| FEE | FCB90TRMNLBILLING | Cb90 Terminal Billing Fee |
| FEE | FVFP200 | Vf P200 |
| FEE | FCDMATRMNLBILLING | Cdma Terminal Billing Fee |
| FEE | FNURIT3010CDPDTRMNL | Nurit 3010 Cdpd Terminal Fee |
| FEE | FCDV1TRMNLBILLING | Cdv1 Terminal Billing Fee |
| FEE | FCLCTNFINADJ | Collections Financial Adj |
| FEE | FCFPPTRMNLBILLING | Cfpp Terminal Billing Fee |
| FEE | FCLVRGONFCSTND | Clover Go Nfc Stand |
| FEE | FCHKTRMNLBILLING | Chek Terminal Billing Fee |
| FEE | FCKMTTRMNLBILLING | Ckmt Terminal Billing Fee |
| FEE | FABADDACHNGNTC | Aba Dda Change Notice Fee |
| FEE | FCLVRMINI2SRTRKT | Clover Mini 2 Starterkit |
| FEE | FCLVRMINI2PINSHLD | Clover Mini 2 Pin Shield |
| FEE | FTRVALAMXDIS | True Value Amex/Disc Fees |
| FEE | FCTRAMT | Cotter Amounts |
| FEE | FCOVRTRMNLBILLING | Covr Terminal Billing Fee |
| FEE | FCPATRMNLBILLING | Cpa Terminal Billing Fee |
| FEE | FDRCTDATACHKRDR | Direct Data Check Reader |
| FEE | FGOPCCHRG | Go Pc Charge |
| FEE | FSRCNMR1000CHKRDR | Soricon Mr1000 Check Reader |
| FEE | FCR10TRMNLBILLING | Cr10 Terminal Billing Fee |
| FEE | FECR | Ecr Fee |
| FEE | FNURIT3010CELTRXXPL | Nurit 3010 Cel Trex Expel Fee |
| FEE | FHYPCMCT6BILLING | Hypercom Ct6 Billing |
| FEE | FCV1ETRMNLBILLING | Cv1E Terminal Billing Fee |
| FEE | FCTZNRLPRNTR | Citizen Roll Printer |
| FEE | FC0NTTRMNLBILLING | C0Nt Terminal Billing Fee |
| FEE | FBPPRTCPTN | Bp Participation Fee |
| FEE | FBPOUTOFNTWK | Bp Out Of Network Fee |
| FEE | FBPMKTRBTAMT | Bp Marketer Rebate Amount |
| FEE | FC100TRMNL | C100 Terminal |
| FEE | FIVIFLASHENCTR400 | Ivi Flash/Encounter 400 |
| FEE | FPYMT1000CUSTDISP | Paymate 1000 Customer Display |
| FEE | FCTZN560PRNT | Citizen 560 Printer |
| FEE | FC562TRMNLBILLING | C562 Terminal Billing Fee |
| FEE | FCLVRMOBWIFIONLY | Clover Mobile Wi Fi Only |
| FEE | FPYMT1000CASHDRWR | Paymate 1000 Cash Drawer |
| FEE | FCLVRMOBDCK | Clover Mobile Dock |
| FEE | FCLVRMOBPRNT | Clover Mobile Printer |
| FEE | FMNTHWITHECP | Monthly Fee With Ecp |
| FEE | FMNTHECPCHKCON | Mthly Fee With Ecp And Chk Con |
| FEE | FMTHWDACCRECVEMLINV | Mth Fee Wd Acc Recv/Email Inv |
| FEE | FMTHWDACCRECEMLINVACH | Mth Fee Wd Acc Rec/Eml Inv/Ach |
| FEE | FMNTHWITHCOMMSAFE | Mthly Fee With Commerce Safe |
| FEE | FMNTHWITHACCPYBL | Mthly Fee With Acc Payable |
| FEE | FMNTHFLATA | Monthly Flat Fee A |
| FEE | FVFV200CPLUS | Vf V200C Plus |
| FEE | FVFV400CPLUS | Vf V400C Plus |
| FEE | FDATCAPCASHREGBILL | Datacap Cash Regstr Bill |
| FEE | FNURIT2070TDCTRMNLBILLING | Nurit 2070 Tdc Terminal Bill |
| FEE | FDCSPPIIPINPAD | Dc Sppii Pinpad |
| FEE | FDATACARDDBT | Datacard Debit |
| FEE | FDATACARD860ITMNL | Datacard 860I Terminal |
| FEE | FDGRDTRMNLBILLING | Dgrd Terminal Billing Fee |
| FEE | FDISPTRMNLBILLING | Disp Terminal Billing Fee |
| FEE | FDLICTRMNLBILLING | Dlic Terminal Billing Fee |
| FEE | FDRAWTRMNLBILLING | Draw Terminal Billing Fee |
| FEE | FDRWRTRMNLBILLING | Drwr Terminal Billing Fee |
| FEE | FDISCNTREV | Discount Revenue |
| FEE | FDSPPTRMNLBILLING | Dspp Terminal Billing |
| FEE | FATACARD680ST | Datacard 680 St |
| FEE | FFEDBUWADJ | Federal Buw Adjustment |
| FEE | FSTATEBUWADJ | State Buw Adjustment |
| FEE | FFEDOSTNDOBLGOVRD | Fed Outstndng Oblg Override |
| FEE | FSTATEOSTNDOBLGOVRD | State Outstndng Oblg Override |
| FEE | FNDCTXN | Ndc Transaction Fee |
| FEE | FNDCADDRVER | Ndc Address Verification Fee |
| FEE | FCHKSVCADJREV | Check Services Fee Adj/Rev |
| FEE | FIMPRNPUR | Imprinter Purchase |
| FEE | FPCLEASES | Pc Lease Fees |
| FEE | FMDMRNTL | Modem Rental Fee |
| FEE | FNDCHLPDSK | Ndc Help Desk Fee |
| FEE | FPHNTRNG | Phone Training |
| FEE | FTRMNLPROGCHRG | Terminal Programming Charge |
| FEE | FVIBLBKRBT | Visa Billback Rebates |
| FEE | FNDCMLNGCHRG | Ndc Mailing Charge |
| FEE | FRPRTADJREV | Report Fee Adj/Rev |
| FEE | FTENCUSTSETUPMDL | Ten Customer Set Up Module Fee |
| FEE | FCSTMDTMAP | Custom Data Mapping |
| FEE | FADJMGMT | Adjustment Of Management Fee |
| FEE | FDBTCARDMINADJREV | Debit Card Min Fee Adj/Rev |
| FEE | FDBTNTWKSETUP | Debit Network Setup Fee |
| FEE | FENCRPT | Encryption Fee |
| FEE | FMINFORCLSDLOC | Min Fee For Closed Locations |
| FEE | FTRAINING | Training Fee |
| FEE | FPRGMING | Programming Fee |
| FEE | FAGNTBNKSTLMNT | Agent Bank Settlement |
| FEE | FCASHADVRBT | Cash Advance Rebate |
| FEE | FCOSTFUND | Cost Of Funds |
| FEE | FDBTINVSTTIME | Debit For Investment Time |
| FEE | FRVRSPRFT | Reverse Profitability |
| FEE | FDPSTFNDINERR | Deposit Funded In Error |
| FEE | FREVDUPDPST | Reverse Duplicate Deposit |
| FEE | FCHKNVRRCVD | Check Never Received |
| FEE | FRPLCMNTLSTCHK | Replacement Of Lost Check |
| FEE | FCLCTNLTR | Collection Letter |
| FEE | FMSPSTTXN | Misposted Transactions |
| FEE | FCRISNGBNKCHK | Credit For Issuing Bank Check |
| FEE | FCRQRTRLYADJCHRG | Credit For Quarterly Adj Chrge |
| FEE | FDIFFGRS | Difference In Gross |
| FEE | FDUPCR | Duplicate Credit |
| FEE | FMRCHCRERR | Merchant Credited In Error |
| FEE | FMRCHDBTERR | Merchant Debited In Error |
| FEE | FOVRPMT | Overpayment |
| FEE | FPYMTERR | Payment Error |
| FEE | FPRCONVCHGBK | Pre Conversion Chargeback |
| FEE | FFLTS | Float Fees |
| FEE | FAGTBNKRBT | Agent Bank Rebate |
| FEE | FIMPRNPLTPLSTC | Imprinter Plate/Plastic Fee |
| FEE | FEQPSHPCHRG | Equipment Shipping Charge |
| FEE | FFLEETONEDBTCARDDPST | Fleet One Debit Card Deposits |
| FEE | FFLEETONEDBTCARDADJ | Fleet One Debit Card Adj |
| FEE | FSTRDVALDPST | Stored Value Deposits |
| FEE | FSTRDVALADJS | Stored Value Adjustments |
| FEE | FDBTCARDCHGBK | Debit Card Chargeback |
| FEE | FDBTCARDCHGBKREV | Debit Card Chargeback Reversal |
| FEE | FWEXSTLMNTADJ | Wex Settlement Adjustment |
| FEE | FELECCASHREGBILL | Electronic Cash Regstr Bill |
| FEE | FEH33TRMNLBILLING | Eh33 Terminal Billing Fee |
| FEE | FSMSNG24INCHKSK | Samsung 24 Inch Kiosk |
| FEE | FSMSNGKSKBASE | Samsung Kiosk Base |
| FEE | FELICTRMNLBILLING | Elic Terminal Billing Fee |
| FEE | FENTCH3100 | En Touch 3100 |
| FEE | FEPPPTRMNLBILLING | Eppp Terminal Billing Fee |
| FEE | FSLSTAXONEQPPUR | Sales Tax On Equipment Purch |
| FEE | FESEEKSCNRP | E Seek Scanner With Out P |
| FEE | FRCHFIN | Reach Financial |
| FEE | FFTRCASHADVPVDR1 | Future Cash Advance Provider 1 |
| FEE | FFTRCASHADVPVDR2 | Future Cash Advance Provider 2 |
| FEE | FFTRCASHADVPVDR3 | Future Cash Advance Provider 3 |
| FEE | FCHNFNDNOTFEML | Chn Funding Notification Email |
| FEE | FCHNFNDNOTFFAX | Chn Funding Notification Fax |
| FEE | FCHNFNDNOTFML | Chn Funding Notification Mail |
| FEE | FFDMMPIITRMNLBILLING | Fdm Mpii Terminal Billing Fee |
| FEE | FFD10TRMNLBILLING | Fd10 Terminal Billing Fee |
| FEE | FFD200TRMNLBILLING | Fd 200 Terminal Billing Fee |
| FEE | FFEITTRMNLBILLING | Feit Terminal Billing Fee |
| FEE | FFTJ2TRMNLBILLING | Ftj2 Terminal Billing Fee |
| FEE | FFNDNOTFEML | Funding Notification Email Fee |
| FEE | FFNDNOTFML | Funding Notification Mail Fee |
| FEE | FFOC4TRMNLBILLING | Foc4 Terminal Billing Fee |
| FEE | FFODOTRMNLBILLING | Fodo Terminal Billing Fee |
| FEE | FENVFTPJR | Envoy Ftpjr |
| FEE | FFASTRC | Fastrac Fee |
| FEE | FENVFTP2 | Envoy Ftp2 |
| FEE | FFLEETTAXMRCHCR | Fleet Tax Merchant Credit |
| FEE | FFLEETTAXMRCHDB | Fleet Tax Merchant Debit |
| FEE | FFLEETTAXMRCHCRREV | Fleet Tax Merchant Credit Rev |
| FEE | FFLEETTAXMRCHDBREV | Fleet Tax Merchant Debit Rev |
| FEE | FFUJICASHRGTRBILL | Fuji Cash Register Bill |
| FEE | FTCKICMISC | Telecheck Interchange/Misc Fee |
| FEE | FTPGCHKRDRWIMG | Tpg Check Rdr W/ Imaging |
| FEE | FGEN1TRMNLBILLING | Gen1 Terminal Billing Fee |
| FEE | FGE65TRMNLBILLING | Ge65 Terminal Billing Fee |
| FEE | FGILGTRMNLBILLING | Gilg Terminal Billing Fee |
| FEE | FGPRSTRMNLBILLING | Gprs Terminal Billing Fee |
| FEE | FNURITGPRSPCIM50 | Nurit 8000 Gprs Pci M50 |
| FEE | FGRDRTRMNLBILLING | Grdr Terminal Billing Fee |
| FEE | FWDCRDSWPMAG | Wedge Crd Swp Redr Mag21040145 |
| FEE | FGCSTNDCRDSMPPCK | Gc Standard Card Sample Pack |
| FEE | FGCSHP | Gc Shipping |
| FEE | FPEGFTCRDGO500PKG | Pe Gift Card To Go 500 Package |
| FEE | FPECSTMTOGOPKG | Pe Custom To Go Package |
| FEE | FLYLTGO250PKG | Pe Loyalty To Go 250 Package |
| FEE | FPEGFTCRDGO100PKG | Pe Gift Card To Go 100 Package |
| FEE | FGCHNDSLSTAX | Gc Handling Sales Tax |
| FEE | FGCSVCTAX | Gc Service Tax |
| FEE | FTELNPCHUB10PKHDC | Tellan Pc Hub 10 Pk Hdc |
| FEE | FNURIT2080HDCTRMLBILLING | Nurit 2080 Hdc Terminal Bill |
| FEE | FNURIT2085HDCTRMLBILLING | Nurit 2085 Hdc Terminal Bill |
| FEE | FHYPRCOMT77GQF | Hypercom T77Gq F |
| FEE | FHYPRCOMT77GT | Hypercom T77G T |
| FEE | FTELNPCHUB20PKHDC | Tellan Pc Hub 20 Pk Hdc |
| FEE | FHNDSTBILL | Handset Billing |
| FEE | FHLDTRMNLBILLING | Hold Terminal Billing Fee |
| FEE | FHOOSTRMNLBILLING | Hoos Terminal Billing Fee |
| FEE | FHPTHRMRCPPRNTR | Hp Therma, Receipt Prntr |
| FEE | FHYPRCOM5700RED | Hypercom 5700+ Red |
| FEE | FHRGRTRMNLBILLING | Hrgr Terminal Billing Fee |
| FEE | FHS4MTRMNLBILLING | Hs4M Terminal Billing Fee |
| FEE | FPCHUBBILL | Pc Hub Billing |
| FEE | FTELNPCHUB2PKTDC | Tellan Pc Hub 2 Pk Tdc |
| FEE | FTELNPCHUB5PKTDC | Tellan Pc Hub 5 Pk Tdc |
| FEE | FHYPRCOMCT4BILL | Hypercom Ct4 Billing |
| FEE | FHYP4TRMNLBILLING | Hyp4 Terminal Billing Fee |
| FEE | FMONDLTRN | Monthly Dialtran Fee |
| FEE | FMONIPTXN | Monthly Ip Tran Fee |
| FEE | FCASIO1 | Casio 1 Fee (One Time Fee) |
| FEE | FSTRFRNTOVRG | Store Front Overage |
| FEE | FCRS1 | Crs 1 Fee (One Time Fee) |
| FEE | FCRS2 | Crs 2 Fee (One Time Fee) |
| FEE | FHYPRCOMP1300 | Hypercom P1300 |
| FEE | FH4STTRMNLBILLING | H4St Terminal Billing Fee |
| FEE | FIBMCASHRGSTRBILL | Ibm Cash Regstr Bill |
| FEE | FICVFYCONV | Ic Verify Conversion |
| FEE | FICTLTRMNLBILLING | Ictl Terminal Billing |
| FEE | FIDSETRMNLBILLING | Idse Terminal Billing Fee |
| FEE | FIICETRMNLBILLING | Iice Terminal Billing Fee |
| FEE | FILLSTMNLB | Ills Terminal Billing Fee |
| FEE | FILPFTRMNLBILLING | Ilpf Terminal Billing Fee |
| FEE | FINT2TRMNLBILLING | Int2 Terminal Billing Fee |
| FEE | FIOSKTRMNLBILLING | Iosk Terminal Billing Fee |
| FEE | FPINPADMAG | Pin Pad, Mag30050200 |
| FEE | FIPJKTRMNLBILLING | Ipjk Terminal Billing Fee |
| FEE | FECLPSEPMTTRMNL | Eclipse Payment Terminal |
| FEE | FIVIMR2300CHKRDR | Ivi Mr2300 Checkreader |
| FEE | FISTNTRMNLBILLING | Istn Terminal Billing Fee |
| FEE | FIVELTRMNLBILLING | Ivel Terminal Billing Fee |
| FEE | FIV6MTRMNLBILLING | Iv6M Terminal Billing Fee |
| FEE | FI01TRMNLBILLING | I01 Terminal Billing Fee |
| FEE | FI02TRMNLBILLING | I02 Terminal Billing Fee |
| FEE | FI03TRMNLBILLING | I03 Terminal Billing Fee |
| FEE | FI04TRMNLBILLING | I04 Terminal Billing Fee |
| FEE | FI05TRMNLBILLING | I05 Terminal Billing Fee |
| FEE | FI06TRMNLBILLING | I06 Terminal Billing Fee |
| FEE | FI07TRMNLBILLING | I07 Terminal Billing Fee |
| FEE | FI10TRMNLBILLING | I10 Terminal Billing Fee |
| FEE | FI11TRMNLBILLING | I11 Terminal Billing Fee |
| FEE | FI301TRMNLBILLING | I301 Terminal Billing |
| FEE | FOTI5000TRMNLBILLING | Oti 5000 Terminal Billing |
| FEE | FI510TRMNLBILLING | I510 Terminal Billing Fee |
| FEE | FJIFFYLUBEBILL | Jiffy Lube Billing Fee |
| FEE | FJRDATRMNLBILLING | Jrda Terminal Billing Fee |
| FEE | FJTIPTRMNLBILLING | Jtip Terminal Billing Fee |
| FEE | FBNKPNTIIPPAD | Bankpoint Ii Pin Pad |
| FEE | FKIPRTRMNLBILLING | Kipr Terminal Billing Fee |
| FEE | FKPNTTRMNLBILLING | Kpnt Terminal Billing |
| FEE | FVISTRTPRCSNG | Vi Straight Through Processing |
| FEE | FDSCVPRTCPTN | Discover Participation Fee |
| FEE | FUKSPLTFNDHLDBK | Uk Split Funding Holdback |
| FEE | FUKSPLTFNDPBK | Uk Split Funding Payback |
| FEE | FCLVRHUB | Clover Hub |
| FEE | FEQPRPMTCHRG | Equipment Replacement Charge |
| FEE | FTELNPCHUB2PKHDC | Tellan Pc Hub 2Pk Hdc |
| FEE | FLMAN3010MOTTMNL | Lipman 3010 Motient Terminal |
| FEE | FLGCPLEDSPLRCK | Logic Pole Display Rack |
| FEE | FLPXQTRMNLBILLING | Lpxq Terminal Billing Fee |
| FEE | FCLVRGONFCRDRCLP | Clvr Go Nfc Reader Clip Bndl |
| FEE | FCLVRGONFCRDRDCKCLP | Clvr Go Nfc Rdr Dock Clip Bndl |
| FEE | FLSOFTRMNLBILLING | Lsof Terminal Billing Fee |
| FEE | FLUSWRPOS50CELL | L/Uswire Pos 50 Cellular |
| FEE | FCLVRGONFCRDRDCK | Clvr Go Nfc Reader Dock Bndl |
| FEE | FVBVSETUP | Vbv Setup Fee |
| FEE | FVIVBVTXN | Vbv Visa Trans Fee |
| FEE | FTCKONLNMNTHUSG | Tck Online Mthly Usage Fee |
| FEE | FTCKONLNTXN | Tck Online Trans Fee |
| FEE | FTCKONLNRETITM | Tck Online Return Item Fee |
| FEE | FTCKONLNINACTSITE | Tck Online Inactive Site Fee |
| FEE | FTCKONLNDISC | Tck Online Discount Fee |
| FEE | FLNKSHIELD1SETUP | Linkshield 1 Setup Fee |
| FEE | FLNKSHIELD1MNTH | Linkshield 1 Monthly Usage |
| FEE | FLNKSHIELD1TXN | Linkshield 1 Trans Fee |
| FEE | FLNKSHIELD2SETUP | Linkshield 2 Setup Fee |
| FEE | FLNKSHIELD2MNTH | Linkshield 2 Monthly Usage |
| FEE | FLNKSHIELD2TXN | Linkshield 2 Trans Fee |
| FEE | FLNKSHIELD3TXN | Linkshield 3 Trans Fee |
| FEE | FGTWYPPLTXN | Gateway Paypal Trx Fee |
| FEE | FGTWYBMLTXN | Gateway Bill Me Later Trx Fee |
| FEE | FGTWYGGLTXN | Gateway Google Trx Fee |
| FEE | FFTRLNKPT2TXN | Future Linkpt2 Trans Fee |
| FEE | FFTRLNKPT3SETUP | Future Linkpt3 Setup Fee |
| FEE | FFTRLNKPT3MNTH | Future Linkpt3 Monthly Usage |
| FEE | FFTRLNKPT3TXN | Future Linkpt3 Trans Fee |
| FEE | FFTRLNKPT4SETUP | Future Linkpt4 Setup Fee |
| FEE | FFRAUDSVCSETUP | Fraud Services Setup Fee M |
| FEE | FFRAUDSVCTXN | Fraud Services Trans Fee M |
| FEE | FMRKTKTPURCHDISC | Marketing Kit Purch Discount |
| FEE | FMRKTKTPTBALMESS | Marketing Kit Pts Bal Mess |
| FEE | FLYLTSTLSETUP | Loyalty Settle Set Up Fee |
| FEE | FLYLTSTLACHTXN | Loyalty Settle Ach Trans |
| FEE | FLYLTSTLLOC | Loyalty Settle Location |
| FEE | FLYLTREGCHK | Loyalty Registration Check |
| FEE | FMAC5TRMNLBILLING | Mac5 Terminal Billing Fee |
| FEE | FPERDPBCHSVC | Personal Dp Batch Services |
| FEE | FGMNGAPP | Gaming Application |
| FEE | FMAGTTRMNLBILLING | Magt Terminal Billing Fee |
| FEE | FNTWKTKNSVC | Network Token Services |
| FEE | FMAPP100LBILL | Mapp 100L Billing |
| FEE | FSDSPRC | Sds Processing Fee |
| FEE | FMBRNTRMNLBILLING | Mbrn Terminal Billing Fee |
| FEE | FTELNMACAUTHTDC | Tellan Mac Auth Tdc |
| FEE | FSMPLTXNMCITMNL | Simple Tran Mci Terminal |
| FEE | FMGRMTRMNLBILLING | Mgrm Terminal Billing Fee |
| FEE | FMICVTRMNLBILLING | Micv Terminal Billing Fee |
| FEE | FTELNPCHUB10PKTDC | Tellan Pc Hub 10 Pk Tdc |
| FEE | FTELNPCMACHUB20PKHDC | Tellan Pc Mac Hub 20 Pk Hdc |
| FEE | FTELNPCMACHUB5PKHDC | Tellan Pc Mac Hub 5Pk Hdc |
| FEE | FTELNPCHUB20PKTDC | Tellan Pc Hub 20 Pk Tdc |
| FEE | FCMSTRMBPRPRNT | Comstar Mobilepro Printer |
| FEE | FCLVRSWVLSTNDFORMIN | Swivel Stand For Clover Mini |
| FEE | FMOPATRMNLBILLING | Mopa Terminal Billing Fee |
| FEE | FNURIT3010MBTXTRMNL | Nurit 3010 Mobitex Terminal |
| FEE | FMPMUTRMNLBILLING | Mpmu Terminal Billing Fee |
| FEE | FMPRTTRMNLBILLING | Mprt Terminal Billing Fee |
| FEE | FMPUSTRMNLBILLING | Mpus Terminal Billing Fee |
| FEE | FMT01TRMNLBILLING | Mt01 Terminal Billing Fee |
| FEE | FUNAPRVCRDTXN | Unapproved Card Trans |
| FEE | FMWORTRMNLBILLING | Mwor Terminal Billing Fee |
| FEE | FEBTATHSWITCHS | Ebt Ath Switch Fees |
| FEE | FAMXSVCADJ | Amex Full Service Fee/Adj |
| FEE | FADJAOLWO | Adjustment Aolwo |
| FEE | FADJCOLWO | Adjustment Colwo |
| FEE | FSFTWR | Software |
| FEE | FEQPLEASE | Equipment Lease Fee |
| FEE | FPROGSYSCHNG | Programming System Change |
| FEE | FRAPPLDD | Reapplied Dd |
| FEE | FRETCARD | Returned Credit |
| FEE | FCONTRSGNBNS | Contractual Signing Bonus |
| FEE | FCUSTRBT | Customer Rebate |
| FEE | FCRSSRDMP | Cross Redemption |
| FEE | FVOYADJ | Voyager Adjustment |
| FEE | FRESDLPYMNT | Residual Payment |
| FEE | FMSTRCHGBKREVCR | Maestro Chargeback Reversal Cr |
| FEE | FMSTRCHGBKCR | Maestro Chargeback Credit |
| FEE | FMINANNUALSRTFALL | Minimum Annual Short Fall |
| FEE | FPYMNT1 | Payment 1 |
| FEE | FRCLMDFND | Reclaimed Funds |
| FEE | FMCNOAUTHREV | No Auth Reversal Of Mc Fee |
| FEE | FCMPLNC | Compliance Fee |
| FEE | FLTR | Letter Fee |
| FEE | FNONPMTDRCTDBT | Non Payment Of Direct Debit |
| FEE | FOPRGDNCE | Operational Guidance Fee |
| FEE | FCLCTN | Collections Fee |
| FEE | FMGMT | Management Fee |
| FEE | FVATTRMNLADJ | Vat Terminal Fee Adjustment |
| FEE | FSRTTERMTMNLRNTL | Short Term Terminal Rental Fee |
| FEE | FNEGWHADJ | Negative Warehouse Adjustment |
| FEE | FAMXBLBK | Amex Billback Fee |
| FEE | FRSRCH | Research Fee |
| FEE | FSUSPCLR | Suspense Clearance |
| FEE | FAPMMISCADJCR | Apm Misc Adj Cr |
| FEE | FPROFSVC | Professional Services Fee |
| FEE | FADDLMNGDSVC | Additional Managed Servces Fee |
| FEE | FDEPSTFNDERR | Deposit Funded In Error |
| FEE | FSMLPMMSADJDR | Sm Lpm Msadj Dr |
| FEE | FSMLPMMSADJCR | Sm Lpm Msadj Cr |
| FEE | FMNLAVS | Manual Avs |
| FEE | FMERCRDEDERR | Merchant Credited In Error |
| FEE | FWCNSTLMNTCR | Wicon Settlement Credit |
| FEE | FCASHCARDMNLADJS | Cash Card Manual Adjustments |
| FEE | FCNPADMN | Card Not Present Admin Fee |
| FEE | FREVLNMNYMISCADJ | Revolution Money Misc Adj Fee |
| FEE | FLYLTWBSTHOST | Loyalty Website Hosting |
| FEE | FLYLTWBSTDEV | Loyalty Website Dev/Graphics |
| FEE | FLYLTPGRMCONSLT | Loyalty Program Consultation |
| FEE | FLYLTDTEXTRCTS | Loyalty Data Extracts |
| FEE | FLYLTCSTMRPRT | Loyalty Custom Reporting |
| FEE | FLYLTDATANALYTICS | Loyalty Data Analytics |
| FEE | FLYLTCSTMPLTFMPRGMM | Loyalty Custom Platform Pgming |
| FEE | FSMLPMADJRVDR | Sm Lpm Adjrv Dr |
| FEE | FSMLPMADJRVCR | Sm Lpm Adjrv Cr |
| FEE | FVIDISCNTADJREV | Visa Discount Fee Adj/Rev |
| FEE | FREJRBT | Reject Fee Rebate |
| FEE | FWRLSRBT | Wireless Fee Rebate |
| FEE | FDDACHNGRBT | Dda Change Fee Rebate |
| FEE | FMRCHCLUBRBT | Merchant Club Fee Rebate |
| FEE | FRINSTMTRBT | Reinstatement Fee Rebate |
| FEE | FCUSTSVCRBT | Customer Service Fee Rebate |
| FEE | FNSFRBT | Nsf Fee Rebate |
| FEE | FMLEDSTMTRBT | Mailed Statement Fee Rebate |
| FEE | FVIRCHKRBT | Virtual Check Fee Rebate |
| FEE | FACCTCLSRRBT | Account Closure Fee Rebate |
| FEE | FDISCRTQLFDWRNG | Disc Rate Qualified Wrong Rate |
| FEE | FTXNRBT | Transaction Fee Rebate |
| FEE | FTCKBASXRBT | Basx Telecheck Rebate |
| FEE | FDUPRBT | Duplication Fee Rebate |
| FEE | FFRAUDRBT | Fraud Fee Rebate |
| FEE | FLPGRBT | Lpg Fee Rebate |
| FEE | FNONINSTLRBT | Non Install Rebate |
| FEE | FMISCRBTFRTXT | Misc Rebate Free Form Text |
| FEE | FNEWRTLACCT105RBT | New Retail Acct 105 Rebate |
| FEE | FDSCVBLBKRBT | Discover Billback Rebates |
| FEE | FVITXNADJREV | Visa Transaction Fee Adj/Rev |
| FEE | FMCTXNADJREV | Mastercard Trans Fee Adj/Rev |
| FEE | FDNRSDISNTCADJREV | Diners Discount Fee Adj/Rev |
| FEE | FDNRSTXNADJREV | Diners Transaction Fee Adj/Rev |
| FEE | FDSCVDISNTCADJREV | Discover Discount Fee Adj/Rev |
| FEE | FDSCVTXNADJREV | Discover Trans Fee Adj/Rev |
| FEE | FJCBDISNTCADJREV | Jcb Discount Fee Adj/Rev |
| FEE | FBPGFTCRDADJ | Bp Gift Card Adjustment |
| FEE | FEESFM6C | Fees |
| FEE | FPCINONCMPLNCRFND | Pci Non Compliance Fee Refund |
| FEE | FANNUALRFND | Annual Fee Refund |
| FEE | FJCBTXNADJREV | Jcb Transaction Fee Adj/Rev |
| FEE | FPVTLBLTXNADJREV | Private Label Tran Fee Adj/Rev |
| FEE | FRECALCDSCNT | Recalculation Of Discount Fee |
| FEE | FMCBLBKADJREV | Mc Billback Fee Adj/Rev |
| FEE | FHOSTDSCNT | Host Discounts |
| FEE | FHOSTDSCNTWLMRTMOB | Host Discount Walmart Mobile |
| FEE | FHOSTDSCNTSMTCRD | Host Discount Smartcard |
| FEE | FHOSTDSCNTSPRMSMTCRD | Host Discount Supreme Smartcrd |
| FEE | FVIASSMNTADJREV | Visa Assessment Fee Adj/Rev |
| FEE | FVIBLBKADJREV | Visa Billback Fee Adj/Rev |
| FEE | FILNKICADJREV | Interlink I/C Fee Adj/Rev |
| FEE | FSTARICADJREV | Star I/C Fee Adj/Rev |
| FEE | FSVCSTMDEV | Sv Custom Development Fee |
| FEE | FSVOTHPGM | Sv Other Program Fee |
| FEE | FSVCARDPRODCN | Sv Card Production Fee |
| FEE | FSVCARDPRODCNFRGHT | Sv Card Production Freight |
| FEE | FSVCARDDSTRBTN | Sv Card Distribution |
| FEE | FSVCARDDATAFLISS | Sv Card Data File Issuance Fee |
| FEE | FMCDSCNTRBT | M/C Discount Rebates |
| FEE | FNBNKCRDDSCNTRBT | Non Bank Card Discount Rebates |
| FEE | FTMNLRBT | Terminal Rebates |
| FEE | FMCIAUTHCALLS | Mci Authorization Calls |
| FEE | FMCIUNMTMIN | Mci Unmet Minimum Fee |
| FEE | FVOICEARC | Voice Arc Fee |
| FEE | FNONAUTHFINE | Non Auth Fine |
| FEE | FLEASELINEINSTL | Lease Line Installation Fee |
| FEE | FLEASELINERNTL | Lease Line Rental Fee |
| FEE | FAMERITECH | Ameritech Fee |
| FEE | FHYPRCOMNACEQPBILL | Hypercom Nac Eqpt Billing |
| FEE | FNTNLCHNGOFADDR | National Change Of Address |
| FEE | FSC500PPAD | Sc500 Pin Pad |
| FEE | FNG8TRMNLBILLING | Ng8 Terminal Billing Fee |
| FEE | FNURIT2060HDCTRMLBILLING | Nurit 2060 Hdc Term Bill Fee |
| FEE | FOMNI3750DCPPAD | Omni 3750Dc Pin Pad |
| FEE | FNI32TRMNLBILLING | Ni32 Terminal Billing Fee |
| FEE | FVFONEZONIITERM | Verifone Zon Ii Term |
| FEE | FNPFLTRMNLBILLING | Npfl Terminal Billing Fee |
| FEE | FGNRCPRNT | Generic Printer |
| FEE | FNPRMTRMNLBILLING | Nprm Terminal Billing Fee |
| FEE | FNTAGTRMNLBILLING | Ntag Terminal Billing Fee |
| FEE | FNURIT2060TDCTRMLBILLING | Nurit 2060 Tdc Term Bill Fee |
| FEE | FNURIT2060TRMNLBILLING | Nurit 2060 Terminal Billing |
| FEE | FNTR3TRMNLBILLING | Ntr3 Terminal Billing |
| FEE | FNURIT2070TRMNLBILLING | Nurit 2070 Terminal Billing |
| FEE | FNURIT2085TDCTRMLBILLING | Nurit 2085 Tdc Terminal Bill |
| FEE | FNURIT2090TRMNLBILLING | Nurit 2090 Terminal Billing |
| FEE | FNURIT2070HDCTRMLBILLING | Nurit 2070 Hdc Term Bill Fee |
| FEE | FNURIT8000DCKSTN | Nurit 8000 Docking Stn |
| FEE | FDRCTDBAUSTVAL | Directdb Austria Val |
| FEE | FDRCTDBAUSTREF | Directdb Austria Ref |
| FEE | FDRCTDBGERMVAL | Directdb Germany Val |
| FEE | FDRCTDBGERMSTL | Directdb Germany Stl |
| FEE | FDRCTDBGERMREF | Directdb Germany Ref |
| FEE | FDRCTDBNTHRLNDVAL | Directdb Netherlands Val |
| FEE | FDRCTDBNTHRLNDSTL | Directdb Netherlands Stl |
| FEE | FDRCTDBNTHRLNDREF | Directdb Netherlands Ref |
| FEE | FDRCTDBSPNVAL | Directdb Spain Val |
| FEE | FDRCTDBSPNSTL | Directdb Spain Stl |
| FEE | FDRCTDBSPNREF | Directdb Spain Ref |
| FEE | FDRCTDBUKVAL | Directdb Uk Val |
| FEE | FDRCTDBUKSTL | Directdb Uk Stl |
| FEE | FDRCTDBUKREF | Directdb Uk Ref |
| FEE | FDRCTDBUKMND | Directdb Uk Mnd |
| FEE | FCUPASSMT | Cup Assessment Fee |
| FEE | FCUPACQCLR | Cup Acquirer Clearing Fee |
| FEE | FCUPLCNSE | Cup License Fee |
| FEE | FUPAYAUTH | Union Pay Authorization |
| FEE | FVI3DS | Visa 3Ds Fee |
| FEE | FMCCANECOM | Mc Canada E Commerce Fee |
| FEE | FOCHKTRMNLBILLING | Ochk Terminal Billing Fee |
| FEE | FGST | Gst |
| FEE | FMCXBRDRNONSEPAINTRRB | Mc Xbrdr Non Sepa Inter Rb |
| FEE | FOECATRMNLBILLING | Oeca Terminal Billing Fee |
| FEE | FMCEUECOMDEV | Mc Eu E Commerce Dev Fee |
| FEE | FMCINTFNLAUTH | Mc Proc Integrity Final Auth |
| FEE | FMCINTUNDEFFNL | Mc Proc Intgrity Undef Final |
| FEE | FMCCAFLTRNSMSN | Mc Ca File Transmission Fee |
| FEE | FMCEUACQINTER | Mc Eu Acq Fee Inter |
| FEE | FMCEUACQINTRA | Mc Eu Acq Fee Dom/Intra |
| FEE | FMCASSMT | Mc Assessment |
| FEE | FMCEUFLTRNSMSN | Mc Eu File Transmission Fee |
| FEE | FMCPOSMICROPYMNTINTER | Mc Pos Micro Paym Inter |
| FEE | FMCPOSMICROPYMNTINTRA | Mc Pos Micro Paym Dom/Intra |
| FEE | FMCMIDPAYMINTER | Mc Mid Paym Tier Inter |
| FEE | FMCMIDPAYMINTRA | Mc Mid Paym Tier Dom/Intra |
| FEE | FMCMACROPAYMNTINTER | Mc Macro Paym Tier Inter |
| FEE | FMCMACROPAYMNTINTRA | Mc Macro Paym Tier Dom/Intra |
| FEE | FVIASSMNT | Visa Assessment Fee |
| FEE | FVICLRSETTLDOMINTRA | Visa Clr/Settl Fee Dom/Intra |
| FEE | FMCMINVOL | Mc Min Volume Fee |
| FEE | FVIASSMNTHST | Visa Assessment Fee Hst |
| FEE | FMCACQLCNSE | Mc Acquirer License Fee |
| FEE | FMCACQCNCTVTY | Mc Acquirer Connectivity Fee |
| FEE | FFXCMMSNRT | Fx Commission Rate |
| FEE | FOGRDTRMNLBILLING | Ogrd Terminal Billing Fee |
| FEE | FVIOMNIMSUSAUTHSYS | Omni Vi Misuse Auth System Fee |
| FEE | FVIAUTHEUDOM | Auth Visa Eu Domestic Fee |
| FEE | FVIAUTHEUINTRARGNL | Auth Visa Eu Intraregional Fee |
| FEE | FVIAUTHEUINTERRGNL | Auth Visa Eu Interregional Fee |
| FEE | FOMGCTRMNLBILLING | Omgc Terminal Billing Fee |
| FEE | FOMRNTRMNLBILLING | Omrn Terminal Billing |
| FEE | FOMNICANNTWKPRC | Omni Canada Ntwk Process Fee |
| FEE | FONT2TRMNLBILLING | Ont2 Terminal Billing Fee |
| FEE | FOPT4TRMNLBILLING | Opt4 Terminal Billing Fee |
| FEE | FOMNI3750TRMNL | Omni 3750 Terminal |
| FEE | FO396TRMNLBILLING | O396 Terminal Billing |
| FEE | FOMNI460TRMNL | Omni 460 Terminal |
| FEE | FOMNI470TRMNL | Omni 470 Terminal |
| FEE | FOMNI395TRMNL | Omni 395 Terminal |
| FEE | FPAIOTRMNLBILLING | Paio Terminal Billing Fee |
| FEE | FPAK0TRMNLBILLING | Pak0 Terminal Billing Fee |
| FEE | FPAPETRMNLBILLING | Pape Terminal Billing Fee |
| FEE | FPBAETRMNLBILLING | Pbae Terminal Billing Fee |
| FEE | FMSPOSCHKBNDL | Mspos Chk Prod Bundle |
| FEE | FENVPC | Envoy Pc |
| FEE | FPCHRTRMNLBILLING | Pchr Terminal Billing Fee |
| FEE | FMAPPPCSFTWR | Mapp Pc Software |
| FEE | FPCPROD | Pc Product Fee |
| FEE | FPET1TRMNLBILLING | Pet1 Terminal Billing Fee |
| FEE | FPE11TRMNLBILLING | Pe11 Terminal Billing Fee |
| FEE | FVOYPETREXCTAX | Voyager Petro Excise Tax |
| FEE | FVOYPETRPRIMFUELTAX | Voyager Petro Prim Fuel Tax |
| FEE | FVOYPETRSECFUELTAX | Voyager Petro Sec Fuel Tax |
| FEE | FVOYPETRLCLSLSTAX | Voyager Petro Local Sales Tax |
| FEE | FVOYPETRMISCTAX | Voyager Petro Misc. Tax |
| FEE | FVOYPETRDSCNT | Voyager Petro Discounts |
| FEE | FVYGRPETRSLSTAX | Yoyager Petro Sales Tax |
| FEE | FMSPOSBNDL | Ms Pos Full Prod Bundle |
| FEE | FPGRDTRMNLBILLING | Pgrd Terminal Billing Fee |
| FEE | FPH01TRMNLBILLING | Ph01 Terminal Billing Fee |
| FEE | FPICTRMNLBILLING | Pic Terminal Billing Fee |
| FEE | FDBTPINPADBILLING | Debit Pin Pad Billing |
| FEE | FPJCKTRMNLBILLING | Pjck Terminal Billing Fee |
| FEE | FTELN10PKTDC | Tellan Pc Hub 10 Pk Tdc |
| FEE | FTELN20PKTDC | Tellan Pc Hub 20 Pk Tdc |
| FEE | FMACAUTHSFTWR | Macauthorize Pc Software |
| FEE | FPMP7TRMNLBILLING | Pmp7 Terminal Billing Fee |
| FEE | FPMSPTRMNLBILLING | Pmsp Terminal Billing Fee |
| FEE | FPNPSTRMNLBILLING | Pnps Terminal Billing Fee |
| FEE | FPOCTTRMNLBILLING | Poct Terminal Billing Fee |
| FEE | FPOFPTRMNLBILLING | Pofp Terminal Billing Fee |
| FEE | FPLETRMNLBILLING | Pole Terminal Billing Fee |
| FEE | FPOMNTRMNLBILLING | Pomn Terminal Billing Fee |
| FEE | FPORETRMNLBILLING | Pore Terminal Billing Fee |
| FEE | FPPACTRMNLBILLING | Ppac Terminal Billing Fee |
| FEE | FPPCPTRMNLBILLING | Ppcp Terminal Billing Fee |
| FEE | FPPTZTRMNLBILLING | Pptz Terminal Billing Fee |
| FEE | FPPZXTRMNLBILLING | Ppzx Terminal Billing Fee |
| FEE | FPP1ETRMNLBILLING | Pp1E Terminal Billing Fee |
| FEE | FPP2STRMNLBILLING | Pp2S Terminal Billing |
| FEE | FPRINTRMNLBILLING | Prin Terminal Billing Fee |
| FEE | FPRJ6TRMNLBILLING | Prj6 Terminal Billing Fee |
| FEE | FPRN1TRMNLBILLING | Prn1 Terminal Billing Fee |
| FEE | FPS01TRMNLBILLING | Ps01 Terminal Billing Fee |
| FEE | FPS9CTRMNLBILLING | Ps9C Terminal Billing Fee |
| FEE | FFDCPCSFTWR | Fdc Pc Software |
| FEE | FNURIT2080TRMNLBILLING | Nurit 2080 Terminal Billing |
| FEE | FPLCCTAXMRCHCR | Plcc Tax Merchant Credit |
| FEE | FPLCCTAXMRCHDB | Plcc Tax Merchant Debit |
| FEE | FPLCCTAXMRCHCRREV | Plcc Tax Merchant Credit Rev |
| FEE | FPLCCTAXMRCHDBREV | Plcc Tax Merchant Debit Rev |
| FEE | FAPRPRNTWCASE | Apriva Printa W/Case |
| FEE | FPWPKTRMNLBILLING | Pwpk Terminal Billing Fee |
| FEE | FP101P102TRMNLBILLING | P101/P102 Terminal Billing Fee |
| FEE | FP102TRMNLBILLING | P102 Terminal Billing Fee |
| FEE | FDBTPINPADBILLINGFP20 | Debit Pin Pad Billing |
| FEE | FP350TRMNLBILLING | P350 Terminal Billing Fee |
| FEE | FCLVRP501STNPRNT | Clover P501 Station Printer |
| FEE | FVFONEP355THRMPR | Verifone P355 Thermal Printer |
| FEE | FVFONEPRNTBILL | Verifone Printer Billing |
| FEE | FP8FTRMNLBILLING | P8F Terminal Billing Fee |
| FEE | FHYPP8SSPRKTPRNT | Hyp P8S Sprocket Printer |
| FEE | FUSBTPRNTEQPBILL | Usbt Printer Equip Billing Fee |
| FEE | FT1ETTRMNLBILLING | T1Et Terminal Billing Fee |
| FEE | FP950TRMNLBILLING | P950 Terminal Billing Fee |
| FEE | FQBPOSTRMNLBILLING | Qb Pos Terminal Billing Fee |
| FEE | FQUICTRMNLBILLING | Quic Terminal Billing |
| FEE | FVX520TRMNLBILLING | Vx520 Terminal Billing Fee |
| FEE | FREPRTRMNLBILLING | Repr Terminal Billing Fee |
| FEE | FRESOTRMNLBILLING | Reso Terminal Billing Fee |
| FEE | FRIMTTRMNLBILLING | Rimt Terminal Billing Fee |
| FEE | FRLNKTRMNLBILLING | Rlnk Terminal Billing Fee |
| FEE | FMICROSECR | Micros Ecr |
| FEE | FROTETRMNLBILLING | Rote Terminal Billing Fee |
| FEE | FPOSPORTECR | Pos Port Ecr |
| FEE | FDEPSTRPPCASH | Deposit To Rpp Cash Account |
| FEE | FRRYNTRMNLBILLING | Rryn Terminal Billing Fee |
| FEE | FRSCBTRMNLBILLING | Rscb Terminal Billing Fee |
| FEE | FSABLEECR | Sable Ecr |
| FEE | FFD410TRMNLBILLING | Fd410 Terminal Billing Fee |
| FEE | FRSRCTRMNLBILLING | Rsrc Terminal Billing Fee |
| FEE | FMLGCWLSSCNR | Mertologic Wireless Scnr |
| FEE | FRT8MTRMNLBILLING | Rt8M Terminal Billing Fee |
| FEE | FRWRKTRMNLBILLING | Rwrk Terminal Billing Fee |
| FEE | FRZGTTRMNLBILLING | Rzgt Terminal Billing Fee |
| FEE | FSAPITRMNLBILLING | Sapi Terminal Billing Fee |
| FEE | FSBARTRMNLBILLING | Sbar Terminal Billing Fee |
| FEE | FSBOFTRMNLBILLING | Sbof Terminal Billing Fee |
| FEE | FSCANTRMNLBILLING | Scan Terminal Billing Fee |
| FEE | FSCBRTRMNLBILLING | Scbr Terminal Billing Fee |
| FEE | FAPRVSC30BTCARCHRGR | Apriva Sc30Bt Car Chrgr |
| FEE | FSOFTDPSTBCHCTCRPC | Soft Deposit/Batch Catcher Pc |
| FEE | FSECMTRMNLBILLING | Secm Terminal Billing Fee |
| FEE | FSVCTRMNLBILLING | Serv Terminal Billing Fee |
| FEE | FGOSFTMAGRDR | Go Sft/Mag Reader W/Usb |
| FEE | FSGSTTRMNLBILLING | Sgst Terminal Billing Fee |
| FEE | FSHSTTRMNLBILLING | Shst Terminal Billing Fee |
| FEE | FSIGCPPADEQPBILL | Sigc Pinpad Equip Billing Fee |
| FEE | FMACAUTHPCSFTWR | Macauthorize Pc Software |
| FEE | FMBSECRSFTWR | Mbs Ecr Software |
| FEE | FMCITXNPCSFTWR | Mci Trans Pc Software |
| FEE | FMAPPMISCPCSFTWR | Mapp Miscellaneous Pc Software |
| FEE | FSM1YTRMNLBILLING | Sm1Y Terminal Billing Fee |
| FEE | FSPCITRMNLBILLING | Spci Terminal Billing Fee |
| FEE | FDCSPPIIPPAD | Dc Sppii Pin Pad |
| FEE | FPRLGNPCSFTWR | Prologne Pc Software |
| FEE | FRPLCMNTS | Replacements |
| FEE | FSHIPANDHNDLNG | Shipping And Handling |
| FEE | FQPSPCSFTWR | Qps Pc Software |
| FEE | FSOFTDPSTPCSFTWR | Soft Deposit Pc Software |
| FEE | FSQRLECRSFTWR | Squirrel Ecr Software |
| FEE | FSTACTRMNLBILLING | Stac Terminal Billing Fee |
| FEE | FSTRETRMNLBILLING | Stre Terminal Billing Fee |
| FEE | FSTSTRMNLBILLING | Sts Terminal Billing Fee |
| FEE | FSTWSTRMNLBILLING | Stws Terminal Billing Fee |
| FEE | FSVNOBILL | Sv No Bill |
| FEE | FSVCPLUS | Service Plus |
| FEE | FGOSFTWRPCCHRG | Go Software/Pc Charge Exp |
| FEE | FS101TRMNLBILLING | S101 Terminal Billing Fee |
| FEE | FHP15TCHSCRNMNTR | Hp 15" Tch Scrn Monitor |
| FEE | FS232TRMNLBILLING | S232 Terminal Billing Fee |
| FEE | FS295TRMNLBILLING | S295 Terminal Billing Fee |
| FEE | FS453TRMNLBILLING | S453 Terminal Billing Fee |
| FEE | FIVISCRIBE602 | Ivi Scribe 602 |
| FEE | FIVISCRIBE612 | Ivi Scribe 612 |
| FEE | FIVISCRIBE607 | Ivi Scribe 607 |
| FEE | FS7TRMNLBILLING | S7 Terminal Billing Fee |
| FEE | FS7CRTRMNLBILLING | S7Cr Terminal Billing Fee |
| FEE | FS8TRMNLBILLING | S8 Terminal Billing Fee |
| FEE | FPINPAD | Pin Pad |
| FEE | FHYPRCOMS9PPAD | Hypercom S9 Pin Pad |
| FEE | FTALTLKBILLING | Taltlk Billing |
| FEE | F1000SEUSBPPEQPBILLING | 1000Seusb Pp Equip Billing Fee |
| FEE | FTA01TRMNLBILLING | Ta01 Terminal Billing Fee |
| FEE | FCASHDRWR | Cash Drawer |
| FEE | FFD400TICDMA | Fd400Ti Cdma |
| FEE | FPYMT1000RGSTR | Paymate 1000 Register |
| FEE | FNURIT2080TDCTRMLBILLING | Nurit 2080 Tdc Terminal Bill |
| FEE | FTMSSTFLSVCTAX | Tms Suite Full Service Fee Tax |
| FEE | FNURIT2090HDCTRMLBILLING | Nurit 2090 Hdc Terminal Bill |
| FEE | FFTSTRRCPTPRNT | Ft Store Receipt Printer |
| FEE | FTMSSTHLPDSKTAX | Tms Suite Help Desk Fee Tax |
| FEE | FFD400TIGPRS | Fd400Ti Gprs |
| FEE | FTALTIPPCRDB | Talento T Ipp Credit/Debi |
| FEE | FTIVCTRMNLBILLING | Tivc Terminal Billing Fee |
| FEE | FFD200TIWF | Fd200Ti Wifi |
| FEE | FFD200T | Fd200T |
| FEE | FTKMITRMNLBILLING | Tkmi Terminal Billing Fee |
| FEE | FAUTOTKTDSPNSR | Automated Ticket Dispenser |
| FEE | FTELNPCAUTH | Tellan Pc Authorize Fee |
| FEE | FTELNPCHUB5PK | Tellan Pc Hub 5Pk Hdc |
| FEE | FTMSSTFLSVC | Tms Suite Full Service Fee |
| FEE | FTMSSTHLPDSK | Tms Suite Help Desk Fee |
| FEE | FTMSSTSWAP | Tms Suite Swap Fee |
| FEE | FTPMRTRMNLBILLING | Tpmr Terminal Billing Fee |
| FEE | FTXNTRMNLBILLING | Tran Terminal Billing Fee |
| FEE | FTRBTRMNLBILLING | Trb Terminal Billing Fee |
| FEE | FTREKTRMNLBILLING | Trek Terminal Billing Fee |
| FEE | FTXN330TRCK2BILL | Trans 330 Track 2 Bill |
| FEE | FTRNZTRMNLBILLING | Trnz Terminal Billing |
| FEE | FSTSSNRSEDC | Sts Sunrise Edc |
| FEE | FTSOLTRMNLBILLING | Tsol Terminal Billing Fee |
| FEE | FTMSSTSWAPTAX | Tms Suite Swap Fee Tax |
| FEE | FNURIT2090TDCTRMLBILLING | Nurit 2090 Tdc Terminal Bill |
| FEE | FTRNZ420TMNL | Tranz 420 Terminal |
| FEE | FICREV | Interchange Reversal |
| FEE | FTCKTOTTAX | Telecheck Total Tax |
| FEE | FTCKPOSEQPS | Telecheck Pos Equipment Fees |
| FEE | FTCKRCVRY | Telecheck Recovery Fees |
| FEE | FTCKPMTS | Telecheck Payments |
| FEE | FTCKWRNTYLEDADJ | Telecheck Warranty Ledger Adj |
| FEE | FTCKDB | Tck Debit Fees |
| FEE | FTCKCR | Tck Credit Fees |
| FEE | FTCKRETITM | Telecheck Returned Item Fee |
| FEE | FT340TRMNLBILLING | T340 Terminal Billing Fee |
| FEE | FT4TPTRMNLBILLING | T4Tp Terminal Billing Fee |
| FEE | FVFONETRNZ460 | Verifone Tranz 460 |
| FEE | FT77FTRMNLBILLING | T77F Terminal Billing Fee |
| FEE | FT7PLTRMNLBILLING | T7Pl Terminal Billing Fee |
| FEE | FT77STRMNLBILLING | T77S Terminal Billing Fee |
| FEE | FHYPRCOMT77THRML | Hypercom T77 Thermal |
| FEE | FHYPT77TERMPRN | Hyp T77 Term/Prn In 1 |
| FEE | FDATACRDTRMNL | Datacard Terminals |
| FEE | FTXNZ380DBT | Tranz 380 Debit |
| FEE | F8320TRMNLBILLING | 8320 Terminal Billing Fee |
| FEE | FSTN2018PRNTR | Station 2018 Printer |
| FEE | FUNLMTRMNLBILLING | Unlm Terminal Billing Fee |
| FEE | FUPTCTRMNLBILLING | Uptc Terminal Billing Fee |
| FEE | FURT2TRMNLBILLING | Urt2 Terminal Billing |
| FEE | FUSBTTRMNLBILLING | Usbt Terminal Billing Fee |
| FEE | FNURIT8000USWTRMNL | Nurit 8000 On Usw Termianl Fee |
| FEE | FLYLTBALINQ | Loyalty Balance Inquiry |
| FEE | FLYLTRDMPTN | Loyalty Redemption |
| FEE | FLYLTACCTUPDU52 | Loyalty Account Update |
| FEE | FLYLTADDACCTU53 | Loyalty Add Account |
| FEE | FLYLTIMPL | Loyalty Implementation Fee |
| FEE | FLYLTTXN | Loyalty Transaction Fee |
| FEE | FLYLTCARDSETUP | Loyalty Card Setup Fee |
| FEE | FLYLTMAINTLOC | Loyalty Maint Fee/Location |
| FEE | FVAUTRMNLBILLING | Vau Terminal Billing Fee |
| FEE | FVA76TRMNLBILLING | Va76 Terminal Billing Fee |
| FEE | FVB03TRMNLBILLING | Vb03 Terminal Billing Fee |
| FEE | FVB17TRMNLBILLING | Vb17 Terminal Billing Fee |
| FEE | FVB40TRMNLBILLING | Vb40 Terminal Billing Fee |
| FEE | FVB93TRMNLBILLING | Vb93 Terminal Billing Fee |
| FEE | FCLVRCASHDRW | Clover Cash Drawer |
| FEE | FVC03TRMNLBILLING | Vc03 Terminal Billing Fee |
| FEE | FVIVOTRMNL | Vivo Terminal Fee |
| FEE | FICVVERVALCADDM | Icv Ver Valc Add M |
| FEE | FICVVERIFADDUSR | Icv Verif Add User |
| FEE | FICVWINSUUPGRD | Icv Win Su Upgrd |
| FEE | FICVSETUP | Icv Setup |
| FEE | FICVWINNEWSU | Icv Win New S U |
| FEE | FICVWINNEWMU | Icv Win New M U |
| FEE | FICVWINMULUPGD | Icv Win Mul Upgd |
| FEE | FICVVALCDCHNG | Icv Valcode Chng |
| FEE | FICVUPGDDOSWINS | Icv Upgd Dos/Win S |
| FEE | FICVCONVSUMUWO | Icv Conv Su Mu Wo |
| FEE | FVFPPTRMNLBILLING | Vfpp Terminal Billing Fee |
| FEE | FVFONEMVMR | Verifone Movimrch |
| FEE | FVNSTRMNLBILLING | Vns Terminal Billing Fee |
| FEE | FVIVO4500MTMNL | Vivo 4500M Terminal Billing |
| FEE | FVIVO4500TRMNL | Vivo 4500 Terminal Fee |
| FEE | FICVFYWINMLT | Ic Verify Windows Multi |
| FEE | FCLVRRCPTPRNT | Clover Receipt Printer |
| FEE | FSLIPPRNTBILLING | Slip Printer Billing |
| FEE | FVER0TRMNLBILLING | Ver0 Terminal Billing Fee |
| FEE | FICVFYWINWINMLTUSR | Ic Verify Win/Win Multi User |
| FEE | FICVFYDOSMLTUSR | Ic Verify Dos Multi User |
| FEE | FCLVRSFTWRRC | Clover Software Rc |
| FEE | FVSMTRMNLBILLING | Vsm Terminal Billing Fee |
| FEE | FVLSTCRD | Vlst Crd (Call 8003106661) |
| FEE | FVLSTDB | Vlst Db Fee (Call 8003106661) |
| FEE | FVLSTDBRTN | Vlst Db Rtn (Call 8003106661) |
| FEE | FVLSTRTNCRD | Vlst Rtn Crd (Call 8003106661) |
| FEE | FVLSTDBCB | Vlst Db Cb (Call 8003106661) |
| FEE | FVLSTCBCRD | Vlst Cb Crd (Call 8003106661) |
| FEE | FVALSTARMCHNG | Value Star Matching Fee |
| FEE | FVSFDMSCMMSN | Vs/Fdms Commission Fee |
| FEE | FVSCHNLCMMSN | Vs/Channel Commission Fee |
| FEE | FVT08TRMNLBILLING | Vt08 Terminal Billing Fee |
| FEE | FVT58TRMNLBILLING | Vt58 Terminal Billing Fee |
| FEE | FVUSTRMNLBILLING | Vus Terminal Billing Fee |
| FEE | FV150TRMNLBILLING | V150 Terminal Billing Fee |
| FEE | FV3ATRMNLBILLING | V3A Terminal Billing Fee |
| FEE | FV3CTRMNLBILLING | V3C Terminal Billing Fee |
| FEE | FV3MTRMNLBILLING | V3M Terminal Billing Fee |
| FEE | FV3NTRMNLBILLING | V3N Terminal Billing Fee |
| FEE | FV3STRMNLBILLING | V3S Terminal Billing Fee |
| FEE | FV3TTRMNLBILLING | V3T Terminal Billing Fee |
| FEE | FV3UTRMNLBILLING | V3U Terminal Billing Fee |
| FEE | FV744TRMNLBILLING | V744 Terminal Billing Fee |
| FEE | FV80TRMNLBILLING | V80 Terminal Billing Fee |
| FEE | FWDGETRMNLBILLING | Wdge Terminal Billing Fee |
| FEE | FWEDGTRMNLBILLING | Wedg Terminal Billing Fee |
| FEE | FWFPTTRMNLBILLING | Wfpt Terminal Billing Fee |
| FEE | FWICVTRMNLBILLING | Wicv Terminal Billing Fee |
| FEE | FFD200WFTRMNLBILLING | Fd 200 Wifi Terminal Billing |
| FEE | FWIP2TRMNLBILLING | Wip2 Terminal Billing Fee |
| FEE | FWKITTRMNLBILLING | Wkit Terminal Billing Fee |
| FEE | FWELLSEMVNFCMOBRDR | Wells Emv Nfc Mobl Rdr |
| FEE | FMAGTEKCARDRDR | Mag Tek Card Reader |
| FEE | FWPLETRMNLBILLING | Wple Terminal Billing Fee |
| FEE | FWPTCTRMNLBILLING | Wptc Terminal Billing Fee |
| FEE | FNURIT2090WRLSTERM | Nurit 2090 Wireless Term Fee |
| FEE | FWRXSTRMNLBILLING | Wrxs Terminal Billing Fee |
| FEE | FWEXTAXMRCHCR | Wex Tax Merchant Credit |
| FEE | FWEXTAXMRCHDB | Wex Tax Merchant Debit |
| FEE | FWEXTAXMRCHCRREV | Wex Tax Merchant Credit Rev |
| FEE | FWEXTAXMRCHDBREV | Wex Tax Merchant Debit Rev |
| FEE | FWEXDSCNT | Wright Express Discount |
| FEE | FVFONEFD55 | Verifone Fd55 |
| FEE | FTRSTKPRDIRSCN | Trustkeeper Directed Scans |
| FEE | FTRSTKPRERLTRMN | Trustkeeper Early Termination |
| FEE | FOMNIXBRDRLCLCUR | Omni Xbrdr Local Cur Ap |
| FEE | FCHKRDRMAG | Check Reader, Mag 22360001 |
| FEE | FZONZL300TRMNL | Zon Zl300 Terminal |
| FEE | FX830TRMNLBILLING | X830 Terminal Billing Fee |
| FEE | FX870TRMNLBILLING | X870 Terminal Billing Fee |
| FEE | FYAHOTRMNLBILLING | Yaho Terminal Billing Fee |
| FEE | FYC2RTRMNLBILLING | Yc2R Terminal Billing Fee |
| FEE | FWAYSYSTRMNLBILLING | Waysys Terminal Billing Fee |
| FEE | FTASOLCMPLIABW | Transarmor Sol Compl+Liab Waiv |
| FEE | FCLVRMENUONLNORDR | Clover Menu Online Ordering |
| FEE | FCLVRMENUPRM | Clover Menu Premium |
| FEE | FFRAUDDTCTMNTH | Fraud Detect Monthly |
| FEE | FCLVRONLNSTRVIP | Clover Online Store Vip Fee |
| FEE | FFRAUDDTCTIMPL | Fraud Detect Implementatn Fee |
| FEE | FFRAUDDTCTANNUAL | Fraud Detect Annual Fee |
| FEE | FFRAUDDTCTPRCSNG | Fraud Detect Processing Fee |
| FEE | FACCTUPDRMNTH | Account Updater Monthly Fee |
| FEE | FPERDPIMPL | Personal Dp Implement Fee |
| FEE | FPERDPMNTH | Personal Dp Monthly Fee |
| FEE | FDGTLDISBRSMNTIMP | Digitaldisbursement_Impfee |
| FEE | FINSGHTBNCHMNTH | Ent Insights Bench Mthly |
| FEE | FINSGHTLOBBYMNTH | Ent Insights Lobby Mthly |
| FEE | FTRANINSGHTONETIME | Tran Insights Onetime Fee |
| FEE | FADINSGHTONETIME | Ad Insights Onetime Fee |
| FEE | FADINSGHTIMNTH | Ad Insights Mthly |
| FEE | FTRNSXPLTFRM | Transax Platform |
| FEE | FPNAPLBSNSST | Pineapple Business Suite |
| FEE | FFRAUDDTCTONTM | Fraud Detect One Time Fee |
| FEE | FFRAUDDTCTMNTHMNGDSVC | Fraud Detect Mthlymngdservfee |
| FEE | FFRAUDDTCTMNTHMAIN | Fraud Detect Mthly Main Fee |
| FEE | FDVCINTLGNCE | Device Intelligence Fee |
| FEE | FZONTRMNLBILLING | Zon+ Terminal Billing |
| FEE | FZONXLTRMNLBILLING | Zon Xl Terminal Billing |
| FEE | FZONJTRMNLBILLING | Zonj Terminal Billing Fee |
| FEE | FNWICCBMSTRSMS | Nw Incoming Cb Maestro Sms |
| FEE | FVICHGBK | Visa Chargeback Fee |
| FEE | FNWAC020FRDCNPLACSMS | Nw Acpt 0 20 Frd Cnp Lac Sms |
| FEE | FNWAC2125FRDCNPLACSMS | Nw Acpt 21 25 Frd Cnp Lac Sms |
| FEE | FNWAC2630FRDCNPLACSMS | Nw Acpt 26 30 Frd Cnp Lac Sms |
| FEE | FNWNOACFRDCNPLACSMS | Nw No Acpt Frd Cnp Lac Sms |
| FEE | FNWAC020FRDEXSMS | Nw Acpt 0 20 Frd Excess Sms |
| FEE | FNWAC2125FRDEXSMS | Nw Acpt 21 25 Frd Excess Sms |
| FEE | FNWAC2630FRDEXSMS | Nw Acpt 26 30 Frd Excess Sms |
| FEE | FNWNOACFRDEXSMS | Nw No Acpt Frd Excess Sms |
| FEE | FEBTCASHBNFTPURUT | Ebt Cash Benefit Pur Fee Utah |
| FEE | FEBTFDSTMPPUROR | Ebt Food Stamp Pur Fee Oregon |
| FEE | FEBTFDSTMPRETOR | Ebt Food Stamp Ret Fee Oregon |
| FEE | FEBTCASHBNFTPUROR | Ebt Cash Bene Pur Fee Oregon |
| FEE | FEBTFDSTMPPURID | Ebt Food Stamp Purch Fee Idaho |
| FEE | FEBTFDSTMPRETID | Ebt Food Stamp Ret Fee Idaho |
| FEE | FEBTFDSTMPPURWS | Ebt Food Stamp Purch Fee Wash |
| FEE | FEBTFDSTMPRETWS | Ebt Food Stamp Ret Fee Wash |
| FEE | FEBTCSHBNFTPURWS | Ebt Cash Bene Purch Fee Wash |
| FEE | FEBTFDSTMPPURCOL | Ebt Food Stamp Purch Fee Colo |
| FEE | FEBTFDSTMPRETCOL | Ebt Food Stamp Ret Fee Colo |
| FEE | FEBTFDSTMPRETAL | Ebt Food Stamp Ret Fee Alaska |
| FEE | FEBTCSHBNFTPURAL | Ebt Cash Bene Purch Fee Alaska |
| FEE | FVIAUTHOPTDECLDRTR | Auth Opt Visa Decld Retry Fee |
| FEE | FBYPDBTCOSTFUELPREAUTH | Byp Debit Costco Fuel Pre Auth |
| FEE | FVOYDECL | Voyager Decline |
| FEE | FREGPINDBAUTH | Reg Pin Debit Auth Fee |
| FEE | FREGSIGDBAUTH | Reg Sig Debit Auth Fee |
| FEE | FREGDBAUTH | Reg Debit Authorization Fee |
| FEE | F0CPPTRMNLBILLING | 0Cpp Terminal Billing Fee |
| FEE | FREGPSCAUTHFS | Reg Pin/Sig/Credit Auth Fee Fs |
| FEE | FREGPSCAUTH | Reg Pin/Sig/Credit Auth Fee |
| FEE | FPINSIGCRAUTH | Pin/Sig/Credit Auth Fee Fs |
| FEE | FPINSIGCRAUTHF0CZ | Pin/Sig/Credit Auth Fee |
| FEE | FEBTONLNDECL | Ebt Online Declines |
| FEE | FFUELPREAUTHAPPRV | Fuel Preauth Approved |
| FEE | FFUELPREAUTHDECL | Fuel Preauth Declined |
| FEE | FFUELCMPLTNAPPRV | Fuel Completion Approved |
| FEE | FPURAPRV | Purchase Approved |
| FEE | FPURDECLD | Purchase Declined |
| FEE | FREVAPRV | Reversal Approved |
| FEE | FREVDECLD | Reversal Declined |
| FEE | FRFNDAPRV | Refund Approved |
| FEE | FRFNDDECLD | Refund Declined |
| FEE | FACCESS | Access Fee |
| FEE | FEBTONLNAUTH | Ebt Online Authorization |
| FEE | FEBTONLNRFND | Ebt Online Refund |
| FEE | FFD400GTTRMNLBILLING | Fd400Gt Terminal Billing Fee |
| FEE | FMSTRDB | Maestro Debit Fee |
| FEE | FGFTCARDVOICEAUTH | Gift Card Voice Auth Fee |
| FEE | FVIDBBTCHAUTH | Visa Debit Batch Auth Fee |
| FEE | FTCKIPVERFAUTH | Tck In Person Verf Auth Fee |
| FEE | FTCKIPVERFINQ | Tck In Person Verf Inq Fee |
| FEE | FTCKIPVERFMTHMIN | Tck In Person Verf Mth Min |
| FEE | FMCDBTELEC | Mc Debit Electronic |
| FEE | FMCDBTVOICE | Mc Debit Voice |
| FEE | FMCDBTISSREFF | Mc Debit Issuer Referral |
| FEE | FMCCPDBTMAILORDR | Mc Chip Debit Mail Order |
| FEE | FMCCPDBTELEC | Mc Chip Debit Electronic |
| FEE | FMCCPDBTVOICE | Mc Chip Debit Voice |
| FEE | FMCCPDBTISSREFF | Mc Chip Debit Issuer Referral |
| FEE | FUOFPASLSTXN | U Of Pa Sales Transaction Fee |
| FEE | FDUQUESNESLSTXN | Duquesne Sales Transaction Fee |
| FEE | FDBTMLTXN | Magicline Debit Tran Fee |
| FEE | FDBTGLFNTTXN | Gulfnet Debit Tran Fee |
| FEE | FSHAZAMSPNSR | Shazam Sponsor Fee |
| FEE | FACCELDBTPURSF | Accel Dbt Purchase,Store/Fwd |
| FEE | FWLMRTPLSMSLSTXN | Walmt Pl Sams Sale Tran |
| FEE | FWLMRTPLSMRTRNTXN | Walmt Pl Sams Rtrn Tran |
| FEE | FWLMRTPLSMBSNSSLSTXN | Walmt Pl Sams Busnss Sale Tran |
| FEE | FWLMRTPLSMBSNSRTRNTXN | Walmt Pl Sams Busnss Rtrn Tran |
| FEE | FWLMRTPLGECFSLSTXN | Walmt Pl Gecf Sale Tran |
| FEE | FWLMRTPLGECFRTRNTXN | Walmt Pl Gecf Rtrn Tran |
| FEE | FILNKDBTPURRSBMT | Interlink Dbt Purch,Resubmit |
| FEE | FMCAUTHF03S | Mastercard Auths |
| FEE | FVIAUTHF04S | Visa Auths |
| FEE | FAMXZERODLRAUTH | Zero Dollar Auth Fee Amex |
| FEE | FZERODLRAUTHDISC | Zero Dollar Auth Fee Disc |
| FEE | FDSCVAUTHF07S | Discover Auths |
| FEE | FJCBZERODLRAUTH | Zero Dollar Auth Fee Jcb |
| FEE | FJCBAUTHF08S | Jcb Auths |
| FEE | FGPLECARDAUTH | Gen Pl Ecard Authorization Fee |
| FEE | FPVTLBLEMRK | Pti Private Label Enmark |
| FEE | FDSVINTWKACQPRUSCR | Ds Vi Ntwk Acq Proc Fee Us Cr |
| FEE | FDSVINWKACQPRINTLCR | Ds Vi Nwk Acq Proc Fee Intl Cr |
| FEE | FDSVIIC | Ds Vi Interchange Fee |
| FEE | FDSUSXBRDR | Ds Us Cross Border Fee |
| FEE | FDSFUELMCTXN | Ds Fuel Mc Trn |
| FEE | FDSMCASSMT | Ds Mastercard Assessment Fee |
| FEE | FHDCVINTWKACQPRUSCR | Hdc Vi Ntwk Acq Proc Fee Us Cr |
| FEE | FHDCVINWKACQPRINTLCR | Hdc Vi Nwk Acq Proc Fee Intlcr |
| FEE | FHDCVIIC | Hdc Vi Interchange Fee |
| FEE | FHDCUSXBRDR | Hdc Us Cross Border Fee |
| FEE | FHDCFLMCTXN | Hdc Fl Mc Trn |
| FEE | FHDCMCASSMT | Hdc Mastercard Assessment Fee |
| FEE | FINGENICOLN8000 | Ingenico Lane 8000 |
| FEE | FINGENICOLN7000 | Ingenico Lane 7000 |
| FEE | FINGENICOLN3600 | Ingenico Lane 3600 |
| FEE | FINGENICOLN3000 | Ingenico Lane 3000 |
| FEE | FINGENICOMV5000 | Ingenico Move 5000 |
| FEE | FINGENICODSK3500 | Ingenico Desk 3500 |
| FEE | FINGENICODSK1600 | Ingenico Desk 1600 |
| FEE | F1PCITRMNLBILLING | 1Pci Terminal Billing Fee |
| FEE | F1PP2TRMNLBILLING | 1Pp2 Terminal Billing Fee |
| FEE | FCLVRSCNR1 | Clover Scanner 1 |
| FEE | FWMMCCHGBK | Wm Mc Chargeback Fee |
| FEE | F1YRSTRMNLBILLING | 1Yrs Terminal Billing Fee |
| FEE | F11B0TRMNLBILLING | 11B0 Terminal Billing Fee |
| FEE | FCLVRSKPISV | Shopkeep Isv Clover |
| FEE | FCLVRMCMPISV | Micamp Isv Clover |
| FEE | FMRKIMX64RTR | Meraki Mx64 Router |
| FEE | FDLNKDGS1008PSWTCH | D Link Dgs 1008P Switch |
| FEE | FMRKIMR33ACCPNT | Meraki Mr33 Access Point |
| FEE | FCLVREMPLGNCRD | Clover Employeelogincard |
| FEE | FCLVRFLXSLCNSLV | Clover Flexsiliconesleev |
| FEE | F2DHNDSFREEBCSCNR | 2D Hands Free Bc Scanner |
| FEE | FRP10PINPADBILLING | Rp10 Pin Pad Billing Fee |
| FEE | FRP10STNDBILLING | Rp10 Stand Billing Fee |
| FEE | F12VCTRMNLBILLING | 12Vc Terminal Billing Fee |
| FEE | FMCFNDTXN | Mc Funding Transaction Fee |
| FEE | FCLVRSTNSOLO | Clover Station Solo |
| FEE | FCLVRGO3RDG | Clover Go 3Rd Gen |
| FEE | F13PPTRMNLBILLING | 13Pp Terminal Billing Fee |
| FEE | FREADYLNKTXN | Readylink Txn |
| FEE | FREADYLNKINQ | Readylink Inq |
| FEE | FMNYTFRSCRDPMTPTF | Money Transfer Credit Pmt Ptf |
| FEE | FOSRC1099KCORR | Outsrce 1099 K Correspondence |
| FEE | FOSRCBUWREPFL | Outsrce Buw Reporting/File |
| FEE | FMNYTFRCRDDISCRT | Money Transfer Credit Disc Rt |
| FEE | FETCCHK | Etc Check Fee |
| FEE | FMISCDBAUTH | Misc Debit Authorization Fee |
| FEE | FPAXSTRMGT | Paxstore Mgt Fee |
| FEE | FPAXA80TRMNL | Pax A80 Terminal |
| FEE | FPAXA920MOBTRMNL | Pax A920 Mobile Terminal |
| FEE | FPAXA920PROMOBTRMNL | Pax A920 Pro Mobile Terminal |
| FEE | FDSVINTWKACQUSDP | Ds Vi Ntwk Acq Proc Fee Us D/P |
| FEE | FDSVINWKACQINTLDP | Ds Vi Nwk Acq Proc Fee Intld/P |
| FEE | FDSVIASSMTCR | Ds Visa Assessment Fee Cr |
| FEE | FDSMCIC | Ds Mc Interchange Fee |
| FEE | FDSNONFMCTXN | Ds Nonf Mc Trn |
| FEE | FTAINITLCNSE | Transarmor Initial License Fee |
| FEE | FTAMONMAINT | Transarmor Monthly Maintenance |
| FEE | FCHBSOLECOSYS | Commerce Hub Sol Ecosystem Fee |
| FEE | FCHBSTDPERTXNCTGR | Commercehub Std Per Tran Ct Gr |
| FEE | FCHBSTDPERTXNCTCR | Commercehub Std Per Tran Ct Cr |
| FEE | FCHBSTDPERTXNATCR | Commercehub Std Per Tran At Cr |
| FEE | FCHBSTDPERTXNCTDB | Commercehub Std Per Tran Ct Db |
| FEE | FCHBSTDPERTXNATDB | Commercehub Std Per Tran At Db |
| FEE | FCHBPRMPERTXNCTGR | Commercehub Prm Per Tran Ct Gr |
| FEE | FCHBPRMPERTXNCTCR | Commercehub Prm Per Tran Ct Cr |
| FEE | FCHBPRMPERTXNATCR | Commercehub Prm Per Tran At Cr |
| FEE | FCHBPRMPERTXNCTDB | Commercehub Prm Per Tran Ct Db |
| FEE | FCHBPRMPERTXNATDB | Commercehub Prm Per Tran At Db |
| FEE | FHDCVINTWKACQRPRCSNGUSDP | Hdc Vi Ntwk Acq Proc Fee Us Dp |
| FEE | FHDCVINTWKACQPRCSNGDBTINTL | Hdc Vi Nwk Acq Proc Fee Intldp |
| FEE | FVIHDCASSMTCR | Hdc Visa Assessment Fee Cr |
| FEE | FHDCMCIC | Hdc Mc Interchange Fee |
| FEE | FHDCUSXBRDRNONUSD | Hdc Us Cross Brdr Fee, Nonusd |
| FEE | FHDCNFLMCTXN | Hdc Nfl Mc Trn |
| FEE | FDVCCR3YRPLN | Device Care 3 Year Plan |
| FEE | FTELNMACHUB2PKTDC | Tellan Mac Hub 2Pk Tdc |
| FEE | FAUGUSBCHPRDR | Augusta Usb Chip Reader |
| FEE | FWISEPAD2 | Wisepad 2 |
| FEE | FCLVRFLX3 | Clover Flex 3 |
| FEE | FCLVRFLX3STRTKIT | Clover Flex 3 Starter Kit |
| FEE | FCLVRDUODSPL | Clover Duo Display |
| FEE | FCLVRDUOSTRTKIT | Clover Duo Starter Kit |
| FEE | FCLVRFLEX | Clover Flex |
| FEE | FCLVRFLEX2GSTKT | Clover Flex 2Gstarterkit |
| FEE | FCLVRMIN2TTRCBL | Clover Mini 2 Tether Cbl |
| FEE | FCLVRDUO2TMNL | Clover Duo 2 Terminal |
| FEE | FEPSLBLPRNT | Epson Label Printer |
| FEE | FSTARTHRMLKITPRNT | Star Thermal Kit Printer |
| FEE | FHFREBCSCNR2 | Hands Free Bc Scanner 2 |
| FEE | FCLVRMINI3 | Clover Mini 3 |
| FEE | FCLVRMINI3STRTKIT | Clover Mini 3 Starter Kit |
| FEE | FCLVRSOLOSTRTKIT | Clover Solo Starter Kit |
| FEE | FCLVRACCT | Clover Account |
| FEE | FCLVRMINI2WF | Clover Mini 2 Wifi |
| FEE | FCLVRFLEX2WF | Clover Flex 2 Wifi |
| FEE | FCLVRFLEXTRVLKIT | Clover Flex Travel Kit |
| FEE | FV400MWLSTRMNL | V400M Wireless Terminal |
| FEE | FCLVRFLEX2VRZN | Clover Flex 2 Verizon |
| FEE | FCLVRDUO2DSPL | Clover Duo 2 Display |
| FEE | FCLVRDUO2STKT | Clover Duo 2 Starterkit |
| FEE | FCLVRKCHNDSPL | Clover Kitchen Display |
| FEE | FCLVRSCNR2 | Clover Scanner 2 |
| FEE | FCLVRSMBRWDCRD | Clover Smb Rewards Credit |
| FEE | FWMVICHGBK | Wm Vi Chargeback Fee |
| FEE | FMCDSASSMTGT1K | Mc Ds Assessmnt Tran Amt >=$1K |
| FEE | FMCHDCASSMTGT1K | Mc Hdc Assessmnt Trn Amt >=$1K |
| FEE | FCPLRDMPTN | Cpl Redemption |
| FEE | FESSOEXTRRDMD | Esso Extra Redeemed |
| FEE | FAEROERND | Aero Earned |
| FEE | FCRWSHRDMP | Carwash Redemption |
| FEE | FIOLPCOPTMRDMP | Iol Pc Optimum Redemption |
| FEE | FDISCRTPERITM | Discount Rate Per Item |
| FEE | FNQDSCNTF21K | Non Qual Discount |
| FEE | FBOACARDLSRBT | Boa Card Sales Rebate |
| FEE | FARLNFGNBINUSG | Airline Foreign Bin Usage Fee |
| FEE | FCSTMRPTACCSUBS | Custom Rpt Acc Id (Subs) |
| FEE | FFRAUDDTCTTXN | Fraud Detect Transaction |
| FEE | FFRAUDDTCTMNTHMIN | Fraud Detect Monthly Minimum |
| FEE | FNTWKTKNIMPL | Network Token Implement Fee |
| FEE | FWEX3PDSCNT | Wex 3P Discount |
| FEE | FDDHOSTDSCNTREGLR | Dd+ Host Discount Regular |
| FEE | FDDHOSTDSCNTSUPRM | Dd+ Host Discount Supreme |
| FEE | FDDCSTRDSCNT | Dd+ Cstore Discount Fee |
| FEE | FREGPINSIGCRSLSDISC | Reg Pin/Sig/Credit Sales Disc |
| FEE | FDBTSLSFLATTXN | Debit Sales Flat Tran Fee |
| FEE | FDBTRETFLATTXN | Debit Returns Flat Tran Fee |
| FEE | FREGPINSIGCRSLSTXN | Reg Pin/Sig/Credit Sale Tran |
| FEE | FRSASLSPROMO2 | Rsa Sales Promo 2 |
| FEE | FRSASLSPROMO6 | Rsa Sales Promo 6 |
| FEE | FRSASLSPROMO7 | Rsa Sales Promo 7 |
| FEE | FRSASLSPROMO8 | Rsa Sales Promo 8 |
| FEE | FRSASLSPROMO9 | Rsa Sales Promo 9 |
| FEE | FSVCARDPERACHENTRY | Sv Card Per Ach Entry |
| FEE | FSVCARDPERACHREJ | Sv Card Per Ach Rejection |
| FEE | FCLXDLXMNTH | Clientline Deluxe Monthly Fee |
| FEE | FCLXDLXUSR | Clientline Deluxe User Fee |
| FEE | FDSMCNFL | Ds Fee Non Fuel Mc |
| FEE | FDXBRDR | Ds Cross Border Fee |
| FEE | F3ECATRMNLBILLING | 3Eca Terminal Billing Fee |
| FEE | FHDCXBRDR | Hdc Cross Border Fee |
| FEE | FBINGOFRRFNDSTMT | Bing Offer Rfnd See Stmt |
| FEE | FCARDSPRNGRFND | Cardspring Rfnd8554263327 |
| FEE | FBINGOFRSSEESTMT | Bing Offer Fees See Stmt |
| FEE | FCARDSPRNG | Cardspring 855 426 3327 |
| FEE | FAFSNVGTRRFND | Afs Nvgtr Rfnd 8883729588 |
| FEE | FHRPCAUDISCSETUP | Hrp Cau Disc Set Up Fee |
| FEE | FVIHRPCAUSETUP | Hrp Cau Visa Set Up Fee |
| FEE | FSVIVRUSGINTLMINUTE | Sv Ivr Usage Intl Minute |
| FEE | FFILERSDNCY | File Residency Fee |
| FEE | FADDONACCESSMNTH | Add On Monthly Access Fee |
| FEE | FDTMARKMNTH | Datamark Monthly Fee |
| FEE | FFINDETAILFILE | Financial Detail File Fee |
| FEE | FONLNTRNGACCMNTH | Online Training Acc Month Fee |
| FEE | FCOMBEXTRCTFILE | Combined Extract File Fee |
| FEE | FMRGDATAFILE | Mrg Data File Fee |
| FEE | FVIAUTOBILLINGUPDTMNTH | Vi Auto Billing Upd Mth Fee |
| FEE | FICVFYSETUP | Ic Verify Set Up Fee |
| FEE | FBTCHACTVTYRPT | Batch Activity Report Fee |
| FEE | FFARSRPT | Fars Report Fee |
| FEE | FSPNDTRNDONLNTL | Spendtrend Online Tool Fee |
| FEE | FSPNDTRNDCLSDLPPRPD | Spendtrend Closed Loop Prepaid |
| FEE | FSPNDTRNDMONANLS | Spendtrend Monthly Analysis |
| FEE | FPYMTSTAXMGR | Payments Tax Manager |
| FEE | FFRAUDSVCMNTH | Fraud Services Monthly Fee M |
| FEE | FAPRVPRMTRINIT | Apriva Parameter Init Fee |
| FEE | FCHGBKDTLRPT | Chargeback Detail Report |
| FEE | FRECRRBILLINGAUTH | Recurring Billing Auth Fee |
| FEE | FHRPCAUMCPERMCH | Hrp Cau Mc Per Match Fee |
| FEE | FHRPCAUDISCPERMTCH | Hrp Cau Disc Per Match Fee |
| FEE | FVIHRPCAUPERMTCH | Hrp Cau Visa Per Match Fee |
| FEE | FWX160ONLNDBTMONRPT | Wx 160 Online Debit Mthly Rpt |
| FEE | FVINETONLNMNTH | Visa Net Online Monthly |
| FEE | FHRPCAUMCPRC | Hrp Cau Mc Processing Fee |
| FEE | FHRPCAUDISCPRCSNG | Hrp Cau Disc Processing Fee |
| FEE | FVIHRPCAUPPRCSNG | Hrp Cau Visa Processing Fee |
| FEE | FEQPMAINTPINPAD | Equip Maint @ $3.00/Pinpad |
| FEE | F380XTRMNLBILLING | 380X Terminal Billing Fee |
| FEE | F4ADUTRMNLBILLING | 4Adu Terminal Billing Fee |
| FEE | FCARDDSGNPRDCT | Card Designs / Products |
| FEE | FCOLLATERAL | Collateral |
| FEE | F3RDPRTYDMPDMNTH | 3Rdprty Dimpldough Monthly Fee |
| FEE | F3RDPRTYDMPDSETUP | 3Rdprty Dimpldough Setup Fee |
| FEE | F3RDPRTYDMPDINSTLMT12 | 3Rdprty Dmpldoug Instlmt Fee12 |
| FEE | F3RDPRTYDMPDINSTLMT24 | 3Rdprty Dmpldoug Instlmt Fee24 |
| FEE | F3RDPRTYDMPDINSTLMT36 | 3Rdprty Dmpldoug Instlmt Fee36 |
| FEE | FGFTCARDDTONLORDR | Gift Card Data Only Order |
| FEE | FDTONLORDSETUP | Data Only Order Setup Fee |
| FEE | FDTONLORDTXN | Data Only Order Trnsaction Fee |
| FEE | F4KAMTRMNLBILLING | 4Kam Terminal Billing Fee |
| FEE | F3RDPRTYAFFINITYMNTH | 3Rdprty Affinity Monthly Fee |
| FEE | F3RDPRTYAFFINITYSETUP | 3Rdprty Affinity Setup Fee |
| FEE | FMRKTMAT | Marketing Materials |
| FEE | F4MUUTRMNLBILLING | 4Muu Terminal Billing Fee |
| FEE | F4NMUTRMNLBILLING | 4Nmu Terminal Billing Fee |
| FEE | FPRMTN | Promotion |
| FEE | FCARDSGNPRDCT | Carrier Designs / Products |
| FEE | FSPLTYPRDCT | Specialty Product |
| FEE | FSPLTYSVC | Specialty Services |
| FEE | FINTRNTCMPSSMNTH | Intrnet Cmpssf/E Monthly Fee |
| FEE | FSHPNG | Shipping |
| FEE | FINTRNTCMPSSSETUP | Intrnet Cmpssf/E Setup Fee |
| FEE | F4SUUTRMNLBILLING | 4Suu Terminal Billing |
| FEE | FINTRNTCMPSSINSTL12 | Intrnet Cmpssf/E Instlmt Fee12 |
| FEE | FINTRNTCMPSSINSTL24 | Intrnet Cmpssf/E Instlmt Fee24 |
| FEE | FINTRNTCMPSSINSTL36 | Intrnet Cmpssf/E Instlmt Fee36 |
| FEE | FTRSTCOMMPASSTHRU | Trust Commerce Pass Thru Fees |
| FEE | F4VAMTRMNLBILLING | 4Vam Terminal Billing |
| FEE | F4VCMTRMNLBILLING | 4Vcm Terminal Billing Fee |
| FEE | FCRDBALSTATNOTIFVL | Crd Bal And Stat Notificatn Vl |
| FEE | FMWLTPROVISION | Mob Wlt Provisioning |
| FEE | FMWLTRMVPROVISION | Mob Wlt Remve Provision |
| FEE | FINTRNTMOBWLTPROVISION | Intrnet Mob Wlt Provisioning |
| FEE | FINTRNTRMVMOBWLTPROVISION | Intrnet Remve Mob Wlt Prov |
| FEE | FSCVVIRTACTWPROVISION | Scv Virt Activtion W Provision |
| FEE | FEANVIRTACTWPROVISION | Ean Virt Activtion W Provision |
| FEE | FBALTRTMTMNTH | Balance Treatment Monthly |
| FEE | F4WBSTRMNLBILLING | 4Wbs Terminal Billing Fee |
| FEE | FSVCARDPOSSFULFIN | Sv Card Pos Successful Fin |
| FEE | FPZYGCMNTH | Payeezy Giftcard Monthly Fee |
| FEE | FPZYGCSETUP | Payeezy Giftcard Setup Fee |
| FEE | FPZYGC12 | Payeezy Giftcard 12 |
| FEE | FPZYGC24 | Payeezy Giftcard 24 |
| FEE | FPZYGC36 | Payeezy Giftcard 36 |
| FEE | F41DCTRMNLBILLING | 41Dc Terminal Billing Fee |
| FEE | FSFTWRSUPPRT | Software Support(Multi) |
| FEE | FINTRNTACCLIVESUPPRT | Internet Access/Live Support |
| FEE | FAFFNLCLAUTH | Affn Local Auth Fee |
| FEE | FAFFNWATSAUTH | Affn Wats Auth Fee |
| FEE | FAFFN950AUTH | Affn 950 Auth Fee |
| FEE | FTSYSAUTH | Tsys Authorization Fee |
| FEE | FCASHSTN950AUTH | Cash Station 950 Auth Fee |
| FEE | FPULSELCLAUTH | Pulse Local Auth Fee |
| FEE | FPULSEWATSAUTH | Pulse Wats Auth Fee |
| FEE | FBMLPERITM | Bml Per Item Fee |
| FEE | FGOOGRETTXN | Google Return Trans Fee |
| FEE | FGLBLGTWYMSFTSECR | Global Gtway/Microsoft Secr |
| FEE | FMCCONVADJ | Mc Conv Fee Adj |
| FEE | FVICONVADJ | Visa Conv Fee Adj |
| FEE | FMCCONVADJCHGBK | Mc Conv Fee Adj Chgbk |
| FEE | FVICONVADJCHGBK | Visa Conv Fee Adj Chgbk |
| FEE | FMCCONVADJCHGBKF46H | Mc Conv Fee Adj Chgbk % |
| FEE | FVICONVADJCHGBKPRCNT | Visa Conv Fee Adj Chgbk % |
| FEE | FMCCONVADJRFND | Mc Conv Fee Adj Refund |
| FEE | FVICONVADJRFND | Visa Conv Fee Adj Refund |
| FEE | FMCCONVADJRFNDF46L | Mc Conv Fee Adj Refund % |
| FEE | FVICONVADJRFNDPRCNT | Visa Conv Fee Adj Refund % |
| FEE | FMCCONVADJCBREV | Mc Conv Fee Adj Chgbk Rev |
| FEE | FVICONVADJCHGBKREV | Visa Conv Fee Adj Chgbk Rev |
| FEE | FMCCONVADJCBREVF46P | Mc Conv Fee Adj Chgbk Rev% |
| FEE | FVICONVADJCHGBKREVPRCNT | Visa Conv Fee Adj Chgbk Rev % |
| FEE | FNGTWHST | Netgateway Host Fee |
| FEE | FSEWRKSTNMNTH | Se Workstation Monthly Fee |
| FEE | FTCKBASX | Basx Telecheck Fee |
| FEE | FNEWACCTBRDNG | New Account Boarding Fee |
| FEE | FPRDCRVWMGMT | Periodic Review Management Fee |
| FEE | FAUDITCMPLNC | Audit/Compliance Fee |
| FEE | FMTRLDSCRP | Material Discrepancy Fee |
| FEE | FBRDNGCMPLNC | Boarding Compliance Fee |
| FEE | FMNTRINGCMPLNC | Monitoring Compliance Fee |
| FEE | FFLNGWTHDRWLSMS | Filing Withdrawal Sms |
| FEE | FRTMEDISCACCTUPDSVC | Rtime Disc Acct Updtr Srvc Fee |
| FEE | FAUTHMCDECLDRTR | Auth Opt Mc Decld Retry Fee |
| FEE | FAUTHDISCDECLDRTR | Auth Opt Disc Decld Retry Fee |
| FEE | FMRCHEXCLBNDL | Merchant Exclusives Bundle |
| FEE | FDSVINFL | Ds Fee Non Fuel Vi |
| FEE | FDSLACXBRDR2 | Ds Lac Cross Border Fee 2 |
| FEE | FHDCLACXBRDR2 | Hdc Lac Cross Border Fee 2 |
| FEE | FSCVVIRTACTVNPROV | Scv Virt Activtion W Provisn % |
| FEE | FEANVIRTACTVNPROV | Ean Virt Activtion W Provisn % |
| FEE | FSTRDVLCARDTXN | Stored Val Crd Trans % |
| FEE | FSTRDVLCARDINTRNTTXN | Stored Val Crd Trans Intnet % |
| FEE | FSTRDVLCARDBTCHTXN | Stored Val Crd Trans Batch % |
| FEE | FSTRDVLCARDRDMPTN | Stored Val Crd Redemption % |
| FEE | FSTRDVLCARDRDMPTNUNLCK | Stored Val Crd Redmptn Unlck % |
| FEE | FSTRDVLCARDNOPOS | Stored Val Crd Non Pos % |
| FEE | F50AATRMNLBILLING | 50Aa Terminal Billing Fee |
| FEE | FHPRP5000BASEUNT | Hp Rp5000 Base Unit |
| FEE | F50DCTRMNLBILLING | 50Dc Terminal Billing Fee |
| FEE | FFD50TI | Fd50Ti |
| FEE | FOMNI3350VERIX21 | Omni 3350 Verix 2.1 |
| FEE | FEFSIC | Efs Interchange Fee |
| FEE | FTCKIC | Tcheck Interchange Fee |
| FEE | FIOLESSOFLEETIC | Iol Esso Fleet Interchange Fee |
| FEE | FEMPLCSIC | Em Plcs Interchange |
| FEE | FPVTLBLRTL | Private Label Retailer Fee |
| FEE | FFLEETONERTL | Fleetone Retailer Fee |
| FEE | FSVSRTL | Svs Retailer Fee |
| FEE | FVALLNKRTL | Valuelink Retailer Fee |
| FEE | FCONNSETUP | Connectivity Set Up Fee |
| FEE | FCONNMNTH | Connectivity Monthly Fee |
| FEE | FDBTMLOTHRITMS | Magicline Debit Other Itms Fee |
| FEE | FACCELDBOTHITMS | Accel Debit Other Items Fee |
| FEE | FDISCOTHRVOL | Discover Other Volume Fee |
| FEE | FMACOTHRVOL | Mac Other Volume Fee |
| FEE | FMRCHRWDRBT | Merchant Reward Rebate |
| FEE | FDSMCFUEL | Ds Fee Fuel Mc |
| FEE | FMSTRNETDSCNT | Maestro Net Discount Fee |
| FEE | FPULSENETDSCNT | Pulse Net Discount Fee |
| FEE | FCASHSTNNETDSCNT | Cash Station Net Discount Fee |
| FEE | FNETDSCNTML | Magicline Net Discount Fee |
| FEE | FPULSEDBTSLS | Pulse Debit Sale Fee |
| FEE | FHDCFLVITXN | Hdc Fl Vi Trn |
| FEE | FMERCHALRTVAT | Merchant Alert Vat Fee |
| FEE | FMERCHALRTBNDLVAT | Merchant Alert Bundle Vat Fee |
| FEE | FWEBLNCRVAT | Web Launcher Vat Fee |
| FEE | FMNTHVAT | Monthly Fee Vat |
| FEE | FPCIDSSMGMTVAT | Pci Dss Management Vat Fee |
| FEE | FXBORDERCAN | Can Cross Border Fee |
| FEE | FXBORDERNOCAN | Can Cross Border Fee, Noncan |
| FEE | FWRLSTRMNLDNLD | Wireless Terminal Download Fee |
| FEE | FXBORDERAPLCL | Ap Cross Border Fee, Local |
| FEE | FVIRTTRMNLACTVN | Virtual Terminal Activation |
| FEE | FSIGDBTMQCHGBKTXN | Sig Debit Mid Qual Chrgbk Tran |
| FEE | FVIPRCLVLIC | Visa Proc Lvl Interchange Fee |
| FEE | FSIGDBTNQCHGBKTXN | Sig Debit Non Qual Chrgbk Tran |
| FEE | FSTARCLRTXN | Star Clearing Trans Fee |
| FEE | FAMXNQREVTXN | Amex Non Qual Revrsal Tran Fee |
| FEE | FMCWRLDCHGBKDSCNT | Mc World Chrgbk Discount |
| FEE | FMCWRLDREVDSCNT | Mc World Reversal Discount |
| FEE | FVIRWRDCHGBKDSCNT | Vi Reward Chrgbk Discount |
| FEE | FMCWRLDMQCHGBKDSCNT | Mc World Mid Qual Chrgbk Disc |
| FEE | FMCWRLDMQREVDSCNT | Mc World Mid Qual Rev Disc |
| FEE | FVIRWRDMQCHGBKDSCNT | Vi Reward Mid Qual Chrgbk Disc |
| FEE | FVIRWRDMQRVSLDSCNT | Vi Reward Mid Qual Rev Disc |
| FEE | FMCWRLDNQCHGBKDSCNT | Mc World Non Qual Chrgbk Disc |
| FEE | FVIRWRDNQCHGBKDSCNT | Vi Reward Non Qual Chrgbk Disc |
| FEE | FVIRWRDNQRVSLDSCNT | Vi Reward Non Qual Rev Disc |
| FEE | FDNRSCARD | Diners Card Fee |
| FEE | FAMXCARD | Amex Card Fee |
| FEE | FDSCCARD | Discover Card Fee |
| FEE | FMACDBTCARD | Mac Debit Card Fee |
| FEE | FNYCEDBTCARD | Nyce Debit Card Fee |
| FEE | FPULSEDBTCARD | Pulse Debit Card Fee |
| FEE | FDSPREMCHGBKDSCNT | Ds Premium Chargeback Discount |
| FEE | FDSPREMRVSLDSCNT | Ds Premium Reversal Discount |
| FEE | FDSPREMMQCHGBKDIS | Ds Prem Midqual Chrgbck Discnt |
| FEE | FDSPRMMQRVSLDISC | Ds Prem Midqual Revrsal Discnt |
| FEE | FDSPREMNQCHGBKDIS | Ds Prem Nonqual Chrgbck Discnt |
| FEE | FDSPREMCHGBKTXN | Ds Premium Chrgbck Trans Fee |
| FEE | FDSPREMRVSLTXN | Ds Premium Reversal Trans Fee |
| FEE | FDSPREMMQCHGBKTXN | Ds Prem Midql Chrgbck Trns Fee |
| FEE | FDSPREMMQRVSLTXN | Ds Prem Midql Revrsal Trns Fee |
| FEE | FDSPREMNQCHBGKTXN | Ds Prem Nonql Chrgbck Trns Fee |
| FEE | FDSPREMNQRVSLTXN | Ds Prem Nonql Revrsal Trns Fee |
| FEE | FDSFUELVI | Ds Fee Fuel Vi |
| FEE | FDSVIINTLSVC | Ds Visa Intl Service Fee |
| FEE | FDSFLVITXN | Ds Fl Vi Trn |
| FEE | FVIHDCINTLSVC | Hdc Visa Intl Service Fee |
| FEE | FHDCNFVITXN | Hdc Nf Vi Trn |
| FEE | FMCELTRNCBCRD | Mastercard Elec. Bcard Fee |
| FEE | FVISTDBSNSCARD | Visa Std Businesscard Rate |
| FEE | FVINQ | Visa Non Qualified Rate |
| FEE | FMCSTNDRATE | Mastercard Standard Rate |
| FEE | FMCSTNDFRGNRATE | Mastercard Std Foreign Rate |
| FEE | FMCNQRATE | Mastercard Non Qualified Rate |
| FEE | FWCPAUTH | Wcp Authorization Fee |
| FEE | FWCPSVC | Wcp Service Fee |
| FEE | FWCPRETTXN | Wcp Return Transaction Fee |
| FEE | FPVTLBLCHGBKDSCNT | Private Label Chargeback Disc |
| FEE | FPVTLBLRVSLDSCNT | Private Label Reversal Disc |
| FEE | FGENPISLSDSCNT | Gen Pl Sales Discount |
| FEE | FGENPIRATEDSCNT | Gen Pl Return Discount |
| FEE | FVIELECCHPSCHG | Visa Electron Chip Serv Chg |
| FEE | FVIELECCHPRFND | Visa Electron Chip Refunds |
| FEE | FMCPVTLBLSLSDSCNT | Mc Private Lbl Sales Discount |
| FEE | FMCPVTLBLRETDSCNT | Mc Private Lbl Returns Disc |
| FEE | FMCPVTLBLCHGBKDSCNT | Mc Private Lbl Chrgbck Disc |
| FEE | FMCPVTLBLREVDSCNT | Mc Private Lbl Reversal Disc |
| FEE | FFSBEDC0150GRID10 | Fsb Edc Wats 0150 Grid10 |
| FEE | F8CMWTRMNLBILLING | 8Cmw Terminal Billing Fee |
| FEE | F8DOCTRMNLBILLING | 8Doc Terminal Billing Fee |
| FEE | FDSNFLVITXN | Ds Nfl Vi Trn |
| FEE | F8GPRTRMNLBILLING | 8Gpr Terminal Billing Fee |
| FEE | FHDCLACAPINTLACQR | Hdc Lac/Ap Intl Acq Fee |
| FEE | FNRT8400TRMNLBILLING | Nurit 8400 Terminal Billing |
| FEE | FSLSDSCNTRATE | Sales Discount Rate |
| FEE | FDNRSMCRETDSCNT | Diners (Mc)Returns Discount |
| FEE | FSIGDBTMQCHGBKDSCNT | Sig Debit Mid Qual Chrgbk Disc |
| FEE | FSIGDBTNQCHGBKDSCNT | Sig Debit Non Qual Chrgbk Disc |
| FEE | FDBTCHGBKDSCNT | Debit Chargeback Discount |
| FEE | FDBTRVSLDSCNT | Debit Reversal Discount |
| FEE | FVICHKCARDCHGBKDSCNT | Visa Check Card Chrgbck Disc |
| FEE | FVICHKCARDREVDSCNT | Visa Check Card Reversal Disc |
| FEE | FVIPYMTDSCNTRATE | Vi Payment Discount Rate |
| FEE | FVIFNDDSCNTRATE | Vi Funding Discount Rate |
| FEE | FWLSNWSTELTRNC | Wells/Norwest Electronic |
| FEE | FWLSNWSTMAILTELEPHN | Wells/Norwest Mail/Telephone |
| FEE | FWLSNWSTTOUCHTONE | Wells/Norwest Touch Tone |
| FEE | FWLSNWSTPPR | Wells/Norwest Paper |
| FEE | FINTRNTGRID | Internet Grid |
| FEE | FSKYBNKGRID | Sky Bank Grid |
| FEE | FWFBINETGRID | Wfb Internet Grid |
| FEE | FMCCATRETDSCNT | Mc Cat Returns Discnt |
| FEE | FVICATRETDSCNT | Vi Cat Returns Discnt |
| FEE | FFIB21735000004 | Fib 2173/5000/004 |
| FEE | FFIB47510000051 | Fib 4751/0000/051 |
| FEE | FFIB14870000 | Fib 1487/0000 |
| FEE | FWACHOVIAGRRD009 | Wachovia Grid 009 |
| FEE | F9C06TRMNLBILLING | 9C06 Terminal Billing Fee |
| FEE | FSNTRUST09520019 | Suntrust 0952/0019 |
| FEE | FDSLACAPINTLACQ | Ds Lac/Ap Intl Acq Fee |
| FEE | FDYMICMSC | Dynamic Msc 9L4 |
| FEE | F9PCITRMNLBILLING | 9Pci Terminal Billing Fee |
| FEE | FJEWELERS | Jewelers |
| FEE | FDPSTCAPTLRTL | Deposit Capture/Retail |
| FEE | FDPSTCAPTLMOTO | Deposit Capture/Moto |
| FEE | FSPRMKTOVR2MM | Supermarket Over 2Mm |
| FEE | FVINETRESTCAPT | Visanet Rest. Capture |
| FEE | FDPSTCAPTR | Deposit Capture |
| FEE | FBRNTGRID0003 | Barnett Grid # 0003 |
| FEE | FBRNTGRID0007 | Barnett Grid # 0007 |
| FEE | FWFBRTL | Wfb Retail |
| FEE | FBOHGRID926 | Bank Of Hawaii Grid |
| FEE | FWLSRTL | Wells Retail |
| FEE | FWLSMAILTELEPHNORDR | Wells Mail/Telephone Order |
| FEE | FWLSHTLCARRNTL | Wells Hotel/Car Rental |
| FEE | FNWSTGRID11FDRDMTH8001 | Nwst Grid #11/ Fdr Dmeth 8 001 |
| FEE | FNWSTGRID26FDRDMTH8008 | Nwst Grid #26/ Fdr Dmeth 8 008 |
| FEE | FONLNDBTMIN | Online Debit Minimum Fee |
| FEE | FGOOGSUPPRTDBTACCTVRFY | Goog Support Debit Acct Verify |
| FEE | FPERIPHRLEQP | Peripheral Equipment |
| FEE | FDRCTDBFRNCVAL | Directdb France Val |
| FEE | FDRCTDBFRNCSTL | Directdb France Stl |
| FEE | FDRCTDBITLVAL | Directdb Italy Val |
| FEE | FDRCTDBBELVAL | Directdb Belgium Val |
| FEE | FRTBTGRMNYVAL | Rtbt Germany Val |
| FEE | FRTBTGRMNYSTL | Rtbt Germany Stl |
| FEE | FRTBTNTHLNDSTL | Rtbt Netherlands Stl |
| FEE | FRTBTNTHLNDREF | Rtbt Netherlands Ref |
| FEE | FVIQLYECOMEU | Visa Qtrly Ecommerce Fee Eu |
| FEE | FVIINTLACQEU | Visa Intl Acquiring Fee Eu |
| FEE | FVIINTLECOMEU | Visa Intl Ecommerce Fee Eu |
| FEE | FVIBTCHAUTH0HC | Visa Batch Authorization Fee |
| FEE | FVIVOICEISSREFF | Visa Voice Issuer Referral Fee |
| FEE | FJCBVOICEISSRRFRL | Jcb Voice Issuer Referral Fee |
| FEE | FMCBTCHAUTH | Mastercard Batch Auth Fee |
| FEE | FMCVOICEISSREFF | Mc Voice Issuer Referral Fee |
| FEE | FMSTRBTCHAUTH | Maestro Batch Auth Fee |
| FEE | FMSTRVOICEAUTH | Maestro Voice Auth Fee |
| FEE | FMSTRVOICEISSRRFRL | Maestro Voice Issuer Ref Fee |
| FEE | FMSTRSOLOBTCHAUTH | Maestro Solo Batch Auth Fee |
| FEE | FMSTRSOLOLCLAUTH | Maestro Solo Local Auth Fee |
| FEE | FMSTRSOLOVOICEAUTH | Maestro Solo Voice Auth Fee |
| FEE | FMSTRSOLOVOICEISSRRFRL | Maestro Solo Voice Iss Ref Fee |
| FEE | FSOLOBTCHAUTH | Solo Batch Authorization Fee |
| FEE | FSOLOLCAUTH | Solo Local Authorization Fee |
| FEE | FSOLOVOICEAUTH | Solo Voice Authorization Fee |
| FEE | FSOLOVOICEISSRRFNDAUTH | Solo Voice Issuer Ref Auth Fee |
| FEE | FSOLOCHPBTCHAUTH | Solo Chip Batch Auth Fee |
| FEE | FSOLOCHPLCAUTH | Solo Chip Local Auth Fee |
| FEE | FSOLOCHPVOICEAUTH | Solo Chip Voice Auth Fee |
| FEE | FSOLOCHPVOICEISSRRFND | Solo Chip Voice Iss Ref Fee |
| FEE | FVIELECBTCHAUTH | Visa Electron Batch Auth Fee |
| FEE | FVIELECLCLAUTH | Visa Electron Local Auth Fee |
| FEE | FVIELECVOICEAUTH | Visa Electron Voice Auth Fee |
| FEE | FVICHIPVOICISSREF | Visa Chip Voice Iss Ref Fee |
| FEE | FVIDBTLCLAUTH | Visa Debit Local Auth Fee |
| FEE | FVIDBTVOICEAUTH | Visa Debit Voice Auth Fee |
| FEE | FVIDBTVOICEISSREF | Visa Debit Voice Iss Ref Fee |
| FEE | FVIPCARDAUTH | Visa Purchasing Card Auth Fee |
| FEE | FVIPCARDLCLAUTH | Visa Purch Card Local Auth Fee |
| FEE | FVIPCARDVOICEAUTH | Visa Purch Card Voice Auth Fee |
| FEE | FVIPURCDVOICEISSREF | Visa Pur Cd Voice Iss Ref Fee |
| FEE | FVIDBTCHPLCLAUTH | Visa Debit Chip Local Auth Fee |
| FEE | FVIDBTCHPVOICEAUTH | Visa Debit Chip Voice Auth Fee |
| FEE | FVIDBTCHPVOIISSR | Visa Debit Chp Voi Iss Ref Fee |
| FEE | FVICHIPBTCHAUTH | Visa Chip Batch Auth Fee |
| FEE | FVICHIPLCLAUTH | Visa Chip Local Auth Fee |
| FEE | FVICHIPVOIISSREFF | Visa Chip Voi Iss Referral Fee |
| FEE | FMCCHPBTCHAUTH | Mastercard Chip Batch Auth Fee |
| FEE | FMCCHPLCLAUTH | Mastercard Chip Local Auth Fee |
| FEE | FMCCHPVOICEAUTH | Mastercard Chip Voice Auth Fee |
| FEE | FMCCHPVOICEISSREF | Mc Chip Voice Issuer Ref Fee |
| FEE | FMCPCARDAUTH | Mastercard Purch Card Auth Fee |
| FEE | FMCPCARDLCLAUTH | Mc Purchase Cd Local Auth Fee |
| FEE | FMCPCARDVCAUTH | Mc Purchase Cd Voice Auth Fee |
| FEE | FMCPCARDVOICEISSR | Mc Purch Crd Voice Iss Ref |
| FEE | FDNRSVOICEISSREF | Diners Voice Issuer Ref Fee |
| FEE | FDNRSREVTXN | Diners Reversal Trans Fee |
| FEE | FVINQRFNDTEXPREM | Visa Nq Refund T/Fee Ex.Prem |
| FEE | FVICHIPNQRFNDTFEXPREM | Visachip Nq Refund T/F Ex.Prem |
| FEE | FMCNQRFNDTXNPREM | Mc Nq Rfnd Trans Fee (Prem) |
| FEE | FMCCHPNQRFNDTPREM | Mc Chip Nq Rfnd T/Fee (Prem) |
| FEE | FVICHPNQRFNDTPRM | Visachip Nqrefundt/Fee(Prem) |
| FEE | FMCNQRFNDTXNEXPREM | Mc Nq Rfnd Trans Fee Ex. Prem |
| FEE | FMCCHPNQRFNDTEPREM | Mc Chip Nq Rfnd T/Fee Ex.Prem |
| FEE | FVICOMMRFNDTXNCNTLSEXBDR | Vi Comm Ref Tx C/Les(Ex B Dr) |
| FEE | FMCCHPNQRFNDCLESS | Mc Chip Nq Rfnd Cnt Less |
| FEE | FMCPURCRDNQRFNDCLESS | Mc Purch Crd Nq Rfnd Cnt Less |
| FEE | FMCCHPRFNDTRNCLESS | Mc Chip Rfnd Trn Cnt Less |
| FEE | FMCCHPNQRFNDTRNCLESS | Mc Chip Nq Rfnd Trn Cnt Less |
| FEE | FMCPCARDSLSTRNCLESS | Mc Purch Crd Sls Trn Cnt Less |
| FEE | FMCPCARDRFDTRNCLESS | Mc Purch Crd Rfd Trn Cnt Less |
| FEE | FMCPCARDNQRFDTRNCLESS | Mc Prch Cd Nq Rfd Trn Cnt Less |
| FEE | FVPAYQLSLSTXNCHGCLESS | Vpay Qual Sls Trn Chg Cnt Less |
| FEE | FVPAYQLRFDTXNCHGCLESS | Vpay Qual Rfd Trn Chg Cnt Less |
| FEE | FVPAYNQSLSCHRGCLESS | Vpay Nq Sls Chrg Cnt Less |
| FEE | FVICHPRFNDTXNCLESS | Vi Chip Rfnd Trn Cnt Less |
| FEE | FVICHPNQRFDTXNCLESS | Vi Chip Nq Rfd Trn Cnt Less |
| FEE | FVIPCARDNQSLSTXNCNTLS | Vi Prch Cd Nq Sls Trn Cnt Less |
| FEE | FVIPCARDNQRFNDTXNCNTLS | Vi Prch Cd Nq Rfd Trn Cnt Less |
| FEE | FVIPCARDSLSTXNCNTLS64K | Vi Purch Crd Sls Trn Cnt Less |
| FEE | FVIPCARDRFNDTXNCNTLS | Vi Purch Crd Rfd Trn Cnt Less |
| FEE | FVICOMMCRDRFNDTXNCNTLS | Vi Comm Crd Rfnd Trn Cnt Less |
| FEE | FVIELTRNCDRSLSTXNCNTLS | Vi Electrn Dr Sls Trn Cnt Less |
| FEE | FVIELTRNCDRRFNDTXNCNTLS | Vi Electrn Dr Rfd Trn Cnt Less |
| FEE | FVIELTRNCDRNQSLSTXNCNTLS | Vi Elect Dr Nq Sl Trn Cnt Less |
| FEE | FVIELTRNCDRNQRFNDTXNCNTLS | Vi Elct Dr Nq Rfd Trn Cnt Less |
| FEE | FMSTRNQSLSTXN | Maestro Non Qual Sls Trans Fee |
| FEE | FMSTRNQRFNDTXN | Maestro Non Qual Refund Trn Fe |
| FEE | FSOLONQSLSTXN | Solo Non Qual Sales Trans Fee |
| FEE | FVIPCARDNQRFNDT | Visa Purch Card Nq Rfnd T/Fee |
| FEE | FMSTRNQRFND | Maestro Non Qual Refunds |
| FEE | FSOLONQSVCCHG | Solo Non Qual Service Charge |
| FEE | FSOLONQRFND | Solo Non Qual Refunds |
| FEE | FVIPCARDNQSRVCHG | Visa Purchase Card Nq Srv Chg |
| FEE | FVIPCARDNQRFND | Visa Purchase Card Nq Refunds |
| FEE | FMCPCARDNQRFND | Mc Purchase Card Nq Refunds |
| FEE | FMCPCARDNQRFNDT | Mc Purchase Card Nq Rfnd T/Fee |
| FEE | FMCRFNDTXNPREM | Mc Refunds Trans Fee (Prem) |
| FEE | FMCCHPRFNDTXNPREM | Mc Chip Rfnd Trans Fee (Prem) |
| FEE | FVIRFNDTXNPRM | Visa Refunds Trans Fee(Prem) |
| FEE | FVIRFNDTXNEXPREM | Visa Refunds Trans Fee Ex.Prem |
| FEE | FMCRFNDTXNEXPREM | Mc Refunds Trans Fee Ex. Prem |
| FEE | FMCCHPREFTXNEPREM | Mc Chip Ref Trans Fee Ex.Prem |
| FEE | FVICOMMCARDRFNDT | Visa Comm Card Rfnd T/Fee |
| FEE | FVIPCARDRFNDT | Visa Purchase Card Rfnd T/Fee |
| FEE | FAMXAUTH06S | Amex Auths |
| FEE | FAMXVOICEAUTH0YE | Amex Voice Authorization Fee |
| FEE | FCNCLTN | Cancellation Fee |
| FEE | FMQDSCNT | Mid Qual Discount |
| FEE | FMQDSCNT80D | Mid Qual Discount |
| FEE | FQDSCNTF21F | Qual Discount |
| FEE | FQDSCNTF80F | Qual Discount |
| FEE | FAUTHAUT | Authorizer Fee |
| FEE | FAMXINTCG | American Express Interchange |
| FEE | FMCICFBPC | Mc Interchange Fee |
| FEE | FDSCVINTCG | Discover Interchange |
| FEE | FDBTINTCG | Debit Interchange Fee |
| FEE | FPREPAIDCASHCARDINTCG | Prepaid Cash Card Intrchg Fee |
| FEE | FFLEETONEIC | Fleet One Intrchg Fee |
| FEE | FEBTINTCG | Ebt Interchange Fee |
| FEE | FVIICBPV | Visa Interchange Fee |
| FEE | FWEXINTCG | Wex Interchange Fee |
| FEE | FICVRFY | Ic Verify |
| FEE | FHYPCMPRNTRBILLING | Hypercom Printer Billing |
| FEE | FHYPCMPRNTRBILLINGCP7 | Hypercom Printer Billing |
| FEE | FHYPRCOMTRMNLBILLING | Hypercom Terminal Billing |
| FEE | FHYPRCOMTRMNLBILLINGFCT7 | Hypercom Terminal Billing |
| FEE | FTRMNLBILLINGFDEB | Terminal Billing |
| FEE | FICVRFYD07 | Ic Verify |
| FEE | FHYPRCOMTRMNLBILLINGFD08 | Hypercom Terminal Billing |
| FEE | FFNDINGADJD46 | Funding Adjustment |
| FEE | FDPOSTADJ | Deposit Adjustment |
| FEE | FFNDINGADJD53 | Funding Adjustment |
| FEE | FSTLMNTADJFD54 | Settlement Adjustment |
| FEE | FRVSLDUPCRDT | Reverse Duplicate Credit |
| FEE | FDSCVCHGBKD71 | Discover Chargeback |
| FEE | FARBTRATION | Arbitration Fee |
| FEE | FCRDTADJ | Credit Adj. Fee |
| FEE | FGCLCLAUTH | Gift Card Local Auth Fee |
| FEE | FGCAUTHG91 | Gift Card Authorizarion Fee |
| FEE | FTELNMACHUB10PKHDC | Tellan Mac Hub 10 Pk Hdc |
| FEE | FMCSLSTXNK01 | Mastercard Sales Trans Fee |
| FEE | FVISLSTXNK05 | Visa Sales Trans Fee |
| FEE | FDNRSSLSTXN | Diners Sales Trans |
| FEE | FICVRFYVLCD | Ic Verify Valcode |
| FEE | FFUTUREFL55 | Future |
| FEE | FFUTUREFL56 | Future |
| FEE | FMISCADJMAB | Misc Adjustment |
| FEE | FSDSMA1 | Sds |
| FEE | FSDSRVSL | Sds Reversal |
| FEE | FCRDTADJM02 | Credit Adjustment |
| FEE | FADJOLWO | Adjustment Olwo |
| FEE | FMCNOAUTH2NDCHGBKFM2C | No Auth 2Nd Cb Mc Fee |
| FEE | FDPOSTADJM3A | Deposit Adjustment |
| FEE | FPERIPHRLBILLINGM3C | Peripheral Billing |
| FEE | FFNDINGADJ | Funding Adjustment |
| FEE | FFNDINGADJFM3E | Funding Adjustment |
| FEE | FFNDINGADJFM3F | Funding Adjustment |
| FEE | FFNDINGADJFM3G | Funding Adjustment |
| FEE | FSTLMNTADJFM3H | Settlement Adjustment |
| FEE | FSTLMNTADJFM3I | Settlement Adjustment |
| FEE | FSTLMNTADJFM3J | Settlement Adjustment |
| FEE | FSTLMNTADJFM3K | Settlement Adjustment |
| FEE | FSTLMNTADJFM3L | Settlement Adjustment |
| FEE | FSTLMNTADJFM3M | Settlement Adjustment |
| FEE | FSTLMNTADJFM3N | Settlement Adjustment |
| FEE | FSTLMNTADJFM3P | Settlement Adjustment |
| FEE | FSTLMNTADJFM3Q | Settlement Adjustment |
| FEE | FSTLMNTADJFM3R | Settlement Adjustment |
| FEE | FACHRJCTFM3T | Ach Reject |
| FEE | FACHRJCTFM3U | Ach Reject |
| FEE | FACHRJCTFM3V | Ach Reject |
| FEE | FACHRJCTFM3W | Ach Reject |
| FEE | FACHRJCTFM3X | Ach Reject |
| FEE | FREPRGMING | Reprogramming Fee |
| FEE | FADJOLWOM40 | Adjustment Olwo |
| FEE | FCHGBKM6D | Chargeback(S) |
| FEE | FMISCADJM6G | Miscellaneous Adjustment |
| FEE | FMCPREAUTHFOEE | Mc Pre Auth Fee |
| FEE | FVFONETRMNLBILLING | Verifone Terminal Billing |
| FEE | FTRMNLBILLINGFO10 | Terminal Billing |
| FEE | FVFONETRMNLBILLINGFO38 | Verifone Terminal Billing |
| FEE | FTRMNLBILLINGFO90 | Terminal Billing |
| FEE | FPBASTRMNLBILLING | Pbas Terminal Billing Fee |
| FEE | FPBASTRMNLBILLINGFPBS | Pbas Terminal Billing Fee |
| FEE | FVFONETRMNLBILLINGFPNC | Verifone Terminal Billing |
| FEE | FPPSTRMNLBILLING | Pps9 Terminal Billing Fee |
| FEE | FPP9TRMNLBILLING | Pps9 Terminal Billing Fee |
| FEE | FTRMNLBILLINGFP7E | Terminal Billing |
| FEE | FRITTRMNLBILLING | Rit3 Terminal Billing Fee |
| FEE | FRI3TRMNLBILLING | Rit3 Terminal Billing Fee |
| FEE | FSTLMTSTMT | Settlement Statement Fee |
| FEE | FTCTRMNLBILLING | T Cc Terminal Billing Fee |
| FEE | FTCCTRMNLBILLING | T Cc Terminal Billing Fee |
| FEE | FTRMNLBILLINGFTEM | Term Terminal Billing Fee |
| FEE | FTRMNLBILLINGFTER | Term Terminal Billing |
| FEE | FTCKSETUPFT21 | Telecheck Setup Fee |
| FEE | FHYPRCOMTRMNLBILLINGFFT7E | Hypercom Terminal Billing |
| FEE | FFUTUREFU55 | Future |
| FEE | FFUTUREFU56 | Future |
| FEE | FLYLTACCTONFILE | Loyalty Accounts On File |
| FEE | FTRMNLBILLINGFVA8 | Terminal Billing Fee |
| FEE | FICVRFYVLCDVRO | Ic Verify Valcode |
| FEE | FANNULFEESCRTYBNDL | Annual Fee Security Bundle |
| FEE | FGCLCLAUTH0M3 | Gift Card Local Auth Fee |
| FEE | FMCDBTRETTXNF1B1 | Mc Debit Returns Trans Fee |
| FEE | FVIDBTRETTXN1B5 | Vi Debit Returns Trans Fee |
| FEE | FTRMNLBILLINGF12O | Terminal Billing Fee |
| FEE | FSDSRVSL2AD | Sds Reversal |
| FEE | FLYLT | Loyalty Fee |
| FEE | FMQDSC21J | Mid Qual Discount |
| FEE | FLYLT3AJ | Loyalty |
| FEE | FCLNTSOTNPKG | Client Solution Package |
| FEE | FCLNTSOLNPKG3IC | Client Solution Package |
| FEE | FTELNMACHUB5PKTDC | Tellan Mac Hub 5Pk Tdc |
| FEE | FFLEETONEIC50Z | Fleetone Interchange Fee |
| FEE | FVOYICF531 | Voyager Interchange Fee |
| FEE | FVOYICF532 | Voyager Interchange |
| FEE | FWEXINTCG535 | Wex Interchange Fee |
| FEE | FFUTUREF54B | Future |
| FEE | FFUTUREF54C | Future |
| FEE | FADJ59Z | Adjustment Fee |
| FEE | FMCSLSTXN6B1 | Mastercard Sales Trans Fee |
| FEE | FMCCRDTTXN6B2 | Mastercard Credits Trans Fee |
| FEE | FVISLSTXN6B5 | Visa Sales Transaction Fee |
| FEE | FVICRTXN6B6 | Visa Credits Trans Fee |
| FEE | FMCPCARDSRVCHRGCLESS | Mc Purch Crd Srv Chrg Cnt Less |
| FEE | FDSCVSLSTXN7B1 | Discover Sales Trans Fee |
| FEE | FDSCVCRDTTXN7B3 | Discover Credits Trans Fee |
| FEE | FDSCVDBTRETTXN | Discover Debit Returns Trans |
| FEE | FEBTTXN79M | Ebt Transaction |
| FEE | FPNCNJ81567000333 | Pnc New Jersey 8156/7000 333 |
| FEE | FPNCNJ81567000444 | Pnc New Jersey 8156/7000 444 |
| FEE | FMQDSCNT80Q | Mid Qual Discount |
| FEE | FNWSTGRID85N | Norwest Grid 85N |
| FEE | FNWSTGRID85O | Norwest Grid 85O |
| FEE | FVOLDSCNT9L0 | Vol. Discount 9L0 |
| FEE | FVOLDSCNT9L3 | Vol. Discount 9L3 |
| FEE | FVOLDSCNT9L5 | Vol. Discount 9L5 |
| FEE | FWLSFIBGRD94X | Wells/Fib Grid 94X |
| FEE | FWLSFIBGRD94Y | Wells/Fib Grid 94Y |
| FEE | FWLSFIBGRD94Z | Wells/Fib Grid 94Z |
| FEE | FDRCTDBITLSTL | Directdb Italy Stl |
| FEE | FDRCTDBITLREF | Directdb Italy Ref |
| FEE | FDRCTDBITLSTLFOAX | Directdb Italy Stl |
| FEE | FDRCTDBITLREFFOAY | Directdb Italy Ref |
| FEE | FVILCLAUTH0HD | Visa Local Authorization Fee |
| FEE | FVIVOICEAUTH0HE | Visa Voice Authorization Fee |
| FEE | FJCBLCLAUTH0ID | Jcb Local Authorization Fee |
| FEE | FJCBVOICEAUTH0IE | Jcb Voice Authorization Fee |
| FEE | FMCLCLAUTH0JD | Mastercard Local Auth Fee |
| FEE | FMCVOICEAUTH0JE | Mastercard Voice Auth Fee |
| FEE | FMSTRNQAUTH | Maestro Local Auth Fee |
| FEE | FDNRSCTCHAUTH | Diners Batch Authorization Fee |
| FEE | FDNRSLCLAUTH | Diners Local Authorization Fee |
| FEE | FDNRSVOICEAUTH | Diners Voice Authorization Fee |
| FEE | FAMXLCLAUTH0YD | Amex Local Authorization Fee |
| FEE | FDNRSCHGBKTXN | Diners Chrgbk Trans Fee |
| FEE | FPRFRPLCMTGLD | Preferred Placement Gold |
| FEE | FPRFRPLCMTSILV | Preferred Placement Silv |
| FEE | FPRFRPLCMTPLAT | Preferred Placement Plat |
| FEE | FVRTUALLPMOBLCNSE | Virtual Lp Mobile License Fee |
| FEE | FCREDEQNOTSOLCES | Cred For Equip Not Sold By Ces |
| FEE | FPERLYLTYSTLMNT | Per Loyalty Settlement |
| FEE | FPERLYLTYTXN | Per Loyalty Transaction |
| FEE | FBNKBILLBCKREF | Bank Billback Refund (Mc) |
| FEE | FSEWRKSTNSETUP | Se Workstation Set Up Fee |
| FEE | FRESONLSETUP | Re$Ource Online Set Up Fee |
| FEE | FENTLSURCHG | Entitlement Surcharge Fee |
| FEE | FNODSCRPFFOP | No Descriptor Available |
| FEE | FUAVETXN | U$Ave Transaction Fee |
| FEE | FUAVEOFFRADDNDM | U$Ave Offer Addendum Fee |
| FEE | FUVEOVRLYCRTN | U$Ave Overlay Creation Fee |
| FEE | FUAVECSTMRPRT | U$Ave Custom Reporting Fee |
| FEE | FUAVECRDHLDRDLVRY | U$Ave Cardholder Delivery Fee |
| FEE | FUAVEMRKTNG | U$Ave Marketing Fee |
| FEE | FUAVEMRKTNGFF08 | U$Ave Marketing Fee |
| FEE | FWELLS | Wells |
| FEE | FTAXEXMPT | Tax Exempt |
| FEE | FKAT1 | Kat1 |
| FEE | FSRPYFRAUDCNCLSVC | Surepay Fraud Cancel Svc |
| FEE | FTRLCHGBKREVMANUAL | Trailing Chrgbk Rev Fee Manual |
| FEE | FPYMTSHLDPERTXN | Payment Shield (Per Trans) |
| FEE | FPYMTSHLDMNTHLY | Payment Shield (Monthly Fee) |
| FEE | FPYMTSHLD | Payment Shield |
| FEE | FMRCHPRTCPTN | Merchant Participation |
| FEE | FMSTRCHGBKREV | Maestro Chargeback Reversal Dr |
| FEE | FPYMNT2 | Payment 2 |
| FEE | FMTROPYMNT | Metrocard Payment |
| FEE | FVICGHBK | Visa Chargebacks |
| FEE | FMACADJREVCUSTINQ | Mac Adj. Rev. Customer Inq. |
| FEE | FMOSTADJCUSTINQ | Most Adj. Customer Inquiry |
| FEE | FHNRADJCUSTINQ | Honor Adj. Customer Inquiry |
| FEE | FCASHSTNADJCUSTINQ | Cashstation Adj. Customer Inq |
| FEE | FCASHSTNADJREVINQ | Cashstation Adj. Rev. Inquiry |
| FEE | FBNKMTADJREVCUSTINQ | Bankmate Adj. Rev. Cust. Inq. |
| FEE | FSTRADJCUSTINQ | Star Adj. Customer Inquiry |
| FEE | FMSTRADJREVCUSTINQ | Maestro Adj. Rev. Customer Inq |
| FEE | FPULSEADJCUSTINQ | Pulse Adj. Customer Inquiry |
| FEE | FPULSEADJREVCUSTINQ | Pulse Adj. Rev. Customer Inq. |
| FEE | FALRTADJREVCUSTINQ | Alert Adj. Rev. Customer Inq. |
| FEE | FAFFNADJCUSTINQFM47 | Affn Adj. Customer Inquiry |
| FEE | FAFFNADJREVCUSTINQFM48 | Affn Adj. Rev. Customer Inq. |
| FEE | FMMRANNFPR3 | Mmr Annual 866 575 6567 |
| FEE | FMMRANNWELLEX | Mmr Annual Wellex 866 575 6567 |
| FEE | FPWRPCKOMNI380 | Power Pack Omni380 |
| FEE | FNODSCRPFSTD | No Descriptor Available |
| FEE | FMMRMNTH | Mmr Monthly 866 575 6567 |
| FEE | FMMRWELLEXMNTH | Mmr Wellex Mthly 866 575 6567 |
| FEE | FNODSCRPFUIC | No Descriptor Available |
| FEE | FWBVALSETUP | Webvalues Setup Fee |
| FEE | FWBVALRDMPTN | Webvalues Redemption Fee |
| FEE | FWBVALTXN | Webvalues Transaction Fee |
| FEE | FWBVALDSTRDTN | Webvalues Distribution Fee |
| FEE | FWBVALACCPTNC | Webvalues Acceptance Fee |
| FEE | FWBVALRPRT | Webvalues Reporting Fee |
| FEE | FWBVALMRKTN | Webvalues Marketing Fee |
| FEE | FWBVALSPPRT | Webvalues Support Fee |
| FEE | FWBVALMEDIA | Webvalues Media Fee |
| FEE | FWBVALMISC | Webvalues Miscellaneous Fee |
| FEE | FNODESCFU21 | No Decriptor Available |
| FEE | FUAVEACQPRCNT | U$Save Acquirer Percentage Fee |
| FEE | FNODESCAVBLFU23 | No Decriptor Available |
| FEE | FNODESCFU24 | No Decriptor Available |
| FEE | FNODESCFU25 | No Decriptor Available |
| FEE | FNODESCFU26 | No Decriptor Available |
| FEE | FNODESCAVBLFU27 | No Decriptor Available |
| FEE | FUAVENATSLSFLTTXN | U$Save Nat Sales Flat Transact |
| FEE | FUAVENATSLSFLTTXNFU42 | U$Save Nat Sales Flat Transact |
| FEE | FNODESCAVBLFU43 | No Decriptor Available |
| FEE | FNODESCFU44 | No Decriptor Available |
| FEE | FNODESCFU45 | No Decriptor Available |
| FEE | FUAVENATSLSFLTTXNFU46 | U$Save Nat Sales Flat Transact |
| FEE | FNODSCRPFU47 | No Descriptor Available |
| FEE | FNODESCFU61 | No Decriptor Available |
| FEE | FUAVEPRTNRSHPPRCNT | U$Save Partnership Percentage |
| FEE | FNODSCRPFU63 | No Descriptor Available |
| FEE | FNODSCRPFU64 | No Descriptor Available |
| FEE | FNODSCRPFU65 | No Descriptor Available |
| FEE | FNODSCRPFU66 | No Descriptor Available |
| FEE | FNODSCRPFU67 | No Descriptor Available |
| FEE | FGENPLSLSTXN | Gen Pl Sales Trn Fee |
| FEE | FGENPLCRTXN | Gen Pl Credit Trn Fee |
| FEE | FGENPLCHGBKTXN | Gen Pl Chg Back Trn Fee |
| FEE | FGENPLREVTXN | Gen Pl Reversal Trn Fee |
| FEE | FMNYSTN950AUTH | Money Station 950 Auth Fee |
| FEE | FMNYSTNLCLAUTH | Money Station Local Auth Fee |
| FEE | FMNYSTNWATSAUTH | Money Station Wats Auth Fee |
| FEE | FWEXLCLAUTHF0DT | Wright Express Local Auth Fee |
| FEE | FWEXWATSAUTHF0DU | Wright Express Wats Auth Fee |
| FEE | FWEX950AUTHF0DW | Wright Express 950 Auth Fee |
| FEE | FIKEA950AUTH | Ikea (P/L) 950 Auth Fee |
| FEE | FIKEALCLAUTH | Ikea (P/L) Local Auth Fee |
| FEE | FIKEAWATSAUTH | Ikea (P/L) Wats Auth Fee |
| FEE | FMAGICLINE950AUTH | Magicline 950 Auth Fee |
| FEE | FMAGICLINELCLAUTHF0F0 | Magicline Local Auth Fee |
| FEE | FMAGICLINEWATSAUTH | Magicline Wats Auth Fee |
| FEE | FACCELPREAUTH | Accel Preauth Fee |
| FEE | FHNRPREAUTH | Honor Preauth Fee |
| FEE | FINTRLNKPREAUTH | Interlink Preauth Fee |
| FEE | FMACPREAUTH | Mac Preauth Fee |
| FEE | FBLTRLADJF0D6 | Bilateral Fee Adj(Visa Chgbk) |
| FEE | FMSTRPREAUTH | Maestro Preauth Fee |
| FEE | FNYCEPREAUTH | Nyce Preauth Fee |
| FEE | FPULSEPREAUTHF0GG | Pulse Preauth Fee |
| FEE | FSTRPREAUTHAPPRVD | Star Preauth Approved |
| FEE | FSTRPREAUTHDECL | Star Preauth Declines |
| FEE | FMAGICLINEPREAUTH | Magicline Preauth Fee |
| FEE | FVI3DAYAUTHCNCL | Vi 3 Day Auth Cancellation Fee |
| FEE | FVI7DAYAUTHCNCL | Vi 7 Day Auth Cancellation Fee |
| FEE | FVIVRUAUTHF0HF | Visa Vru Authorization Fee |
| FEE | FVIVRUDEFAUTH | Visa Vru Def Auth Fee |
| FEE | FJCB3DAYAUTHCNCL | Jcb 3Day Auth Cancellation Fee |
| FEE | FJCB7DAYAUTHCNCL | Jcb 7Day Auth Cancellation Fee |
| FEE | FJCBVRUAUTHF0IF | Jcb Vru Authorization Fee |
| FEE | FJCBVRUDEFAUTH | Jcb Vru Def Authorization Fee |
| FEE | FMC7DAYAUTHCNCL | Mc 7 Day Auth Cancellation Fee |
| FEE | FMCVRUAUTHF0JF | Mastercard Vru Auth Fee |
| FEE | FMCVRUDEFAUTH | Mastercard Vru Def Auth Fee |
| FEE | FMSTRVRUAUTH | Maestro Vru Authorization Fee |
| FEE | FMSTRVRUDEFAUTH | Maestro Vru Def Auth Fee |
| FEE | FMSTRSOLOVRUAUTH | Maestro Solo Vru Auth Fee |
| FEE | FMSTRSOLOVRUDEFAUTH | Maestro Solo Vru Def Auth Fee |
| FEE | FSOLOVRUAUTH | Solo Vru Authorization Fee |
| FEE | FSOLODEFAUTH | Solo Vru Def Auth Fee |
| FEE | FSOLOCHIPVRUAUTH | Solo Chip Vru Auth Fee |
| FEE | FSOLOCHIPVRUDEFAUTHF0NG | Solo Chip Vru Def Auth Fee |
| FEE | FVIELECVRUAUTH | Visa Electron Vru Auth Fee |
| FEE | FVIELECVRUDEFAUTH | Visa Electron Vru Def Auth Fee |
| FEE | FVIDBVRUAUTH | Visa Debit Vru Auth Fee |
| FEE | FVIDBVRUDEFAUTH | Visa Debit Vru Def Auth Fee |
| FEE | FVIPURCHCARDVRUAUTH | Visa Purch Card Vru Auth Fee |
| FEE | FVIPURCHCARDVRUDEFAUTH | Visa Purch Card Vru Def Auth |
| FEE | FVIDBCHIPVRUAUTH | Visa Debit Chip Vru Auth Fee |
| FEE | FVIDBCHIPVRUDEFAUTH | Visa Debit Chip Vru Def Auth |
| FEE | FVICHIPVRUAUTH | Visa Chip Vru Auth Fee |
| FEE | FVICHIPVRUDEFAUTH | Visa Chip Vru Def Auth Fee |
| FEE | FMCCHIPVRUAUTH | Mastercard Chip Vru Auth Fee |
| FEE | FMCCHIPVRUDEFAUTH | Mastercard Chip Vru Def Auth |
| FEE | FMCPRUCHCDVRUAUTHF0UF | Mc Purchase Cd Vru Auth Fee |
| FEE | FMCPURCHCDVRUDEFAUTH | Mc Purchase Cd Vru Def Auth |
| FEE | FDSCVRUAUTH | Discover Vru Auth Fee |
| FEE | FDSCVRUDEFAUTH | Discover Vru Def Auth Fee |
| FEE | FDNRVRUAUTHF0WF | Diners Vru Authorization Fee |
| FEE | FDNRVRUDEFAUTH | Diners Vru Def Auth Fee |
| FEE | FVICASHSLSTXN | Visacash Sales Transaction Fee |
| FEE | FMNDEXSLSTXN | Mondex Sales Transaction Fee |
| FEE | FRBRTMRSSLSTXN | Robert Morris Sales Trans Fee |
| FEE | FVALLNKSLSTXN | Value Link Sales Trans Fee |
| FEE | FSMRTWRLDTXN | Smart World Transaction Fee |
| FEE | FBLCKACTVTNTXN | Block Activation Trans Fee |
| FEE | FVALLNKTXN | Valuelink Transaction Fee |
| FEE | FAMXVRUAUTHF0YF | Amex Vru Authorization Fee |
| FEE | FAMXVRUDEFAUTH | Amex Vru Def Authorization Fee |
| FEE | FARTDBTXN | Alert Debit Tran Fee |
| FEE | FMSTDBTXN | Most Debit Tran Fee |
| FEE | FMNYSTNDBTXN | Money Station Debit Tran Fee |
| FEE | FITSDBTXN | Its Debit Tran Fee |
| FEE | FACCELSPNSR | Accel Sponsor Fee |
| FEE | FSTRSPNSR | Star Sponsor Fee |
| FEE | FPNSRHNR | Honor Sponsor Fee |
| FEE | FMAGICLINESPNSR | Magicline Sponsor Fee |
| FEE | FPNSRNYCE | Nyce Sponsor Fee |
| FEE | FPULSESPNSR | Pulse Sponsor Fee |
| FEE | FPNSRTXF01R | Tx Sponsor Fee |
| FEE | FPNSRCU24 | Cu 24 Sponsor Fee |
| FEE | FPNSRMPACTF01T | Mpact Sponsor Fee |
| FEE | FAFFNSPNSR | Affn Sponsor Fee |
| FEE | FPNSRALSK | Alaska Option Sponsor Fee |
| FEE | FPNSRINSTTLLR | Instant Teller Sponsor Fee |
| FEE | FVIVOLTIERTXN | Visa Volume Tier Trans Fee |
| FEE | FPNSRATH | Ath Sponsor Fee |
| FEE | FPNSRCRTL | Cartel Sponsor Fee |
| FEE | FDNRINTRNTDIALAUTH | Diners Internet Dial Auth Fee |
| FEE | FAMXINTRNTAUTHF06J | Amex Internet Ll Auth Fee |
| FEE | FAMXCPTR | Amex Capture Fee |
| FEE | FDSCVOID | Discover Voids |
| FEE | FDSCINTAUTH | Discover Internet Ll Auth Fee |
| FEE | FDSCCRRET | Discover Credits/Returns |
| FEE | FDSCFDCINTGWAUTH | Discover Fdc Int Gw Auth Fee |
| FEE | FJCBONLNCPTRTXN | Jcb Online Capture Trans |
| FEE | FGENPLCITIAUTH | Gen Pl Citibnk Financ Auth Fee |
| FEE | FGENPLINTLAUTOAUTH | Gen Pl Intl Auto Auth Fee |
| FEE | FGENPLPHHAUTH | Gen Pl Ph&H Authorization Fee |
| FEE | FGENPLSITEOILAUTH | Gen Pl Site Oil Auth Fee |
| FEE | FGENPLSIMAUTH | Gen Pl Simonson Auth Fee |
| FEE | FMBNAAUTH | Mbna Auth Fee |
| FEE | FPVTLBLVOICEAUTHF095 | Private Label Voice Auth Fee |
| FEE | FCRANTHONYLCLAUTH | C.R. Anthony Local Auth Fee |
| FEE | FCRANTHONYDRCTSOL | C.R.Anthony Direct Solutions |
| FEE | FCRANTHONYARUAUTH | C.R.Anthony Vru Auth Fee |
| FEE | FENRTECRADDRVRFY | Enroute Ecr Address Verify |
| FEE | FENRTECRLCLWATSAUTH | Enroute Local/Wats Auth Fee |
| FEE | FENRTECRAUTH | Enroute Ecr Auth Fee |
| FEE | FENRTECRDRCTSOLN | Enroute Direct Solutions |
| FEE | FENRTVRUAUTH | Enroute Vru Auth Fee |
| FEE | FENRTVRUVOICEAUTH | Enroute Vru/Voice Auth Fee |
| FEE | FENRTVOICEADDRVRFY | Enroute Voice Addr Verify |
| FEE | FENCOREAUTOADDRVER | Encore Auto Addr Verification |
| FEE | FENCOREECRADDRVER | Encore Ecr Addr Verification |
| FEE | FENCOREEDCCPTR | Encore Edc Capture Fee |
| FEE | FTRMLINQDB | Terminal Inquiries Debit |
| FEE | FSTRDBDNL | Star Debit Denial |
| FEE | FSTRDBDNLSTGFWD | Star Dbt Denial,Store & Fwd |
| FEE | FSTRDBDNLDBDRFT | Star Dbt Denial,Debit Draft |
| FEE | FSTRDBDNLRESUB | Star Dbt Denial,Resubmit |
| FEE | FINTRLNKDBDEN | Interlink Debit Denial |
| FEE | FINTRLNKDBDENSTRFWD | Interlink Dbt Denial,Store/Fwd |
| FEE | FINTRLNKDBDENDBDRFT | Interlink Dbt Denial,Dbt Draft |
| FEE | FINTRLNKDBDENRESUB | Interlink Dbt Denial,Resubmit |
| FEE | FINTRLNKDECLTXN | Interlink Decline Trans Fee |
| FEE | FINTRLNKAPPRTXN | Interlink Approved Trans Fee |
| FEE | FINTRLNKVOIDTXNF15G | Interlink Void Trans Fee |
| FEE | FINTRLNKBALINQ | Interlink Balance Inquiry Fee |
| FEE | FINTRLNKERRTXNF15J | Interlink Error Trans Fee |
| FEE | FONUSDBBALINQ | Onus Debit Balance Inquiry |
| FEE | FONUSDBBALDNL | Onus Debit Denial |
| FEE | FONUSDBBALDNLSTRFWD | Onus Debit Denial,Store & Fwd |
| FEE | FONUSDBBALDNLDBDRFT | Onus Debit Denial,Debit Draft |
| FEE | FONUSDBBALDNLRESUB | Onus Debit Denial,Resubmission |
| FEE | FACCELDBBALINQ | Accel Debit Balance Inquiry |
| FEE | FACCELDBDNL | Accel Debit Denial |
| FEE | FACCELDBDNLSTRFWD | Accel Debit Denial,Store & Fwd |
| FEE | FACCELDBDNLDBTDRFT | Accel Debit Denial,Debit Draft |
| FEE | FACCELDBDNLRESUB | Accel Dbt Denial,Resubmission |
| FEE | FNDCPASSTHRUAUTH | Ndc Pass Thru Auth |
| FEE | FMAPPPASSTHRUAUTH | Mapp Pass Thru Auth |
| FEE | FAUTHDCLN | Auth Decline Fee |
| FEE | FVOICEAUTHMERCHLOOKUP | Voice Auth Merch Lookup |
| FEE | FAUTHDCLNF19Y | Auth Decline Fee |
| FEE | FCRTLDCLN | Cartel Decline Fee |
| FEE | FFDMSDBCPTR | Fdms Debit Capture Fee |
| FEE | FCMCAMERMCROLN | American Micro Loan Fee Mc |
| FEE | FVIAMERMICROLOAN | American Micro Loan Fee Visa |
| FEE | FWEBPG | Web Page Fee |
| FEE | FRECONTPE | Reconciliation Tape |
| FEE | FDISCSMMRYRPT | Discount Summary Report |
| FEE | FWSCD028DLYACTVTYREP | Ws Cd 028 Daily Activity Rpt |
| FEE | FWARNBLTNMNTH | Warning Bulletin Monthly Fee |
| FEE | FENVOYTRMNLMAINT | Envoy Terminal Maint Fee |
| FEE | FICVRFYMAINT | Ic Verify Maintenance Fee |
| FEE | FTRNSMSSNCHRG | Transmission Charges |
| FEE | FMSTRDBBALINQ | Maestro Debit Balance Inquiry |
| FEE | FMSTRDBDNL | Maestro Debit Denial |
| FEE | FMSTRDBDNLSTRFWD | Maestro Dbt Denial,Store/Fwd |
| FEE | FMSTRDBDNLDBDRFT | Maestro Dbt Denial, Dbt Draft |
| FEE | FMSTRDBTDNLRESUB | Maestro Dbt Denial, Resubmit |
| FEE | FEVSISTR | Evsi Store |
| FEE | FONLDBBALINQ | Online Debit Balance Inquiry |
| FEE | FCASHSTNWATSAUTH | Cash Station Wats Auth Fee |
| FEE | FAMXINTRNTDIALAUTH | Amex Internet Dial Auth Fee |
| FEE | FDISCINTRNTDIALAUTH | Disc Internet Dial Auth Fee |
| FEE | FICEPACSETUP | Icepac Setup Fee |
| FEE | F5000TRMNLBILLING | 5000 Terminal Billing Fee |
| FEE | FVICASHIC | Visacash Interchange Fee |
| FEE | FROBERTMRSIC | Robert Morris Interchange Fee |
| FEE | FDUQUESNEIC | Duquesne Interchange Fee |
| FEE | FAMXDUESASSMT | Amex Dues/Assessment Fee |
| FEE | FJCBDUESASSMT | Jcb Dues/Assessment Fee |
| FEE | FMACDBDUESASSMT | Mac Debit Dues/Assessment Fee |
| FEE | FDNROTHRITMS | Diners Other Items Fee |
| FEE | FEFTIDBOTHRITM | Efti Debit Other Items Fee |
| FEE | FMOSTDBOTHRITM | Most Debit Other Items Fee |
| FEE | FDNROTHRVOL | Diners Other Volume Fee |
| FEE | FBNKMTOTHRVOL | Bankmate Other Volume Fee |
| FEE | FEFTINETDISC | Efti Net Discount Fee |
| FEE | FMOSTNETDISC | Most Net Discount Fee |
| FEE | FAFFNNETDISC | Affn Net Discount Fee |
| FEE | FACCELNETDISC | Accel Net Discount Fee |
| FEE | FSTRNETDISC | Star Net Discount Fee |
| FEE | FMACDBSLS | Mac Debit Sale Fee |
| FEE | FMSTRDBSLS | Maestro Debit Sale Fee |
| FEE | FINTRLNKDBSLS | Interlink Debit Sale Fee |
| FEE | FNYCEDBSLS | Nyce Debit Sale Fee |
| FEE | FXPLORDBSLS | Explore Debit Sale Fee |
| FEE | FEFTIDBSLS | Efti Debit Sale Fee |
| FEE | FMACDBRET | Mac Debit Returns Tran Fee |
| FEE | FMSTRDBRET | Maestro Debit Returns Fee |
| FEE | FNYCEDBRET | Nyce Debit Return Fee |
| FEE | FEFTIDBCARD | Efti Debit Card Fee |
| FEE | FMOSTDBCARD | Most Debit Card Fee |
| FEE | FCASHSTNDBCARD | Cash Station Debit Card Fee |
| FEE | FAFFNSPNSRDBCARD | Affn Sponsor Debit Card Fee |
| FEE | FMAGICLINEDBCARD | Magicline Debit Card Fee |
| FEE | FACCELDBCARD | Accel Debit Card Fee |
| FEE | FBNKMTDBCARD | Bankmate Debit Card Fee |
| FEE | FVICPSKEYENTR | Visa Cps Key Entered Fee |
| FEE | FVISTNDRDBSNSSCARD | Visa Standard Businesscard Fee |
| FEE | FVIELECBSNSSCARD | Visa Elec. Businesscard Fee |
| FEE | FMCSTNDRDIC | Mastercard Standard Intg Fee |
| FEE | FMCMERIT1 | Mastercard Merit1 Fee |
| FEE | FMCMERIT1F712 | Mastercard Merit1 Fee |
| FEE | FMCSTGFRGN | Mastercard Std Foreign Fee |
| FEE | FVIEIRFIC | Visa Eirf Interchange Rate |
| FEE | FVICPSKEYENTRR | Visa Cps Key Entered Rate |
| FEE | FVISTDELECBCARD | Visa Std Elec. Bcard Rate |
| FEE | FMCMERIT1RT | Mastercard Merit1 Rate |
| FEE | FMCMERIT1RT743 | Mastercard Merit1 Rate |
| FEE | FEBTSLSDISC | Ebt Sales Discount Fee |
| FEE | FEBTRETDISC | Ebt Returns Discount Fee |
| FEE | FCNTRLBNK80601000GRD01 | Central Bank 8060/1000 Grid 01 |
| FEE | FCNTRLBNK80601000GRD02 | Central Bank 8060/1000 Grid 02 |
| FEE | FCNTRLBNK80601000GRD03 | Central Trust 8060/1000 Grid 3 |
| FEE | FCNTRLBNK80601000GRD04 | Central Trust 8060/1000 Grid 4 |
| FEE | FPNCNJ81567000000 | Pnc New Jersey 8156/7000 000 |
| FEE | FPNCNJ81567000111 | Pnc New Jersey 8156/7000 111 |
| FEE | FPNCNJ81567000222 | Pnc New Jersey 8156/7000 222 |
| FEE | FPNCNJ81569000111 | Pnc New Jersey 8156/9000 111 |
| FEE | FPNCNJ81569000201 | Pnc New Jersey 8156/9000 201 |
| FEE | FPNCNJ81569000202 | Pnc New Jersey 8156/9000 202 |
| FEE | FPNCNJ81569000203 | Pnc New Jersey 8156/9000 203 |
| FEE | FPNCNJ81569000222 | Pnc New Jersey 8156/9000 222 |
| FEE | FPNCNJ81569000333 | Pnc New Jersey 8156/9000 333 |
| FEE | FPNCNJ81569000777 | Pnc New Jersey 8156/9000 777 |
| FEE | FPNCNJ81569000888 | Pnc New Jersey 8156/9000 888 |
| FEE | FPNCNJ81567000001 | Pnc New Jersey 8156/7000 001 |
| FEE | FBANKOFBOSTON1074030001 | Bank Of Boston 1074/0300 01 |
| FEE | FBANKOFBOSTON1074030002 | Bank Of Boston 1074/0300 02 |
| FEE | FBANKOFBOSTON1074030003 | Bank Of Boston 1074/0300 03 |
| FEE | FBANKOFBOSTON1074030004 | Bank Of Boston 1074/0300 04 |
| FEE | FBANKOFBOSTON1074030005 | Bank Of Boston 1074/0300 05 |
| FEE | FBANKOFBOSTON1074030006 | Bank Of Boston 1074/0300 06 |
| FEE | FBANKOFBOSTON1074030007 | Bank Of Boston 1074/0300 07 |
| FEE | FBANKOFBOSTON1074030014 | Bank Of Boston 1074/0300 14 |
| FEE | FBANKOFBOSTON1074030015 | Bank Of Boston 1074/0300 15 |
| FEE | FBANKOFBOSTON1074030016 | Bank Of Boston 1074/0300 16 |
| FEE | FBANKOFBOSTON1074050001 | Bank Of Boston 1074/0500 01 |
| FEE | FBANKOFBOSTON1074050002 | Bank Of Boston 1074/0500 02 |
| FEE | FBANKOFBOSTON1074050003 | Bank Of Boston 1074/0500 03 |
| FEE | FBANKOFBOSTON1074050004 | Bank Of Boston 1074/0500 04 |
| FEE | FBANKOFBOSTON1074050005 | Bank Of Boston 1074/0500 05 |
| FEE | FBANKOFBOSTON1074050006 | Bank Of Boston 1074/0500 06 |
| FEE | FBANKOFBOSTON1074050007 | Bank Of Boston 1074/0500 07 |
| FEE | FBANKOFBOSTON1074050014 | Bank Of Boston 1074/0500 14 |
| FEE | FBANKOFBOSTON1074050015 | Bank Of Boston 1074/0500 15 |
| FEE | FBANKOFBOSTON1074050016 | Bank Of Boston 1074/0500 16 |
| FEE | FBANKOFBOSTON1074060001 | Bank Of Boston 1074/0600 01 |
| FEE | FBANKOFBOSTON1074060002 | Bank Of Boston 1074/0600 02 |
| FEE | FBANKOFBOSTON1074060003 | Bank Of Boston 1074/0600 03 |
| FEE | FBANKOFBOSTON1074060004 | Bank Of Boston 1074/0600 04 |
| FEE | FBANKOFBOSTON1074060005 | Bank Of Boston 1074/0600 05 |
| FEE | FBANKOFBOSTON1074060006 | Bank Of Boston 1074/0600 06 |
| FEE | FBANKOFBOSTON1074060007 | Bank Of Boston 1074/0600 07 |
| FEE | FBANKOFBOSTON1074060014 | Bank Of Boston 1074/0600 14 |
| FEE | FBANKOFBOSTON1074060015 | Bank Of Boston 1074/0600 15 |
| FEE | FBANKOFBOSTON1074060016 | Bank Of Boston 1074/0600 16 |
| FEE | FCOMMBNK42500200008 | Commerce Bank 4250/0200 008 |
| FEE | FCOMMBNK42500200009 | Commerce Bank 4250/0200 009 |
| FEE | FCOMMBNK42501400008 | Commerce Bank 4250/1400 008 |
| FEE | FCOMMBNK42501400009 | Commerce Bank 4250/1400 009 |
| FEE | FCOMMBNK42501400012 | Commerce Bank 4250/1400 012 |
| FEE | FCBKCGRID008 | Cbkc Grid 008 |
| FEE | FCBKCGRID012 | Cbkc Grid 012 |
| FEE | FSBEDCLCL0005GRID01 | Fsb Edc Local 0005 Grid01 |
| FEE | FSBEDCLCL0010GRID02 | Fsb Edc Local 0010 Grid02 |
| FEE | FSBEDCLCL0020GRID03 | Fsb Edc Local 0020 Grid03 |
| FEE | FSBEDCLCL0025GRID04 | Fsb Edc Local 0025 Grid04 |
| FEE | FSBEDCLCL0030GRID05 | Fsb Edc Local 0030 Grid05 |
| FEE | FSBEDCLCL0035GRID06 | Fsb Edc Local 0035 Grid06 |
| FEE | FSBEDCLCL0050GRID07 | Fsb Edc Local 0050 Grid07 |
| FEE | FSBEDCLCL0060GRID08 | Fsb Edc Local 0060 Grid08 |
| FEE | FSBEDCWATS0130GRID09 | Fsb Edc Wats 0130 Grid09 |
| FEE | FSBEDC9500225GRID11 | Fsb Edc 950 0225 Grid11 |
| FEE | FSBEDC9500230GRID12 | Fsb Edc 950 0230 Grid12 |
| FEE | FSBEDCPAPR0320GRID14 | Fsb Edc Paper 0320 Grid14 |
| FEE | FSBEDCPAPR0335GRID15 | Fsb Edc Paper 0335 Grid15 |
| FEE | FSBEDCPAPR0345GRID16 | Fsb Edc Paper 0345 Grid16 |
| FEE | FSBEDCPAPR0350GRID17 | Fsb Edc Paper 0350 Grid17 |
| FEE | FSBEDCPAPR0360GRID18 | Fsb Edc Paper 0360 Grid18 |
| FEE | FSBEDCPAPR0370GRID19 | Fsb Edc Paper 0370 Grid19 |
| FEE | FSBEDCPAPR0375GRID20 | Fsb Edc Paper 0375 Grid20 |
| FEE | FSBEDCDIRLCL1030GRID21 | Fsb Edc Dir/Local 1030 Grid21 |
| FEE | FSBEDCDIRLCL1100GRID22 | Fsb Edc Dir/Local 1100 Grid22 |
| FEE | FSBEDCLCL0040GRID23 | Fsb Edc Local 0040 Grid23 |
| FEE | FSBEDCWATS0105GRID24 | Fsb Edc Wats 0105 Grid24 |
| FEE | FSBEDCWATS0110GRID25 | Fsb Edc Wats 0110 Grid25 |
| FEE | FSBEDCWATS0120GRID26 | Fsb Edc Wats 0120 Grid26 |
| FEE | FSBEDCWATS0140GRID27 | Fsb Edc Wats 0140 Grid27 |
| FEE | FSBEDCPAPR0305GRID28 | Fsb Edc Paper 0305 Grid28 |
| FEE | FSBEDCPAPR0310GRID29 | Fsb Edc Paper 0310 Grid29 |
| FEE | FSBEDCPAPR0330GRID30 | Fsb Edc Paper 0330 Grid30 |
| FEE | FSBEDCPAPR0340GRID31 | Fsb Edc Paper 0340 Grid31 |
| FEE | FSBEDCDIRLCL1005GRID32 | Fsb Edc Dir/Local 1005 Grid32 |
| FEE | FSBEDCDIRLCL1010GRID33 | Fsb Edc Dir/Local 1010 Grid33 |
| FEE | FSBEDCDIRLCL1020GRID34 | Fsb Edc Dir/Local 1020 Grid34 |
| FEE | FSBEDCDIRLCL1040GRID35 | Fsb Edc Dir/Local 1040 Grid35 |
| FEE | FSBEDCDIRLCL1050GRID36 | Fsb Edc Dir/Local 1050 Grid36 |
| FEE | FSBEDCDIRWATS1105GRID37 | Fsb Edc Dir/Wats 1105 Grid37 |
| FEE | FSBEDCDIRWATS1110GRID38 | Fsb Edc Dir/Wats 1110 Grid38 |
| FEE | FSBEDCDIRWATS1120GRID39 | Fsb Edc Dir/Wats 1120 Grid39 |
| FEE | FSBEDCDIRWATS1130GRID40 | Fsb Edc Dir/Wats 1130 Grid40 |
| FEE | FSBEDCDIRWATS1140GRID41 | Fsb Edc Dir/Wats 1140 Grid41 |
| FEE | FSBEDCDIRWATS1150GRID42 | Fsb Edc Dir/Wats 1150 Grid42 |
| FEE | FFDRGRDPEILTRV | Fdr Grid Peil Travel |
| FEE | FFDRGRDHUSSCORP | Fdr Grid Hussmann Corp |
| FEE | FFDRGRDKCZOO | Fdr Grid K C Zoo |
| FEE | FFDRGRDNRTHWST | Fdr Grid Northwest |
| FEE | FFDRGRDAMERACDMY | Fdr Grid Amer Academy |
| FEE | FFDRGRDJOHNBULL | Fdr Grid John Bull |
| FEE | FFDRGRDMINSUPP | Fdr Grid Min Supplies |
| FEE | FFDRGRDMEDA | Fdr Grid Meda |
| FEE | FFDRGRDCNTRYCRFT | Fdr Grid Country Craft |
| FEE | FFDRGRDLKFRNT | Fdr Grid Lakefront |
| FEE | FFDRGRDBOEMLRCHV | Fdr Grid Boemler Chev |
| FEE | FFDRGRDTPLNEQUP | Fdr Grid Topline Equip |
| FEE | FFDRGRD80253020TOT | Fdr Grid 8025/3020/Tot |
| FEE | FCOMMBNK | Commerce Bank |
| FEE | FMGNUNPLANTERS01 | Magna/Union Planters 01 |
| FEE | FMGNUNPLANTERS02 | Magna/Union Planters 02 |
| FEE | FMGNUNPLANTERS03 | Magna/Union Planters 03 |
| FEE | FMGNUNPLANTERS04 | Magna/Union Planters 04 |
| FEE | FVICHKCARDREVDISC | Visa Check Card Reversal Disc |
| FEE | FFIB11521000008 | Fib 1152/1000/008 |
| FEE | FFIB11521000012 | Fib 1152/1000/012 |
| FEE | FFIB11521000020 | Fib 1152/1000/020 |
| FEE | FFIB11521000021 | Fib 1152/1000/021 |
| FEE | FFIB11521000023 | Fib 1152/1000/023 |
| FEE | FFIB11521000024 | Fib 1152/1000/024 |
| FEE | FFIB11521000025 | Fib 1152/1000/025 |
| FEE | FFIB11521000028 | Fib 1152/1000/028 |
| FEE | FFIB11521000029 | Fib 1152/1000/029 |
| FEE | FFIB11521000030 | Fib 1152/1000/030 |
| FEE | FFIB47510000060 | Fib 4751/0000/060 |
| FEE | FFIB11521000050 | Fib 1152/1000/050 |
| FEE | FFIB11521000051 | Fib 1152/1000/051 |
| FEE | FFIB11521000052 | Fib 1152/1000/052 |
| FEE | FFIB11521000061 | Fib 1152/1000/061 |
| FEE | FFIB11521000062 | Fib 1152/1000/062 |
| FEE | FFIB11521000063 | Fib 1152/1000/063 |
| FEE | FFIB11521000064 | Fib 1152/1000/064 |
| FEE | FFIB11521000070 | Fib 1152/1000/070 |
| FEE | FFIB11521000071 | Fib 1152/1000/071 |
| FEE | FFIB11521000111 | Fib 1152/1000/111 |
| FEE | FBANCONMTRX626 | Banc One Matrix 626 |
| FEE | FBANCONMTRX710 | Banc One Matrix 710 |
| FEE | FFIB13520000100 | Fib 1352/0000/100 |
| FEE | FFIB14870000001 | Fib 1487/0000/001 |
| FEE | FFIB14870000002 | Fib 1487/0000/002 |
| FEE | FFIB14870000003 | Fib 1487/0000/003 |
| FEE | FFIB14870000004 | Fib 1487/0000/004 |
| FEE | FFIB14870000022 | Fib 1487/0000/022 |
| FEE | FFIB14870000023 | Fib 1487/0000/023 |
| FEE | FFIB14870000024 | Fib 1487/0000/024 |
| FEE | FFIB14870000025 | Fib 1487/0000/025 |
| FEE | FFIB14870000026 | Fib 1487/0000/026 |
| FEE | FFIB14870000027 | Fib 1487/0000/027 |
| FEE | FFIB14870000028 | Fib 1487/0000/028 |
| FEE | FFIB14870000050 | Fib 1487/0000/050 |
| FEE | FFIB14870000052 | Fib 1487/0000/052 |
| FEE | FFIB14870000053 | Fib 1487/0000/053 |
| FEE | FFIB14870000056 | Fib 1487/0000/056 |
| FEE | FFIB14870000111 | Fib 1487/0000/111 |
| FEE | FFIB47640000001 | Fib 4764/0000/001 |
| FEE | FFIB47640000002 | Fib 4764/0000/002 |
| FEE | FFIB47640000004 | Fib 4764/0000/004 |
| FEE | FFIB47640000111 | Fib 4764/0000/111 |
| FEE | FFIB11521000073 | Fib 1152/1000/073 |
| FEE | FFIB11521000074 | Fib 1152/1000/074 |
| FEE | FFIB11521000075 | Fib 1152/1000/075 |
| FEE | FBANCONMTRX729 | Banc One Matrix 729 |
| FEE | FBANCONMTRX738 | Banc One Matrix 738 |
| FEE | FFIB11521000076 | Fib 1152/1000/076 |
| FEE | FFIB11521000202 | Fib 1152/1000/202 |
| FEE | FFIB16203000201 | Fib 1620/3000/201 |
| FEE | FFIB16203000200 | Fib 1620/3000/200 |
| FEE | FFIB11521000005 | Fib 1152/1000/005 |
| FEE | FFIB1487SYSTOT | Fib 1487/Sys/Tot |
| FEE | FFIB11521000003 | Fib 1152/1000/003 |
| FEE | FFIB13520000101 | Fib 1352/0000/101 |
| FEE | FFIB14870000005 | Fib 1487/0000/005 |
| FEE | FFIB14870000007 | Fib 1487/0000/007 |
| FEE | FFIB47510000007 | Fib 4751/0000/007 |
| FEE | FFIB47510000019 | Fib 4751/0000/019 |
| FEE | FFIB47510000029 | Fib 4751/0000/029 |
| FEE | FFIB11521000031 | Fib 1152/1000/031 |
| FEE | FCTDISC2GRID1 | Ct Disc2 Grid #1 |
| FEE | FCTDISC2GRID2 | Ct Disc2 Grid #2 |
| FEE | FCTDISC2GRID3 | Ct Disc2 Grid #3 |
| FEE | FCTDISC2GRID4 | Ct Disc2 Grid #4 |
| FEE | FCTDISC2GRID5 | Ct Disc2 Grid #5 |
| FEE | FCTDISC2GRID6 | Ct Disc2 Grid #6 |
| FEE | FCTDISC2GRID7 | Ct Disc2 Grid #7 |
| FEE | FCTDISC2GRID8 | Ct Disc2 Grid #8 |
| FEE | FCTDISC2GRID9 | Ct Disc2 Grid #9 |
| FEE | FCTDISC2GRID10 | Ct Disc2 Grid #10 |
| FEE | FWACHGRID01 | Wachovia Grid 001 |
| FEE | FWACHGRID02 | Wachovia Grid 002 |
| FEE | FWACHGRID03 | Wachovia Grid 003 |
| FEE | FWACHGRID04 | Wachovia Grid 004 |
| FEE | FWACHGRID05 | Wachovia Grid 005 |
| FEE | FPNCNJ14512000003 | Pnc New Jersey 1451/2000 003 |
| FEE | FPNCNJ14512000013 | Pnc New Jersey 1451/2000 013 |
| FEE | FPNCNJ14512000016 | Pnc New Jersey 1451/2000 016 |
| FEE | FPNCNJ14512000017 | Pnc New Jersey 1451/2000 017 |
| FEE | FPNCNJ14512000020 | Pnc New Jersey 1451/2000 020 |
| FEE | FPNCNJ14512000022 | Pnc New Jersey 1451/2000 022 |
| FEE | FPNCNJ14512000023 | Pnc New Jersey 1451/2000 023 |
| FEE | FPNCNJ14512000025 | Pnc New Jersey 1451/2000 025 |
| FEE | FPNCNJ14512000026 | Pnc New Jersey 1451/2000 026 |
| FEE | FPNCNJ14512000027 | Pnc New Jersey 1451/2000 027 |
| FEE | FPNCNJ14512000028 | Pnc New Jersey 1451/2000 028 |
| FEE | FPNCNJ14512000029 | Pnc New Jersey 1451/2000 029 |
| FEE | FPNCNJ14512000030 | Pnc New Jersey 1451/2000 030 |
| FEE | FPNCNJ14512000031 | Pnc New Jersey 1451/2000 031 |
| FEE | FWACHGRD007 | Wachovia Grid 007 |
| FEE | FWACHGRD008 | Wachovia Grid 008 |
| FEE | FWACHGRD010 | Wachovia Grid 010 |
| FEE | FWACHGRD011 | Wachovia Grid 011 |
| FEE | FWACHGRD012 | Wachovia Grid 012 |
| FEE | FSUNTRUST00420001 | Suntrust 0042/0001 |
| FEE | FSUNTRUST00420002 | Suntrust 0042/0002 |
| FEE | FSUNTRUST00420146 | Suntrust 0042/0146 |
| FEE | FSUNTRUST00420151 | Suntrust 0042/0151 |
| FEE | FSUNTRUST00420152 | Suntrust 0042/0152 |
| FEE | FSUNTRUST00420153 | Suntrust 0042/0153 |
| FEE | FSUNTRUST00420154 | Suntrust 0042/0154 |
| FEE | FSUNTRUST00425555 | Suntrust 0042/5555 |
| FEE | FSUNTRUST00420156 | Suntrust 0042/0156 |
| FEE | FSUNTRUST03950001 | Suntrust 0395/0001 |
| FEE | FSUNTRUST03950005 | Suntrust 0395/0005 |
| FEE | FSUNTRUST03950006 | Suntrust 0395/0006 |
| FEE | FSUNTRUST03950007 | Suntrust 0395/0007 |
| FEE | FSUNTRUST03950025 | Suntrust 0395/0025 |
| FEE | FSUNTRUST03950050 | Suntrust 0395/0050 |
| FEE | FSUNTRUST03950051 | Suntrust 0395/0051 |
| FEE | FSUNTRUST03950075 | Suntrust 0395/0075 |
| FEE | FSUNTRUST03950076 | Suntrust 0395/0076 |
| FEE | FSUNTRUST03957999 | Suntrust 0395/7999 |
| FEE | FSUNTRUST09120005 | Suntrust 0912/0005 |
| FEE | FSUNTRUST09120006 | Suntrust 0912/0006 |
| FEE | FSUNTRUST09120007 | Suntrust 0912/0007 |
| FEE | FSUNTRUST09120008 | Suntrust 0912/0008 |
| FEE | FSUNTRUST09120009 | Suntrust 0912/0009 |
| FEE | FSUNTRUST09120010 | Suntrust 0912/0010 |
| FEE | FSUNTRUST09120011 | Suntrust 0912/0011 |
| FEE | FSUNTRUST09120335 | Suntrust 0912/0335 |
| FEE | FSUNTRUST09128888 | Suntrust 0912/8888 |
| FEE | FSUNTRUST09160005 | Suntrust 0916/0005 |
| FEE | FSUNTRUST09160006 | Suntrust 0916/0006 |
| FEE | FSUNTRUST09160007 | Suntrust 0916/0007 |
| FEE | FSUNTRUST09160008 | Suntrust 0916/0008 |
| FEE | FSUNTRUST09160013 | Suntrust 0916/0013 |
| FEE | FSUNTRUST09160014 | Suntrust 0916/0014 |
| FEE | FSUNTRUST09160015 | Suntrust 0916/0015 |
| FEE | FSUNTRUST09160025 | Suntrust 0916/0025 |
| FEE | FSUNTRUST09160026 | Suntrust 0916/0026 |
| FEE | FSUNTRUST09160069 | Suntrust 0916/0069 |
| FEE | FSUNTRUST09160070 | Suntrust 0916/0070 |
| FEE | FSUNTRUST09160071 | Suntrust 0916/0071 |
| FEE | FSUNTRUST09160072 | Suntrust 0916/0072 |
| FEE | FSUNTRUST09160490 | Suntrust 0916/0490 |
| FEE | FSUNTRUST09160491 | Suntrust 0916/0491 |
| FEE | FSUNTRUST09160590 | Suntrust 0916/0590 |
| FEE | FSUNTRUST09160591 | Suntrust 0916/0591 |
| FEE | FSUNTRUST09160592 | Suntrust 0916/0592 |
| FEE | FSUNTRUST09160593 | Suntrust 0916/0593 |
| FEE | FSUNTRUST09160595 | Suntrust 0916/0595 |
| FEE | FSUNTRUST09167999 | Suntrust 0916/7999 |
| FEE | FSUNTRUST09168888 | Suntrust 0916/8888 |
| FEE | FSUNTRUST09220001 | Suntrust 0922/0001 |
| FEE | FSUNTRUST09220005 | Suntrust 0922/0005 |
| FEE | FSUNTRUST09220006 | Suntrust 0922/0006 |
| FEE | FSUNTRUST09220007 | Suntrust 0922/0007 |
| FEE | FSUNTRUST09220008 | Suntrust 0922/0008 |
| FEE | FSUNTRUST09220009 | Suntrust 0922/0009 |
| FEE | FSUNTRUST09221234 | Suntrust 0922/1234 |
| FEE | FSUNTRUST09226665 | Suntrust 0922/6665 |
| FEE | FSUNTRUST09226666 | Suntrust 0922/6666 |
| FEE | FSUNTRUST09228888 | Suntrust 0922/8888 |
| FEE | FSUNTRUST00420155 | Suntrust 0042/0155 |
| FEE | FSUNTRUST09300001 | Suntrust 0930/0001 |
| FEE | FSUNTRUST09300002 | Suntrust 0930/0002 |
| FEE | FSUNTRUST09300003 | Suntrust 0930/0003 |
| FEE | FSUNTRUST09300004 | Suntrust 0930/0004 |
| FEE | FSUNTRUST09300005 | Suntrust 0930/0005 |
| FEE | FSUNTRUST09300006 | Suntrust 0930/0006 |
| FEE | FSUNTRUST09300007 | Suntrust 0930/0007 |
| FEE | FSUNTRUST09300008 | Suntrust 0930/0008 |
| FEE | FSUNTRUST09300009 | Suntrust 0930/0009 |
| FEE | FSUNTRUST09300010 | Suntrust 0930/0010 |
| FEE | FSUNTRUST09300011 | Suntrust 0930/0011 |
| FEE | FSUNTRUST09300012 | Suntrust 0930/0012 |
| FEE | FSUNTRUST09300013 | Suntrust 0930/0013 |
| FEE | FSUNTRUST09400005 | Suntrust 0940/0005 |
| FEE | FSUNTRUST09400006 | Suntrust 0940/0006 |
| FEE | FSUNTRUST09400007 | Suntrust 0940/0007 |
| FEE | FSUNTRUST09400008 | Suntrust 0940/0008 |
| FEE | FSUNTRUST09400009 | Suntrust 0940/0009 |
| FEE | FSUNTRUST09400010 | Suntrust 0940/0010 |
| FEE | FSUNTRUST09400011 | Suntrust 0940/0011 |
| FEE | FSUNTRUST09460005 | Suntrust 0946/0005 |
| FEE | FSUNTRUST09460006 | Suntrust 0946/0006 |
| FEE | FSUNTRUST09460007 | Suntrust 0946/0007 |
| FEE | FSUNTRUST09460072 | Suntrust 0946/0072 |
| FEE | FSUNTRUST09460493 | Suntrust 0946/0493 |
| FEE | FSUNTRUST09520005 | Suntrust 0952/0005 |
| FEE | FSUNTRUST09520006 | Suntrust 0952/0006 |
| FEE | FSUNTRUST09520007 | Suntrust 0952/0007 |
| FEE | FSUNTRUST09520008 | Suntrust 0952/0008 |
| FEE | FSUNTRUST09520009 | Suntrust 0952/0009 |
| FEE | FSUNTRUST09520010 | Suntrust 0952/0010 |
| FEE | FSUNTRUST09520012 | Suntrust 0952/0012 |
| FEE | FSUNTRUST09520013 | Suntrust 0952/0013 |
| FEE | FSUNTRUST09520014 | Suntrust 0952/0014 |
| FEE | FSUNTRUST09520015 | Suntrust 0952/0015 |
| FEE | FSUNTRUST09520017 | Suntrust 0952/0017 |
| FEE | FSUNTRUST09520069 | Suntrust 0952/0069 |
| FEE | FSUNTRUST09160596 | Suntrust 0916/0596 |
| FEE | FSUNTRUST00420157 | Suntrust 0042/0157 |
| FEE | FSUNTRUST09400012 | Suntrust 0940/0012 |
| FEE | FSUNTRUST00420158 | Suntrust 0042/0158 |
| FEE | FMERCHLVLGRID | Merchant Level Grid |
| FEE | FSUPERMRKTUNDR2MM | Supermarket Under 2Mm |
| FEE | FPETRINIS | Petrinis |
| FEE | FIBSCTELEFLORA | Ibsc/Teleflora |
| FEE | FBK1RESTASSOC | Bk1 Restaurant Assoc |
| FEE | FBARNETTGRID1 | Barnett Grid # 0001 |
| FEE | FBARNETTGRID2 | Barnett Grid # 0002 |
| FEE | FBARNETTGRID4 | Barnett Grid # 0004 |
| FEE | FBARNETTGRID5 | Barnett Grid # 0005 |
| FEE | FBARNETTGRID6 | Barnett Grid # 0006 |
| FEE | FBARNETTGRID8 | Barnett Grid # 0008 |
| FEE | FDELAWAREPAPRMERCHGRID | Delaware Paper Merchants Grid |
| FEE | FNWSTGRID1FDRDMETH | Nwst Grid #1 / Fdr Disc Meth2 |
| FEE | FNWSTGRID2FDRDMETH | Nwst Grid #2 / Fdr Disc Meth2 |
| FEE | FNWSTGRID3FDRDMETH | Nwst Grid #3 / Fdr Disc Meth2 |
| FEE | FNWSTGRID4FDRDMETH | Nwst Grid #4 / Fdr Disc Meth2 |
| FEE | FNWSTGRID5FDRDMETH | Nwst Grid #5 / Fdr Disc Meth2 |
| FEE | FNWSTGRID6FDRDMETH | Nwst Grid #6 / Fdr Disc Meth2 |
| FEE | FNWSTGRID7FDRDMETH | Nwst Grid #7 / Fdr Disc Meth2 |
| FEE | FNWSTGRID8FDRDMETH | Nwst Grid #8 / Fdr Disc Meth2 |
| FEE | FNWSTGRID9FDRDMETH | Nwst Grid #9 / Fdr Disc Meth5 |
| FEE | FNWSTGRID10FDRDMETH | Nwst Grid #10/ Fdr Disc Meth5 |
| FEE | FNWSTGRID1410901200880 | Nwst Grid #14/ 1090 1200 880 |
| FEE | FNWSTGRID1714700600002 | Nwst Grid #17/ 1470 0600 002 |
| FEE | FNWSTGRID1814700600003 | Nwst Grid #18/ 1470 0600 003 |
| FEE | FNWSTGRID1914700600004 | Nwst Grid #19/ 1470 0600 004 |
| FEE | FNWSTGRID23FDRDMETH8001 | Nwst Grid #23/ Fdr Dmeth 8 001 |
| FEE | FNWSTGRID24FDRDMETH8005 | Nwst Grid #24/ Fdr Dmeth 8 005 |
| FEE | FNWSTGRID2514700600005 | Nwst Grid #25/ 1470 0600 005 |
| FEE | FCTDISC2GRD11 | Ct Disc2 Grid #11 |
| FEE | FCTDISC2GRD12 | Ct Disc2 Grid #12 |
| FEE | FCTDISC2GRD13 | Ct Disc2 Grid #13 |
| FEE | FCTDISC2GRD14 | Ct Disc2 Grid #14 |
| FEE | FFUTUREF93V | Future |
| FEE | FBK1DAYTNMATRX002 | Bk1 Dayton Matrix 002 |
| FEE | FFUTUREF93X | Future |
| FEE | FFUTUREF93Y | Future |
| FEE | FFUTUREF93Z | Future |
| FEE | FNANAVLLYLCPAPR | Napa Valley/Lc Paper |
| FEE | FEDCCRDSWIPESGMNT | Edc Card Swipe Segment |
| FEE | FPAPRSEGMNT | Paper Segment |
| FEE | FEDCKEYENTRSGMNT | Edc Key Entered Segment |
| FEE | FNWSTGRID12FDRDMETH8005 | Nwst Grid #12/ Fdr Dmeth 8 005 |
| FEE | FNWSTGRID1310901200002 | Nwst Grid #13/ 1090 1200 002 |
| FEE | FNWSTGRID1514700300002 | Nwst Grid #15/ 1470 0300 002 |
| FEE | FNWSTGRID1614700300003 | Nwst Grid #16/ 1470 0300 003 |
| FEE | FNWSTGRID2014700600005 | Nwst Grid #20/ 1470 0600 005 |
| FEE | FNWSTGRID2130410000002 | Nwst Grid #21/ 3041 0000 002 |
| FEE | FNWSTGRID2230410000003 | Nwst Grid #22/ 3041 0000 003 |
| FEE | FBTMENFDRGRD80253070006 | Boatmen Fdr Grid 8025/3070/006 |
| FEE | FBTMENFDRGRD80254010001 | Boatmen Fdr Grid 8025/4010/001 |
| FEE | FBTMENFDRGRD80254010002 | Boatmen Fdr Grid 8025/4010/002 |
| FEE | FBTMENFDRGRD80254010003 | Boatmen Fdr Grid 8025/4010/003 |
| FEE | FBTMENFDRGRD80256010003 | Boatmen Fdr Grid 8025/6010/003 |
| FEE | FBTMENFDRGRD80256010004 | Boatmen Fdr Grid 8025/6010/004 |
| FEE | FBTMENFDRGRD80256010005 | Boatmen Fdr Grid 8025/6010/005 |
| FEE | FBTMENFDRGRD80256010006 | Boatmen Fdr Grid 8025/6010/006 |
| FEE | FBTMENFDRGRD80256010007 | Boatmen Fdr Grid 8025/6010/007 |
| FEE | FBTMENFDRGRD80256010008 | Boatmen Fdr Grid 8025/6010/008 |
| FEE | FBTMENFDRGRD80256010009 | Boatmen Fdr Grid 8025/6010/009 |
| FEE | FBTMENFDRGRD80256010010 | Boatmen Fdr Grid 8025/6010/010 |
| FEE | FBTMENFDRGRD80256010011 | Boatmen Fdr Grid 8025/6010/011 |
| FEE | FBTMENFDRGRD80256620100 | Boatmen Fdr Grid 8025/6620/100 |
| FEE | FCBKCGRID001 | Cbkc Grid 001 |
| FEE | FBANCONEMATRX720 | Banc One Matrix 720 |
| FEE | FHUNTNGTNGRID1ETC | Huntintton Grid #1 Etc |
| FEE | FHUNTNGTNGRID3MOTO | Huntington Grid #3 Mo/To |
| FEE | FHUNTNGTNGRID4MOTO | Huntington Grid #4 Mo/To |
| FEE | FHUNTNGTNGRID5VOICE | Huntington Grid #5 Voice Etc |
| FEE | FMISC | Misc |
| FEE | FGCUP100TXN | Gc Up 100 Transaction Fee |
| FEE | FGCJMPSTRTMNTH | Gc Jumpstart Monthly Fee |
| FEE | FALLCRCARDAUTH | All Credit Card Authorizations |
| FEE | FFUTUREF5MF | Future |
| FEE | FLACCNCHPFLLBCK | Lac And Cn Chip Fallback Fee |
| FEE | F3PTEGFSINSTLMT12 | 3Rdprty Egftsoc Instlmt Fee12 |
| FEE | F3PTEGFSINSTLMT24 | 3Rdprty Egftsoc Instlmt Fee24 |
| FEE | F3PTEGFSINSTLMT36 | 3Rdprty Egftsoc Instlmt Fee36 |
| FEE | FVIDSTXNNONFUEL | Ds Tran Fee Vi Non Fuel |
| FEE | FMCDSTXNFUEL | Ds Tran Fee Mc Fuel |
| FEE | FMCIDSTXNNONFUEL | Ds Tran Fee Mc Non Fuel |
| FEE | FVIDSTXNFUEL | Ds Tran Fee Vi Fuel |
| FEE | FFSRVFRNTENDAUTH | Fiserv Front End Auth Fees |
| FEE | FCDMNTH | Cd Monthly Fee |
| FEE | FCDIC | Cd Intrchng Fee |
| FEE | FINTRNTNL | International Fee |
| FEE | FCOMDATADISC | Comdata Discount |
| FEE | FCLVRKTCHNDISPL24 | Clover Kitchendisplay 24 |
| FEE | FBUMPBARKB9000USB | Bump Bar Kb9000 Usb |
| FEE | FCLVRKIOSKDISP | Clover Kiosk Display |
| FEE | FCLVRKIOSKMINITRMNL | Clover Kiosk Mini Termnl |
| FEE | FCLVRKIOSKPRNTR | Clover Kiosk Printer |
| FEE | FCLVRKIOSKFRM | Clover Kiosk Frame |
| FEE | FMINECOMTXN | Min Ecom Trn Fee |
| FEE | FBASISECOMTXN | Basis Ecom Trn Fee |
| FEE | FMAXECOMTXN | Max Ecom Trn Fee |
| FEE | FMCAUTHEXCLREV | Mc Auth Exclude Reversal Fee |
| FEE | FVIAUTHEXCLREV | Visa Auth Exclude Reversal Fee |
| FEE | FDISCAUTHEXCLDREV | Disc Auth Exclude Reversal Fee |
| FEE | FAMXAUTHXCLDREV | Amex Auth Exclude Reversal Fee |
| FEE | FNYCENTWRKANN | Nyce Network Annual Fee |
| FEE | FCULIANCENTWRKANN | Culiance Network Annual Fee |
| FEE | FPULSENTWRKANN | Pulse Network Annual Fee |
| FEE | FACCELNTWRKANN | Accel Network Annual Fee |
| FEE | FSTRNTWRKANN | Star Network Annual Fee |
| FEE | FCLVRFLX4 | Clover Flex 4 |
| FEE | FCLVRFLX4STRTRKT | Clover Flex 4 Starterkit |
| FEE | FCLVRFLX4PCKT | Clover Flex 4 Pocket |
| FEE | FCLVRCMPCT | Clover Compact |
| FEE | FCLVRCOMPN | Clover Companion |
| FEE | FSTRTRMLKTPNRT4 | Star Thermal Kit Printr4 |
| FEE | FEFSOTRIC | Efs Otr Interchange Fee |
| FEE | FTCKOTRIC | Tcheck Otr Interchange Fee |
| FEE | FFLTONEOTRIC | Fleetone Otr Interchange Fee |
| FEE | FWEXOTRDISC | Wex Otr Discount |
| FEE | FMCCNP | Mastercard Cnp Fee |
| FEE | FMCCNPPERITM | Mastercard Cnp Per Item Fee |
| FEE | FVICNP | Visa Cnp Fee |
| FEE | FVICNPPERITM | Visa Cnp Per Item Fee |
| FEE | FDNRCNP | Diners Cnp Fee |
| FEE | FDNRCNPPERITEM | Diners Cnp Per Item Fee |
| FEE | GLOBALFEETBL | Global Fee Table |
| FEE | FMCTPEMSGFRMTERR | Mc Tpe Message Format Error |
| FEE | FMCAPAUTHACQPRCLT | Mc Ap Auth Acq Proc Fee Lt |
| FEE | FMCAPAUTHACQPRCXBLT | Mc Ap Auth Acq Proc Fee Xb Lt |
| FEE | FMCAPAUTHACQPRCGT | Mc Ap Auth Acq Proc Fee Gt |
| FEE | FMCAPAUTHACQPRCXBGT | Mc Ap Auth Acq Proc Fee Xb Gt |
| FEE | FVICOMMSOL | Vi Commercial Solutions Fee |
| FEE | FVIHIGHINTGRTYRISK | Vi High Integrity Risk Fee |
| FEE | FVIHIGHINTGRTYRISKVOL | Vi High Integrity Risk Fee Vol |
| FEE | FVIAPPRTLAUTHNPTXN | Vi Ap Partial Auth Np Tran Fee |
| FEE | FMCMOTODOM | Mc Moto Domestic Fee |
| FEE | FMCMOTOXBRDR | Mc Moto Cross Border Fee |
| FEE | FMCNTWKACCSSAUTHNONUS | Mc Ntwk Access Auth Fee Nonus |
| FEE | FMCNTWKACCSSSETTLHNONUS | Mc Ntw Access Settle Fee Nonus |
| FEE | FINTRLNKDBEMVFLBCK | Interlink Dbt Emv Fallback |
| FEE | FINTRLNKDBEXCSSRATTMPT | Interlink Dbt Excess Reattempt |
| FEE | FINTRLNKDBDTLRPT | Intrlnk Dbt Fee Detail Report |
| FEE | FILKMAGSTRPCNTCTLSS | Ilk Mag Stripe Contactless Fee |
| FEE | FMCDIGENBAUTH | Mc Dig Enab Authentication Fee |
| FEE | FMCDIGENBAUTHCAP | Mc Dig Enab Authentication Cap |
| FEE | FMCAPDIGENBAUTH | Mc Ap Dig Enab Authentication |
| FEE | FVIPRASSMT | Pr Vi Assessment Fee |
| FEE | FJCBARULCLAUTHDECL | JCB ARU Decline Per Tran Fee |
| FEE | FMSTRELCTRNAUTH | Maestro Debit Electron Approval Per Tran Fee |
| FEE | FDSCVARULCLAUTHDECL | Discover ARU Decline Per Tran Fee |
| FEE | FDSCVARULCLAUTHREFR | Discover ARU Refrral Per Tran Fee |
| FEE | FDSCVVOICEAUTHDECL | Discover Voice Decline Per Tran Fee |
| FEE | FDSCVVOICEAUTHREFR | Discover Voice Refrral Per Tran Fee |
| FEE | FDSCVELCTRNAUTHDECL | Discover Electron Decline Per Tran Fee |
| FEE | FDSCVELCTRNAUTHREFR | Discover Electron Refrral Per Tran Fee |
| FEE | FDSCVELCTRNAUTH | Discover Electron Approval Per Tran Fee |
| FEE | FMSTRELCTRNAUTHREFR | Maestro Debit Electron Refrral Per Tran Fee |
| FEE | FJCBARULCLAUTHREFR | JCB ARU Refrral Per Tran Fee |
| FEE | FJCBVOICEAUTHDECL | JCB Voice Decline Per Tran Fee |
| FEE | FJCBVOICEAUTHREFR | JCB Voice Refrral Per Tran Fee |
| FEE | FJCBELCTRNAUTHDECL | JCB Electron Decline Per Tran Fee |
| FEE | FJCBELCTRNAUTHREFR | JCB Electron Refrral Per Tran Fee |
| FEE | FJCBELCTRNAUTH | JCB Electron Approval Per Tran Fee |
| FEE | FDNRARULCLAUTHDECL | Diners/Carte Bl ARU Decline Per Tran Fee |
| FEE | FDNRARULCLAUTHREFR | Diners/Carte Bl ARU Refrral Per Tran Fee |
| FEE | FVIDBBASISPNT | Visa Debit Trans/Credit Rate |
| FEE | FAMXOPTBASISPNT | Mastercard Opt Trans/Credit Rate |
| FEE | FAMXOPTSLSTXN | Mastercard Opt Sales Trans Fee |
| FEE | FAMXOPTDSC | Mastercard Opt Sales Discount |
| FEE | FMCDBINTRNTAUTH | Mastercard Debit Internet Auth Fee |
| FEE | FMCDBBASISPNT | Mastercard Debit Trans/Credit Rate |
| FEE | FMCDBSLSTXN | Mastercard Debit Sales Trans Fee |
| FEE | FMCDBSLSDSCNT | Mastercard Debit Sales Discount |
| FEE | FVIDBINTRNTAUTH | Visa Debit Internet Auth Fee |
| FEE | FDNRVOICEAUTHDECL | Diners/Carte Bl Voice Decline Per Tran Fee |
| FEE | FVIDBSLSTXN | Visa Debit Sales Trans Fee |
| FEE | FVIDBSLSDSCNT | Visa Debit Sales Discount |
| FEE | FDSCVBASISPNT | Discover Trans/Credit Rate |
| FEE | FAMBASISPNT | Amex Trans/Credit Rate |
| FEE | FMCBASISPNT | Mastercard Trans/Credit Rate |
| FEE | FVIBASISPNT | Visa Trans/Credit Rate |
| FEE | FMSTRELCTRNAUTHDECL | Maestro Debit Electron Decline Per Tran Fee |
| FEE | FUPINTWRKACCESSSAUTH | UPI Network Access Auth Fee |
| FEE | FMCELCTRNAUTH | Mastercard Electron Approval Per Tran Fee |
| FEE | FVIARULCLAUTHDECL | Visa ARU Decline Per Tran Fee |
| FEE | FVIARULCLAUTHREFR | Visa ARU Refrral Per Tran Fee |
| FEE | FVIVOICEAUTHDECL | Visa Voice Decline Per Tran Fee |
| FEE | FVIVOICEAUTHREFR | Visa Voice Refrral Per Tran Fee |
| FEE | FVIELCTRNAUTHDECL | Visa Electron Decline Per Tran Fee |
| FEE | FVIELCTRNAUTHREFR | Visa Electron Refrral Per Tran Fee |
| FEE | FVIELCTRNAUTH | Visa Electron Approval Per Tran Fee |
| FEE | FMCELCTRNAUTHREFR | Mastercard Electron Refrral Per Tran Fee |
| FEE | FDSCVNTWRKACCESSSAUTH | Discover Network Access Auth Fee |
| FEE | FAMXNTWRKACCESSSAUTH | Amex Network Access Auth Fee |
| FEE | FVINTWRKACCESSSAUTH | Visa Network Access Auth Fee |
| FEE | FMCMINDSCNT | Min Discount Fee for Mastercard |
| FEE | FUPIDBSLSDSCNT | UPI Debit Sales Discount Fee |
| FEE | FUPIBASISPNT | UPI Trans/Credit Rate |
| FEE | FUPIDBBASISPNT | UPI Debit Trans/Credit Rate |
| FEE | FAMXELCTRNAUTHDECL | Amex Electron Decline Per Tran Fee |
| FEE | FDNRVOICEAUTHREFR | Diners/Carte Bl Voice Refrral Per Tran Fee |
| FEE | FDNRELCTRNAUTHDECL | Diners/Carte Bl Electron Decline Per Tran Fee |
| FEE | FDNRELCTRNAUTHREFR | Diners/Carte Bl Electron Refrral Per Tran Fee |
| FEE | FDNRELCTRNAUTH | Diners/Carte Bl Electron Approval Per Tran Fee |
| FEE | FAMXARULCLAUTHDECL | Amex ARU Decline Per Tran Fee |
| FEE | FAMXARULCLAUTHREFR | Amex ARU Refrral Per Tran Fee |
| FEE | FAMXVOICEAUTHDECL | Amex Voice Decline Per Tran Fee |
| FEE | FAMXVOICEAUTHREFR | Amex Voice Refrral Per Tran Fee |
| FEE | FUPIDBSLSTXN | UPI Debit Sales Transaction Fee |
| FEE | FAMXELCTRNAUTHREFR | Amex Electron Refrral Per Tran Fee |
| FEE | FAMXELCTRNAUTH | Amex Electron Approval Per Tran Fee |
| FEE | FMCARULCLAUTHDECL | Mastercard ARU Decline Per Tran Fee |
| FEE | FMCARULCLAUTHREFR | Mastercard ARU Refrral Per Tran Fee |
| FEE | FMCVOICEAUTHDECL | Mastercard Voice Decline Per Tran Fee |
| FEE | FMCVOICEAUTHREFR | Mastercard Voice Refrral Per Tran Fee |
| FEE | FMCELCTRNAUTHDECL | Mastercard Electron Decline Per Tran Fee |
| EQUIPMENT | EQUPLEGO | DELEGO V2.5.3 |
| EQUIPMENT | EQUPLGAY | Govolution Gateway ECOM |
| EQUIPMENT | EQUPLMTX | VisualMatrix V 4.2.0 |
| EQUIPMENT | EQUPLNKG | Merchant Link Gateway |
| EQUIPMENT | EQUPLPOS | SurePay Mobile POS |
| EQUIPMENT | EQUPLSYS | Agilysys LMS v7.3 |
| EQUIPMENT | EQUPLT01 | SELECT TICKETING SYSTEMS |
| EQUIPMENT | EQUPLVEW | Balance View RC |
| EQUIPMENT | EQUPM0V7 | Main St Monetra OMAHAv7 |
| EQUIPMENT | EQUPM428 | Tender Retail MCM 4.2.8 |
| EQUIPMENT | EQUPMALL | iMall Gateway |
| EQUIPMENT | EQUPMAS2 | INTUIT CMAP Swipe Software |
| EQUIPMENT | EQUPMERC | Banc One Mercantec |
| EQUIPMENT | EQUPMETX | IQMetrix PYMTAPI GTWRCDW |
| EQUIPMENT | EQUPMNN9 | Atomic Software - G3 BAM COV/EOL |
| EQUIPMENT | EQUPMO30 | Mainstreetmonetra3.0 |
| EQUIPMENT | EQUPMSP7 | IBM SurePOS v7 |
| EQUIPMENT | EQUPMTX4 | IQMetrix RQ4 GTW RC DW |
| EQUIPMENT | EQUPLOEC | 5TH Dimension GTWEC RCDW |
| EQUIPMENT | EQUPLPGA | PYLPGA PAYLEAP GATEWAY |
| EQUIPMENT | EQUPLYC1 | Daly Commerce |
| EQUIPMENT | EQUPMCCK | PTI-Tellan MAC Auth TDC |
| EQUIPMENT | EQUPMHOS | GHSPA v110020 |
| EQUIPMENT | EQUPMIS1 | Springer-Miller Systems |
| EQUIPMENT | EQUPMK2P | PTI-Tellan MAC HUB 2Pk. HDC |
| EQUIPMENT | EQUPMNNR | HYPERCOM T77F COMBO - G3 BAM COV/EOL |
| EQUIPMENT | EQUPMRUF | Monro Muff Vast by ASN |
| EQUIPMENT | EQUPMV33 | Tdr Ret Mer Con v3.3.12 |
| EQUIPMENT | EQUPNCA1 | Kincaid |
| EQUIPMENT | EQUPNHDC | PTI-Nurit 2060 HDC |
| EQUIPMENT | EQUPNI32 | Omni 3200 Termnl/Printer |
| EQUIPMENT | EQUPNN01 | PINNICLE SOFTWARE |
| EQUIPMENT | EQUPNO01 | INNOVATIVE ELECTRONICS |
| EQUIPMENT | EQUPNT1C | E Proc Net Gateway ECOM |
| EQUIPMENT | EQUPNT3Z | PAYwareTransact3.2.4 |
| EQUIPMENT | EQUPNTBE | Aurus GTW EC |
| EQUIPMENT | EQUPNU70 | PTI-Nurit 2070 |
| EQUIPMENT | EQUPNXPT | Salon Expert |
| EQUIPMENT | EQUPO490 | O490 VER OMNI 490 Controller |
| EQUIPMENT | EQUPPGTY | Imprezzio Gateway |
| EQUIPMENT | EQUPRMV8 | IT Retail MTXEPS v8 |
| EQUIPMENT | EQUPRTRU | TransVirtue (g/w) |
| EQUIPMENT | EQUPMT01 | TEMPUS TECHNOLOGIES |
| EQUIPMENT | EQUPMV60 | Touchnet CMM v6.0 |
| EQUIPMENT | EQUPN070 | PTI-Nurit 2070 HDC |
| EQUIPMENT | EQUPNCAN | Yankee Candle AJB-Epicor |
| EQUIPMENT | EQUPNCMY | Auto Owners Insurance Company |
| EQUIPMENT | EQUPNCR  | NCR Falcon |
| EQUIPMENT | EQUPNDS1 | Jenkon Data Systems |
| EQUIPMENT | EQUPNTRV | Sierra National (REST) v 2011-2 |
| EQUIPMENT | EQUPONT2 | Gateway Connect eCommerce |
| EQUIPMENT | EQUPPCMB | HYPERCOM T7PT COMBO - G3 BAM COV/EOL |
| EQUIPMENT | EQUPPDLB |  DCAP DIALTranBPASS |
| EQUIPMENT | EQUPPS40 | VeroTechPOSServerv4.0 |
| EQUIPMENT | EQUPRPYS | Direct Payment GTWY EC |
| EQUIPMENT | EQUPSFDN | MenuSft 7.4 DD Nash EDC |
| EQUIPMENT | EQUPSUNF | Dennis Uniform |
| EQUIPMENT | EQUPTDC1 | PTI-Nurit 2080 TDC |
| EQUIPMENT | EQUPTEGI | IBM GATEWAY |
| EQUIPMENT | EQUPUARE | Square |
| EQUIPMENT | EQUPPYTS | RedOak VPN v. 1.0 RC |
| EQUIPMENT | EQUPVA33 | Transaction Plus-VDB001 |
| EQUIPMENT | EQUPVE34 | v3.00 ICV WIN NEW M U |
| EQUIPMENT | EQUPM3PR | T8315 CPU/MONITOR BRAIN-Rest |
| EQUIPMENT | EQUPNBNK | Vision Bankard GWY ECOM |
| EQUIPMENT | EQUPO90 | Omron Cat 90 |
| EQUIPMENT | EQUPMA01 | REMANCO DATA CONCEPTS |
| EQUIPMENT | EQUPMCV7 | Main St Monetra CRDNETv7 |
| EQUIPMENT | EQUPMNN4 | Hypercom T7 Plus - G3 BAM COV/EOL |
| EQUIPMENT | EQUPMREC | Cinemark/Penny Ecomm |
| EQUIPMENT | EQUPN910 | Travstar/NEDOSv9.1.0 |
| EQUIPMENT | EQUPMTBX | Children's Place AJB EDC |
| EQUIPMENT | EQUPNERA | Panera 5.00k.3. |
| EQUIPMENT | EQUPNMIS | Brinkman ISO GTWY ECOM |
| EQUIPMENT | EQUPNPFL | Verisign PayFlow VApp |
| EQUIPMENT | EQUPNPRM | Verisign PayFlow Pro Prm |
| EQUIPMENT | EQUPNRSL | Verisign SurePay Reseller |
| EQUIPMENT | EQUPO100 | Omron Cat 100 |
| EQUIPMENT | EQUPOXS7 |  MICROS XSTORE7.0TA DW RC |
| EQUIPMENT | EQUPPE9W | PAYLEAP GATEWAY ECOM |
| EQUIPMENT | EQUPPM01 | LIPMAN USA |
| EQUIPMENT | EQUPRETW | T3 Gateway |
| EQUIPMENT | EQUPSPLR | NAS Polar POS v4.9 |
| EQUIPMENT | EQUPMRGT | Network Merchants Gateway |
| EQUIPMENT | EQUPMTKS | RUUM TEK SERVE SOFTWARE |
| EQUIPMENT | EQUPMWOR | Rest SOL CPU MONTOR WKST |
| EQUIPMENT | EQUPN282 | dinerwarev2.8.2 |
| EQUIPMENT | EQUPNC01 | KINCAID TECHNOLOGIES |
| EQUIPMENT | EQUPNCAE | Ventek Car Gtwy EC RC DW |
| EQUIPMENT | EQUPNE01 | 911 SOFTWARE INC |
| EQUIPMENT | EQUPNEI1 | Venue One, Inc |
| EQUIPMENT | EQUPNO11 | CashierNovaLibraECOM1.1 |
| EQUIPMENT | EQUPNPSE | Synapse RC ECOM GTWY |
| EQUIPMENT | EQUPNSCT | FRNTSTRM FASTTRNSCT GTWY |
| EQUIPMENT | EQUPNSFT | Innsoft NorthEDC V2013  |
| EQUIPMENT | EQUPNTEC | VENTEK GATEWAY EC RC DW |
| EQUIPMENT | EQUPNTRC | VENTEK GATEWAY RC DW |
| EQUIPMENT | EQUPO380 | OMNI 380 Terminal |
| EQUIPMENT | EQUPO396 | VER OMNI 396 TERMINAL |
| EQUIPMENT | EQUPONTO | Pronto Xi v701.x RC |
| EQUIPMENT | EQUPOS01 | ONEPOS.COM |
| EQUIPMENT | EQUPPA01 | ISLAND PACIFIC, ONC |
| EQUIPMENT | EQUPPAC1 | Synaro Payment Processor (Mo/To) |
| EQUIPMENT | EQUPPAPI | GWAY API(RTL/MOTO) |
| EQUIPMENT | EQUPPDP4 | Datapark DP11 PARS v4.01 |
| EQUIPMENT | EQUPPGST | Peregrin Scrip Terminal--EDC |
| EQUIPMENT | EQUPPLEC | Plug&Play E-Commerce |
| EQUIPMENT | EQUPPRES | Express LLC AJB |
| EQUIPMENT | EQUPPS01 | Eclipse Guarantee Capable |
| EQUIPMENT | EQUPPTA2 | SEPTA EC |
| EQUIPMENT | EQUPPV80 | Star-Plusv8.0 |
| EQUIPMENT | EQUPPYGT | BLUEPAY GATEWAY |
| EQUIPMENT | EQUPPZWE | Groupon Zappedy Gwy Ecom |
| EQUIPMENT | EQUPQUIP | Curbstone curbstone card v2.1 |
| EQUIPMENT | EQUPRCE7 | Micros RC e7 |
| EQUIPMENT | EQUPREDC | NCR Aloha  EDC v12.3 |
| EQUIPMENT | EQUPREGT | Sacramento Reg Trans Single Set |
| EQUIPMENT | EQUPRFUR | Verifunds RC |
| EQUIPMENT | EQUPRKEC | Network Mrcht GTW ISO EC  |
| EQUIPMENT | EQUPRLSY | SquirrelProfess v1.7/7.0 |
| EQUIPMENT | EQUPRTNR | Merch Partnrs Gateway |
| EQUIPMENT | EQUPRWGD | Level 10 Waterford  |
| EQUIPMENT | EQUPSACE | Hot Sauce RC |
| EQUIPMENT | EQUPSGLB | Boston Globe |
| EQUIPMENT | EQUPSNET | EFSNET |
| EQUIPMENT | EQUPSP46 | MBSPOS4690vL001.05 |
| EQUIPMENT | EQUPSPLU | DBS TransAction + v7.5.1 |
| EQUIPMENT | EQUPSRLS | Retail Commerce Server (RCS) 5.0. |
| EQUIPMENT | EQUPSSI1 | Credit Line |
| EQUIPMENT | EQUPSTMG | Beanstream DM (G/W) |
| EQUIPMENT | EQUPT001 | RETAIL STORE SYSTEMS |
| EQUIPMENT | EQUPT202 | Tranz 330 202 Terminal |
| EQUIPMENT | EQUPT460 | Tranz 460 Terminal |
| EQUIPMENT | EQUPT77F | Hypercom T77F Friction Fed Printer in 1 |
| EQUIPMENT | EQUPTALE | Thales Talento |
| EQUIPMENT | EQUPTERT | PTI-PC Product-T |
| EQUIPMENT | EQUPTHO | Atamoic Authorizer |
| EQUIPMENT | EQUPTL21 | Telrad Tip 21 |
| EQUIPMENT | EQUPTMST | FlightMasterRC ver12.005 |
| EQUIPMENT | EQUPTNET | Verisign/Signio |
| EQUIPMENT | EQUPTPLS | COST PLUS ACI V4.7 |
| EQUIPMENT | EQUPTRAC | PTI- Fastrac |
| EQUIPMENT | EQUPTRGT | INTRIX TRNSCND GTWY  |
| EQUIPMENT | EQUPTRIX | INTRIX TRNSCND GTWY ECOM |
| EQUIPMENT | EQUPTRK2 | TRANZ 330 Track 2 Terminal |
| EQUIPMENT | EQUPTW01 | PATHWAYS GROUP |
| EQUIPMENT | EQUPTWN3 | DATACAP TWN/IPTrn3.0BUYP |
| EQUIPMENT | EQUPV106 | Vrfne Payware v1.06 |
| EQUIPMENT | EQUPV142 | SICOM SL18 v1.42 |
| EQUIPMENT | EQUPV3US | Ver 3.10 ICVERIFY Windows Single User Up |
| EQUIPMENT | EQUPVA81 | MiniNAC-VHY016 |
| EQUIPMENT | EQUPVB21 | RES v 4.0-VMI003 |
| EQUIPMENT | EQUPVB49 | Positouch-VRS002 |
| EQUIPMENT | EQUPVB89 | Omni 3750 WiFi app UEFN261H -VVF002 |
| EQUIPMENT | EQUPVT62 | Oskar 5.5-VOS001 |
| EQUIPMENT | EQUPWP6M | VX510 Dual Comm 6 Meg |
| EQUIPMENT | EQUPWTCH | ACI SwitchSuitePay v6.5 |
| EQUIPMENT | EQUPYC2R | Gateway Connect Retail MO/TO |
| EQUIPMENT | EQUPPCPR | PTI-PC Product |
| EQUIPMENT | EQUPPCRG | VFI PCCharge 5.8.2 Nash |
| EQUIPMENT | EQUPPSTE | MAAS GLBL PYMNTSITE GTWY  |
| EQUIPMENT | EQUPQZPD | KWI |
| EQUIPMENT | EQUPSLOE | LOEHMANN |
| EQUIPMENT | EQUPTA31 | VeriFone |
| EQUIPMENT | EQUPTDCT | Direct Payment GTWY |
| EQUIPMENT | EQUPTHDC | PTI-Nurit 2090 HDC |
| EQUIPMENT | EQUPTINT | NetVERIFY Internet Dial |
| EQUIPMENT | EQUPTVGE | SOFTVOYAGE GTWY |
| EQUIPMENT | EQUPV451 | Xpient v4.5.1 |
| EQUIPMENT | EQUPV800 | PDQ CMS2 v8.00.02 |
| EQUIPMENT | EQUPVA05 | reseller for SDC-Protobase-VAT001 |
| EQUIPMENT | EQUPVA07 | PAXNSHB v 12B-VAM006 |
| EQUIPMENT | EQUPVA29 | Payment Manager v 6.0.1-VCY001 |
| EQUIPMENT | EQUPVA52 | Ingepay v 3.00 with i7780-VIG003 |
| EQUIPMENT | EQUPVA65 | RES v 4.1 or higher-VMI004 |
| EQUIPMENT | EQUPVA93 | Check-Inn for Windows v 2.0-VIS001 |
| EQUIPMENT | EQUPVA95 | Protobase 6.0x+-VSD002 |
| EQUIPMENT | EQUPVA97 | Synaro Payment Processor v 5.2-VIP001 |
| EQUIPMENT | EQUPVB37 | Order Pro v 3.7-VPI001 |
| EQUIPMENT | EQUPVCM4 | ICV4.4 Change MID |
| EQUIPMENT | EQUPVDTC | VIVOPAY DTC DQ OVERLAY |
| EQUIPMENT | EQUPVRWY | Digital River |
| EQUIPMENT | EQUPVT11 | Reward Fuel Controller-VEU001 |
| EQUIPMENT | EQUPVT42 | Retalix StorePoint v 1.3.1  -VRX002 |
| EQUIPMENT | EQUPVA32 | Block Island Ferry-Reserve-VDC001 |
| EQUIPMENT | EQUPPXS8 | Class B PAX S80  |
| EQUIPMENT | EQUPTLML | TEAM NATIONAL XML COMPASS |
| EQUIPMENT | EQUPNAC1 | NAC - Spare ID |
| EQUIPMENT | EQUPNASC | Goodin Assc Gateway ECOM |
| EQUIPMENT | EQUPNEOM | Ogone Gateway ECOM |
| EQUIPMENT | EQUPNTAG | SecureNet |
| EQUIPMENT | EQUPNTXS | Event Network XSTORE 6.0 |
| EQUIPMENT | EQUPNVNC | HP Pay for Cnvnce GTW EC |
| EQUIPMENT | EQUPOMSS | ICOMS (g/w) |
| EQUIPMENT | EQUPOPAL | TradewindDatavntg v10rtl |
| EQUIPMENT | EQUPPAYY | GWAY VIRTUAL TERM(RTL) |
| EQUIPMENT | EQUPPC | PC Personal Computer |
| EQUIPMENT | EQUPPCO2 | SPOS32_4.1.38 T4230XML |
| EQUIPMENT | EQUPPTNU | PTI-Nurit 2080 |
| EQUIPMENT | EQUPPVST | Vistapaymentserver v4.2 |
| EQUIPMENT | EQUPQT70 | Casio QT-7000 |
| EQUIPMENT | EQUPRBCR | VFI RC Payware PC |
| EQUIPMENT | EQUPRCEC | Tempus Gateway-RC-ecom |
| EQUIPMENT | EQUPRCFP | AJB-RC-FiPay |
| EQUIPMENT | EQUPRCOM | FIS CLEARCOMMERCE GTWY |
| EQUIPMENT | EQUPRGTW | Gateway Tick RC |
| EQUIPMENT | EQUPRNT1 | eProcessing Network (E-comm)  |
| EQUIPMENT | EQUPRNW3 | VFI RC Pay Conn GTW |
| EQUIPMENT | EQUPRWRK | Retail Sol CPU Mntr Wkst |
| EQUIPMENT | EQUPSEAC | BOSE RETAIL |
| EQUIPMENT | EQUPSFWS | EZ Retail v1.51 rev28 RC |
| EQUIPMENT | EQUPSMAP | MAPP PC Software --EDC |
| EQUIPMENT | EQUPSOL1 | Credit Link 4000 |
| EQUIPMENT | EQUPSS10 | CDSmartSolutionsv1.0 |
| EQUIPMENT | EQUPSTIQ | 4Ward Plastiq GTW |
| EQUIPMENT | EQUPSV10 | BPOSv1.0 |
| EQUIPMENT | EQUPSWXB | UNVRSALPMNTS GTWY ECOM |
| EQUIPMENT | EQUPSY01 | AMHERST SYSTEMS |
| EQUIPMENT | EQUPT323 | PayWareTransactv3.2.3 |
| EQUIPMENT | EQUPTAL | Taltek 747 Terminal |
| EQUIPMENT | EQUPTC01 | ENTERPRISE COMPUTER SYS |
| EQUIPMENT | EQUPTCO1 | OpenTeeTime.com |
| EQUIPMENT | EQUPTECM | PAYVISION GATEWAY ECOM |
| EQUIPMENT | EQUPTHTA | Talento Term ETC Type 7 |
| EQUIPMENT | EQUPTICR | COLE HAAN |
| EQUIPMENT | EQUPTMAL | OPTIMALPAYMENTSGTWY |
| EQUIPMENT | EQUPTPIS | Hyp TPI Paymt Server v2.0 |
| EQUIPMENT | EQUPTRIA | QUATERION WINDSS 2003.1 |
| EQUIPMENT | EQUPTTS1 | Gateway Ticketing Systems, Inc |
| EQUIPMENT | EQUPTYLV | ClarityLive Payment v1.0  |
| EQUIPMENT | EQUPUIP1 | Apriva Pay Plus Adrd 4.x |
| EQUIPMENT | EQUPV155 | Squirrel v1.55 |
| EQUIPMENT | EQUPV181 | SICOM SLSeries v1.81 |
| EQUIPMENT | EQUPV212 | Retalix EFTlink v2.1.2 |
| EQUIPMENT | EQUPV3PC | PaywarePCv1.2.2singlepay |
| EQUIPMENT | EQUPV452 | Xpient v4.5.2 |
| EQUIPMENT | EQUPV522 | RORC VIPOS v5.2.2.25 |
| EQUIPMENT | EQUPVA09 | T7Plus, PAXNSHB v 02A-VAM002 |
| EQUIPMENT | EQUPVA53 | POS-IM(interface with MacAuth/PCCharge/ICV)-VES001 |
| EQUIPMENT | EQUPVA78 | T7Plus & SQSR7E v 02Q-VHY013 |
| EQUIPMENT | EQUPVA80 | T7Plus & SPOS7J v. 07A-VHY015 |
| EQUIPMENT | EQUPVB14 | DialCard Modules v 3.0-VMD001 |
| EQUIPMENT | EQUPVB16 | Epsilon v 1126.9-VRA003 |
| EQUIPMENT | EQUPVB80 | Touchnet Payment Interface v 9.0 -VTO001 |
| EQUIPMENT | EQUPVB92 | JavaCard v 7.x--Product Renamed JCharge)-VVF005 |
| EQUIPMENT | EQUPVC04 | Live Processor v. 4.3-VRD001 |
| EQUIPMENT | EQUPVFPP | Verifone Rub Pay-At-The-Pump |
| EQUIPMENT | EQUPVRGV | RETL DEC LIVEPROC GTWY |
| EQUIPMENT | EQUPVSS4 | ICV4.4 Single Upg MS |
| EQUIPMENT | EQUPVT10 | Mate Plus v1.0.2 now called XD2000-VEX001 |
| EQUIPMENT | EQUPVT28 | MICROS RES 3000 v 3.1-VMI002 |
| EQUIPMENT | EQUPWV10 | Vrfne Payware v1.0 |
| EQUIPMENT | EQUPXFNE | Children Place AJB |
| EQUIPMENT | EQUPXPYW | SPOS32_3.3.179 M4230B |
| EQUIPMENT | EQUPYAHO | Yahoo Software |
| EQUIPMENT | EQUPYLIQ | Goody Goody Liquors |
| EQUIPMENT | EQUPN101 | SYNCHRONICS COUNTERPOINT |
| EQUIPMENT | EQUPNCOL | KC Nash ISO HDC |
| EQUIPMENT | EQUPNPSR | Synapse RC GTWY |
| EQUIPMENT | EQUPONCM | PAYON AG GTWY |
| EQUIPMENT | EQUPPCPB | MS POS Chk Prod Bundle |
| EQUIPMENT | EQUPPGSW | Six Pymt GTWY |
| EQUIPMENT | EQUPPKP1 | Asbury Park Press |
| EQUIPMENT | EQUPPNCT | PNC 330 Terminal |
| EQUIPMENT | EQUPR2GW | Merch Prtnrs Gateway ECOM |
| EQUIPMENT | EQUPRCNF | American Furniture |
| EQUIPMENT | EQUPRDR2 | Vx805 |
| EQUIPMENT | EQUPRITT | NURIT 2085 Terminal |
| EQUIPMENT | EQUPRPZA | Peter Pipers Pizza  |
| EQUIPMENT | EQUPRSLT | Member Solutions GTWY |
| EQUIPMENT | EQUPSCP1 | IBS Corp |
| EQUIPMENT | EQUPSCRG | NCR SecurePay GTWY |
| EQUIPMENT | EQUPSI01 | ENSIGN SYSTEMS |
| EQUIPMENT | EQUPSMBS | MBS ECR--Software EDC |
| EQUIPMENT | EQUPSOF2 | GO Software Win Charge/Feature Upgrade |
| EQUIPMENT | EQUPSOF3 | GO Software Win Charge/Compliance Upgrade |
| EQUIPMENT | EQUPSOLE | Aerosoles KWI |
| EQUIPMENT | EQUPSQRD | IGS Citi Money Squared |
| EQUIPMENT | EQUPSS01 | CRS RETAIL SYSTEM |
| EQUIPMENT | EQUPT7E | Hypercom T7E Terminal |
| EQUIPMENT | EQUPTACP | DCAP TWTRAN 3.0 Nash |
| EQUIPMENT | EQUPTARH | Retail Arch Loft v2013.1 |
| EQUIPMENT | EQUPTI01 | SK TECHNOLOGIES, INC |
| EQUIPMENT | EQUPTKLX | SPOS32_4.0 EQUINOXT4230XMLB |
| EQUIPMENT | EQUPTLPM | IntelliPay Payment System |
| EQUIPMENT | EQUPTMLK | Marriott / Merchant Link Gateway |
| EQUIPMENT | EQUPTNOR | FuturePOSNorthEDCv2013-1 |
| EQUIPMENT | EQUPTRNZ | TRANZ 330 Track 1 Terminal |
| EQUIPMENT | EQUPTRVR | Digital River GTWY ECOM |
| EQUIPMENT | EQUPTSGY | IATS Gateway |
| EQUIPMENT | EQUPTSOL | AUTHORIZENET(G/W) |
| EQUIPMENT | EQUPTUI1 | Banc One Intuit |
| EQUIPMENT | EQUPTZ42 | Tranz 420 Terminal |
| EQUIPMENT | EQUPU310 | VFIViper-Buypassv3.10 |
| EQUIPMENT | EQUPUICV | v2.46 ICV D-W S-User Up |
| EQUIPMENT | EQUPUMRJ | Blumer AJB |
| EQUIPMENT | EQUPUPAY | BLUEPAY ISO8583 GTWY |
| EQUIPMENT | EQUPURT2 | NURIT 2090 Wireless Terminal |
| EQUIPMENT | EQUPUSYP | VALUE PMNT SYSTEMS GTWY |
| EQUIPMENT | EQUPV103 | Vrfne Payware v1.0.3 |
| EQUIPMENT | EQUPV200 | PDQ CMS2 v2.00.02 |
| EQUIPMENT | EQUPV825 | MTX WinEPS v825 |
| EQUIPMENT | EQUPVA16 | Assist -VAI001 |
| EQUIPMENT | EQUPVA28 | AFS terminal,AFS/IMS(a.k.a.Enterprise soft)-VCM001 |
| EQUIPMENT | EQUPVA35 | DataTran 162 ND/SL/ML v CIT 6.03 -VDS002 |
| EQUIPMENT | EQUPVA47 | EdgCapture 3.7-VED001 |
| EQUIPMENT | EQUPVA49 | TAP Etran v 5.0-VEL001 |
| EQUIPMENT | EQUPVA50 | Order M8 v 3.0-VEM001 |
| EQUIPMENT | EQUPVA99 | One Pointe v 6.2   -VIP003 |
| EQUIPMENT | EQUPVAS4 | ICV4.4 Add User MS |
| EQUIPMENT | EQUPVAVR | Siverware Avrio Rest RC |
| EQUIPMENT | EQUPVB08 | Logic Solutions-VLO001 |
| EQUIPMENT | EQUPVB10 | Monetra v 5.5-VMS001 |
| EQUIPMENT | EQUPVB11 | Monetra v 5.0-VMS002 |
| EQUIPMENT | EQUPVB13 | Payment Manager version 6.3.1-VCY002 |
| EQUIPMENT | EQUPVB15 | WnetCard Modules v 1.00 -VMD002 |
| EQUIPMENT | EQUPVB17 | Digital Dining v 7.3.4  -VMN001 |
| EQUIPMENT | EQUPVB18 | Merchant Charge Plus v 2002-VMR001 |
| EQUIPMENT | EQUPVB22 | SlipStream v 3.0-VME001 |
| EQUIPMENT | EQUPVB33 | Greencash Register v 2004.03.00-VOT001 |
| EQUIPMENT | EQUPVB51 | Live Processor v. 4.3-VRD001 |
| EQUIPMENT | EQUPVB57 | $$$ on the Net v 4.04.20-VSF001 |
| EQUIPMENT | EQUPVB60 | Slim CD v 2.95-VSM001 |
| EQUIPMENT | EQUPVB62 | ETE Golf Solutions-VSS001 |
| EQUIPMENT | EQUPVB78 | Retail.Net v 4.2-VTM001 |
| EQUIPMENT | EQUPVB84 | TransactionWare GM-VTV001 |
| EQUIPMENT | EQUPVB88 | Omni 3600 application FDMO231i -VVF001 |
| EQUIPMENT | EQUPVCD4 | ICV4.4 Change MID MS |
| EQUIPMENT | EQUPVER2 | IC Verify DOS Multi User |
| EQUIPMENT | EQUPVER8 | v2.46 ICV Win Setup |
| EQUIPMENT | EQUPVER9 | v2.46 ICV Additional User |
| EQUIPMENT | EQUPVT01 | ACR with MTXEPS-VAC001 |
| EQUIPMENT | EQUPVT06 | Datasym POS Symcash 6000 2000-GR v 1.2.3-VDY001 |
| EQUIPMENT | EQUPVT12 | Fiscal FSI-2000 v 6.3P-VFS001 |
| EQUIPMENT | EQUPVT18 | eNConcertStore v 2.1006-VIG001 |
| EQUIPMENT | EQUPVT23 | S4 EZScan v2.02.15 with MTXEPS WinEPS v8.15-VLI001 |
| EQUIPMENT | EQUPVT33 | ACS v 6 with MTXEPS WinEPS v 8.15-VNC002 |
| EQUIPMENT | EQUPVT35 | PV3500 v20.00A-VOW001 |
| EQUIPMENT | EQUPVT36 | Pinnacle Palm v 6.1.19.162-VPA001 |
| EQUIPMENT | EQUPVT39 | Lighthouse  v 3.44-VRA004 |
| EQUIPMENT | EQUPVT52 | Aurora with PaymeNT2000 on Atlanta-VSV002 |
| EQUIPMENT | EQUPVT60 | FUELMASTER? BuyPass v. 1.0-VFU001 |
| EQUIPMENT | EQUPVT63 | Viper 3.08-VVF004 |
| EQUIPMENT | EQUPWN8M | FTNI ETRAN GTWY ECOM |
| EQUIPMENT | EQUPWP3M | VX510, 2MF/3M 14.4K PP standard PCI |
| EQUIPMENT | EQUPWPLE | Vx510LE - FD POS(Dial Only) |
| EQUIPMENT | EQUPWRKM | Networkmerch GTWY |
| EQUIPMENT | EQUPXINE | Xinetix |
| EQUIPMENT | EQUPXMNT | PHOENIXMANET GTWY DW |
| EQUIPMENT | EQUPXRBD | SPOS32_4.0 EQUINOXM4240XMLB |
| EQUIPMENT | EQUPYMST | WAY SYSTEMS GATEWAY |
| EQUIPMENT | EQUPYNTG | Interpoynt GTWY ECOM |
| EQUIPMENT | EQUPRDNC | AM PM Store Dynamics v1 |
| EQUIPMENT | EQUPRE01 | AMERICAN EXPRESS RETAIL |
| EQUIPMENT | EQUPSPOS | SMART SOLUTIONS POS V1 |
| EQUIPMENT | EQUPT4NT | MidExpSlipStream4.0North |
| EQUIPMENT | EQUPTEV8 | Food Tec Ver. 8 |
| EQUIPMENT | EQUPTKWY | Softek GTWY |
| EQUIPMENT | EQUPTRI2 | PrimeTrex |
| EQUIPMENT | EQUPUFIN | BluefinGatewayversion4 |
| EQUIPMENT | EQUPUGPY | PlugNPay v4.2RR RC |
| EQUIPMENT | EQUPUNLM | ServUnlimitedUserLicense |
| EQUIPMENT | EQUPVA60 | Ingepay v 3.00 with Aqua-VIG005 |
| EQUIPMENT | EQUPVB29 | Sable 90, 100 NT-VNU001 |
| EQUIPMENT | EQUPVB55 | Sequoia Credit Partner v 5.0 -VSR001 |
| EQUIPMENT | EQUPVB97 | Payment Manager v 6.0.1-VCY001 |
| EQUIPMENT | EQUPVMD4 | ICV4.4 Add MID MS |
| EQUIPMENT | EQUPVMG4 | ICV4.4 Multi Upg |
| EQUIPMENT | EQUPVO01 | INTERVOICE, INC |
| EQUIPMENT | EQUPYWAY | BUYWAY1 (g/w) |
| EQUIPMENT | EQUPZLTD | Yaz LTD RC |
| EQUIPMENT | EQUPTRFR | NT StoreFront PC |
| EQUIPMENT | EQUPZAGY | Groupon Zappedy Gateway |
| EQUIPMENT | EQUPOUCH | uTouchPOS v4.2 RC |
| EQUIPMENT | EQUPRV45 | MICROS RES v4.5 |
| EQUIPMENT | EQUPSC01 | GATEWAY DATA SCIENCES |
| EQUIPMENT | EQUPSOF1 | GO Software Win Charge Basic Package |
| EQUIPMENT | EQUPSYNC | Terminal |
| EQUIPMENT | EQUPT322 | PayWareTransactv3.2.2 |
| EQUIPMENT | EQUPTR21 | POSLyx220w/transnet2.11 |
| EQUIPMENT | EQUPVB04 | Nurit 8000 Secure and 8320 with FDCS-N Rest-VLM001 |
| EQUIPMENT | EQUPVT38 | Epsilon-VRA001 |
| EQUIPMENT | EQUPPYIT | e4PayIt - EC |
| EQUIPMENT | EQUPSA21 | Casio SA-2100 |
| EQUIPMENT | EQUPSGEC | eProcessing ISO GTW EC |
| EQUIPMENT | EQUPSGTY | CENPOS GTWY |
| EQUIPMENT | EQUPSLN5 | NCR Epsilon105 v2.0.1131 |
| EQUIPMENT | EQUPSV82 | MTXWinEPS v827 |
| EQUIPMENT | EQUPTC55 | TEC 5500 |
| EQUIPMENT | EQUPTHE8 | Hypercom T8 Terminal |
| EQUIPMENT | EQUPTIPY | Intellipay Gateway |
| EQUIPMENT | EQUPTO01 | AUTOMATION SERVICES GRP |
| EQUIPMENT | EQUPTSEL | Nitrosell  FDINTG0.1RCDW |
| EQUIPMENT | EQUPTV31 | Vrfne Paywre Tran v3.1.4 |
| EQUIPMENT | EQUPTWPD | DSTOutput GTW |
| EQUIPMENT | EQUPTZWQ | MOTIONSOFT MOSOPAY GTWY |
| EQUIPMENT | EQUPUPRP | Card Gateway v1.1 EC Rc SRS |
| EQUIPMENT | EQUPURLG | True Religion |
| EQUIPMENT | EQUPUYK5 | VFIBUYPAK5.04.20 |
| EQUIPMENT | EQUPV3NM | Ver 3.10 ICVERIFY Windows New Multi User |
| EQUIPMENT | EQUPV4AM | IC VERIFY |
| EQUIPMENT | EQUPV593 | PCChargev5.9.3 |
| EQUIPMENT | EQUPVA17 | PurchasePlus v 2.10-VBD001 |
| EQUIPMENT | EQUPVA37 | Store21 v 4.67-VDV001 |
| EQUIPMENT | EQUPVA40 | EFS v 3.75-VDS001 |
| EQUIPMENT | EQUPVA48 | ClearCommerce Engine-VEF001 |
| EQUIPMENT | EQUPVA62 | KIS Auto Entry v 8.0-VHC001 |
| EQUIPMENT | EQUPVA66 | WIinEPS v 823.0 SP 2-VMX001 |
| EQUIPMENT | EQUPVB90 | PCCharge v 5.7.1 -VVF003 |
| EQUIPMENT | EQUPVMS4 | ICV4.4 Multi Upg MS |
| EQUIPMENT | EQUPVSGL | Clover Software RC |
| EQUIPMENT | EQUPWWRK | i-Works (g/w) |
| EQUIPMENT | EQUPWXRT | Mobile Comm RC GTW |
| EQUIPMENT | EQUPYM01 | PAYMETRIC INC |
| EQUIPMENT | EQUPZHUT | PIZZA HUT SUS Generic |
| EQUIPMENT | EQUPRMLK | Micros with Merch Link |
| EQUIPMENT | EQUPSDTF | SAP TRIVERSITY FOR DOTS |
| EQUIPMENT | EQUPT1E | Hypercom T7P (T1E) |
| EQUIPMENT | EQUPTTIK | GATEWAY TICKETING  |
| EQUIPMENT | EQUPVB07 | PaymentMate v 2.1-VTE003 |
| EQUIPMENT | EQUPVC01 | Monetra v 5.0-VMS002 |
| EQUIPMENT | EQUPVT07 | DRB Systems SiteWatch AFP v 1.0-VDW001 |
| EQUIPMENT | EQUPVT44 | VIPOS with EFT Manager-VRO002 |
| EQUIPMENT | EQUPVT45 | VIPOS with Payment 2000-VRO003 |
| EQUIPMENT | EQUPVT61 | Gasboy CFN AFP v 35-VGB002 |
| EQUIPMENT | EQUPWICV | v2.46 ICV Win New S-User |
| EQUIPMENT | EQUPVPC9 | PC Charge v5.9.1 |
| EQUIPMENT | EQUPVT13 | Gasboy CFN AFP v 40-VGB001 |
| EQUIPMENT | EQUPUELG | eFueling Pegasus v2.0 |
| EQUIPMENT | EQUPVA54 | Paymetron v 1.2-VEP001 |
| EQUIPMENT | EQUPVER7 | IC Verify Set Up Dos/Version |
| EQUIPMENT | EQUPXGP5 | AspexSuperCharge2011 |
| EQUIPMENT | EQUPXPNT | KCX PaymntPro.Net v1.0.8 |
| EQUIPMENT | EQUPXXXX | Terminal App |
| EQUIPMENT | EQUP12Y7 | 07_19_VAR |
| EQUIPMENT | EQUP12YC | Monetra8.x Native SRS |
| EQUIPMENT | EQUP12Z6 | USAT ePort 1.0 RC |
| EQUIPMENT | EQUP12ZN | QFPay GTW CNP DW ISO HDC |
| EQUIPMENT | EQUP13AR | OLB GTWY EC RC SRS |
| EQUIPMENT | EQUP13AZ | NCR EPS v3.2 ATL105 SRS |
| EQUIPMENT | EQUP13BT | PingPong EC |
| EQUIPMENT | EQUP13BV | FatZebra Jabber 2.4.3 MO |
| EQUIPMENT | EQUP13C2 | DATUM CLUB MED CP |
| EQUIPMENT | EQUP13CY | Headnote Payments |
| EQUIPMENT | EQUP13EF | VF Viper 10.00.00 RC VPN |
| EQUIPMENT | EQUP13FZ | CUBIC ISO Retail |
| EQUIPMENT | EQUP13LD | REV 19 GW RC SRS 2.0 SS |
| EQUIPMENT | EQUP12YZ | ISO 8583 Lease |
| EQUIPMENT | EQUP12Z0 | ISO 8583 Lease Line EC |
| EQUIPMENT | EQUP12ZD | 20/9_VAR4 |
| EQUIPMENT | EQUP12ZK | 1stMile Z3PRDC GTW RC  |
| EQUIPMENT | EQUP12ZQ | 18/10_VAR9 |
| EQUIPMENT | EQUP12ZZ | ACI RCS GTW HDC IP |
| EQUIPMENT | EQUP13A1 | Toshiba ACE V8R2 RC SRS |
| EQUIPMENT | EQUP13A3 | PineappleV.1.2.0 GTW EC |
| EQUIPMENT | EQUP13B4 | TR MCM 5.0.0.242 DW TA |
| EQUIPMENT | EQUP13BS | Yapstone Gtwy RCSRS |
| EQUIPMENT | EQUP13BU | FatZebra Jabber 2.4.3 EC |
| EQUIPMENT | EQUP13BY | ArkosPayatthePumpV2 RC |
| EQUIPMENT | EQUP13C3 | DATUM CLUB MED ECOMM |
| EQUIPMENT | EQUP13CJ | 21/2_VAR34 |
| EQUIPMENT | EQUP13CQ | GTW Authorize.net |
| EQUIPMENT | EQUP13CT | GTW FreedomPay |
| EQUIPMENT | EQUP13CV | PNC Authorize.net ecomm |
| EQUIPMENT | EQUP13CW | PNC Authorize.net Rtl mo |
| EQUIPMENT | EQUP13DA | EIGEN DEV PTS 2 GTWY |
| EQUIPMENT | EQUP13DP | 18/4_VAR82 |
| EQUIPMENT | EQUP13DU | PNC CyberSource Retail |
| EQUIPMENT | EQUP13EK | RC THD GetPAN |
| EQUIPMENT | EQUP13G0 | CUBIC TCU266 ISO EC |
| EQUIPMENT | EQUP13G4 | Vitu GTW RC EC |
| EQUIPMENT | EQUP13GJ | 16/9_VAR24 |
| EQUIPMENT | EQUP13GO | AurusIngenicoTeliumTetra |
| EQUIPMENT | EQUP13GS | Skrill RSK002 |
| EQUIPMENT | EQUP13H7 | Gravity Payment CNP |
| EQUIPMENT | EQUP13H8 | Casino Money RC DW Nexgo |
| EQUIPMENT | EQUP13L6 | NMI OmniGateway ISO |
| EQUIPMENT | EQUP13LA | REV 19 V1 GW SS RC |
| EQUIPMENT | EQUP13M4 | JUSTIFI GTW RC |
| EQUIPMENT | EQUP13M5 | ACI RCS RevChip GTW IP |
| EQUIPMENT | EQUP13MH | Jupiter GTW CNP EC RC |
| EQUIPMENT | EQUP13NK | 05/11_Var_Prod |
| EQUIPMENT | EQUP1V01 | ICVERIFY WEBAUTH |
| EQUIPMENT | EQUP20Q4 | Tender Retail with XPI427d |
| EQUIPMENT | EQUP20QP | First Atlantic Commerce |
| EQUIPMENT | EQUP2463 | 234245 |
| EQUIPMENT | EQUP13AQ | OLB GTWY RC SRS |
| EQUIPMENT | EQUP13AW | PAYTRACE GTW RC |
| EQUIPMENT | EQUP13CG | PhosIntegration V0.3 GTW |
| EQUIPMENT | EQUP13CX | AJB RTS GTW RC EC VPN |
| EQUIPMENT | EQUP13D6 | SOFTWARE EXPRESS GTW MX |
| EQUIPMENT | EQUP13D7 | VF Viper 9.00.00 RC VPN |
| EQUIPMENT | EQUP13DW | Secure Payment 1 RC EC |
| EQUIPMENT | EQUP13DX | USAePay GTW RC EC SS |
| EQUIPMENT | EQUP13ER | 13/6_VAR64 |
| EQUIPMENT | EQUP13FB | CastletechV1.1.3SRSRCOMS |
| EQUIPMENT | EQUP13FC | 20/6_VAR82 |
| EQUIPMENT | EQUP13FE | ABJ RTS V4.1 DWRC |
| EQUIPMENT | EQUP13FP | CRYPTPAYRC DW EC |
| EQUIPMENT | EQUP13G3 |  TSL - UNICOMER - RETAIL |
| EQUIPMENT | EQUP13GC | LANE7000 AZUL |
| EQUIPMENT | EQUP13GF | V200C CAC |
| EQUIPMENT | EQUP13GG | Move2500 3G/Wi-Fi |
| EQUIPMENT | EQUP13GM | 19/9_VAR64 |
| EQUIPMENT | EQUP13GP | AurusIngenicoTetrafamily |
| EQUIPMENT | EQUP13GY | iCheckGtwy Omaha RC |
| EQUIPMENT | EQUP13H0 | ATH-POS ACE V8R2 RC-SRS |
| EQUIPMENT | EQUP13H9 | VESTA RC ECOMMERCE |
| EQUIPMENT | EQUP13HF | TSL RETAIL |
| EQUIPMENT | EQUP13I3 | AJB Fipay 2.3 CXPI DW |
| EQUIPMENT | EQUP13IH | CH Network Connector |
| EQUIPMENT | EQUP13IJ | DandF RCSRS Nash |
| EQUIPMENT | EQUP13JK | RentAccept EC GTW RC SRS |
| EQUIPMENT | EQUP13JL | BILL360 RC GTW EC |
| EQUIPMENT | EQUP13K1 | SIRTE069STORISEC |
| EQUIPMENT | EQUP13K2 | SIRTE069STORIS |
| EQUIPMENT | EQUP13K6 | Ingenico Desk 3500 |
| EQUIPMENT | EQUP13KD | 1stMile GTW RC |
| EQUIPMENT | EQUP13KG | GTW BlueSnap |
| EQUIPMENT | EQUP13KH | DandF RCSRS Nash EC |
| EQUIPMENT | EQUP13KI | Paradigm ISO GTW EC |
| EQUIPMENT | EQUP13KN | Pace GTW RC EC 2.0 |
| EQUIPMENT | EQUP13KP | 1stMILEZ3RPDCGTWRC |
| EQUIPMENT | EQUP13KV | Prisma POS 2.0 |
| EQUIPMENT | EQUP13LG | MadMobileAthena GwSrsDw |
| EQUIPMENT | EQUP13LL | ELOTouch RC |
| EQUIPMENT | EQUP13LM | VF Ecomm Gateway Canada |
| EQUIPMENT | EQUP13LR | BridgePay for PointClick |
| EQUIPMENT | EQUP13LU | PayTheory DWRCEC Lab V1 |
| EQUIPMENT | EQUP13LV | Datacap NETePay5.08SrsSs |
| EQUIPMENT | EQUP13MK | Verifone Global GTW RC  |
| EQUIPMENT | EQUP13MO | Blue Sparq RCV.0.1.0 |
| EQUIPMENT | EQUP13MT | Henry Schein RC EC |
| EQUIPMENT | EQUP13MZ | EasyPayGW RC SRS 3.1 EMV |
| EQUIPMENT | EQUP13N2 | PaymentPro 2.2 RC |
| EQUIPMENT | EQUP13N3 | MarketPayRCECGTWTCKV6 |
| EQUIPMENT | EQUP13NA | GTW BridgePay |
| EQUIPMENT | EQUP13NE | Voyager on Luxe 1.x SS |
| EQUIPMENT | EQUP13O4 | Neon One |
| EQUIPMENT | EQUP13O5 | Integrated POS v7.X  RC |
| EQUIPMENT | EQUP13O7 | Paywire Gateway v3.2 MS |
| EQUIPMENT | EQUP13OC | Felix Cloud RC GTW |
| EQUIPMENT | EQUP13OL | Zebra Pay RC GTW v1.0 |
| EQUIPMENT | EQUP13OM | Patch7-16-23 |
| EQUIPMENT | EQUP13OO | Monetra Compass SS 9.y.z |
| EQUIPMENT | EQUP13OR | Agave Paymentsite v3 RC |
| EQUIPMENT | EQUP13OY | SC - Test |
| EQUIPMENT | EQUP13Q0 | Agave Paymentsite v3RC |
| EQUIPMENT | EQUP13QB | ACI ISO Host RCS 5.x CA |
| EQUIPMENT | EQUP1STG | Bill 1st GTWY |
| EQUIPMENT | EQUP20CR | FD-20 CONTACTLESS READER |
| EQUIPMENT | EQUP20O2 | Anacom Webcharge (g/w) |
| EQUIPMENT | EQUP20O3 | CCPay |
| EQUIPMENT | EQUP20O5 | Digital Dining |
| EQUIPMENT | EQUP20OH | LAC Vx820 - Dual IP/Dial |
| EQUIPMENT | EQUP20OI | Canadian Vx680 WiFi-BT |
| EQUIPMENT | EQUP20ON | Mexico Vx675 Wifi |
| EQUIPMENT | EQUP20OV | Plug N Pay VX820 |
| EQUIPMENT | EQUP20Q2 | Home Depot US Processing |
| EQUIPMENT | EQUP20Q3 | Home Depot Canadian iSC250 |
| EQUIPMENT | EQUP20Q5 | Tender Retail |
| EQUIPMENT | EQUP20QA | Eigen Development VX820 Duet |
| EQUIPMENT | EQUP20QL | LAC OpenSolutions Vx670 Ver.04D |
| EQUIPMENT | EQUP20R0 | Omni 395 256K |
| EQUIPMENT | EQUP20R7 | Verifone PAYware PC E-comm |
| EQUIPMENT | EQUP20R9 | Charge Anywhere - Verifone Omni Series |
| EQUIPMENT | EQUP2C01 | HYPERCOM ICE6500,5500 + |
| EQUIPMENT | EQUP30PI | FD-30 W/PROXIMITY READER |
| EQUIPMENT | EQUP321S | Omni 3210SE |
| EQUIPMENT | EQUP4210 | Equinox T4210 |
| EQUIPMENT | EQUP490I | Verifone Omni 490 IL Lane Terminal |
| EQUIPMENT | EQUP4ADU | Ver 4.00 ICVERIFY Additional User |
| EQUIPMENT | EQUP50DC | VERIF-OMNI 3750 IP CAPABLE TERM |
| EQUIPMENT | EQUP6EOM | PROTOBASE SUITE 6.0 ECOM |
| EQUIPMENT | EQUP8CMW | T8315 CPU/MONITOR WORKSTATION-Rest |
| EQUIPMENT | EQUPABO1 | Payment Gateway |
| EQUIPMENT | EQUPADDL | Server Add User License |
| EQUIPMENT | EQUPANTE | Radiant Epsilon 2.0.1131-2019 |
| EQUIPMENT | EQUPARDS | PNC StoreBuilding Tool |
| EQUIPMENT | EQUPAT01 | USA TECHNOLOGIES |
| EQUIPMENT | EQUPATOM | Atomic |
| EQUIPMENT | EQUPBCFX | Boscov (FD) Retail |
| EQUIPMENT | EQUPBRAG | KUBRA Gateway |
| EQUIPMENT | EQUPBRCS | Cybercash Gateway |
| EQUIPMENT | EQUPBSWD | AJB FIPAY RC V4.1 |
| EQUIPMENT | EQUPBUSY | DBS TransAction+v7.5 RC |
| EQUIPMENT | EQUPC303 | 911Sftware CredtLin 3.03 |
| EQUIPMENT | EQUPCAR1 | PTI-Datacard 640 |
| EQUIPMENT | EQUPCC20 | SDCeNConcertstor2.00.20 |
| EQUIPMENT | EQUPCDEC | WIRECARD GTWY EC DW RC |
| EQUIPMENT | EQUPCI01 | ELECTRUM CORPORATION |
| EQUIPMENT | EQUPCING | Ingram Micro eCommerce |
| EQUIPMENT | EQUPCLCO | Cardio Stress Inc |
| EQUIPMENT | EQUPCSI3 | CSI KWI |
| EQUIPMENT | EQUPDCNU | PTI-Nurit 2070 TDC |
| EQUIPMENT | EQUPDCV6 | ALDELO EDC V6.2 |
| EQUIPMENT | EQUPDEVG | Eigen Dev Gateway Ecom |
| EQUIPMENT | EQUPDGE1 | Budge Text |
| EQUIPMENT | EQUPDV64 | ISD Pay Switch JAVA v6.4 |
| EQUIPMENT | EQUPDV80 | DVM80 Digital Voice Multiplexer |
| EQUIPMENT | EQUPDYX1 | Ordyx 3.1  |
| EQUIPMENT | EQUPENGC | DM Engineering RC |
| EQUIPMENT | EQUPF5BX | ELAVON FUSEBOX GATEWAY (ECOM) |
| EQUIPMENT | EQUPFPOW | InfoSolve mPow3.5 RC |
| EQUIPMENT | EQUPGAEC | FREEDOMPAY GATEWAY ECOM |
| EQUIPMENT | EQUPGE01 | INGENICO |
| EQUIPMENT | EQUPGPAR | LagoonParkCashierv8.5 RC |
| EQUIPMENT | EQUPHOUR | Utouch RC |
| EQUIPMENT | EQUPHSTE | TouchSuite |
| EQUIPMENT | EQUPI542 | RetailDLiveprocessor5.4.2 |
| EQUIPMENT | EQUPIBDS | QUIBIDS - ECOMM |
| EQUIPMENT | EQUPIC06 | v2.60 ICV D-W M-User Up |
| EQUIPMENT | EQUPIC11 | v2.60 ICV Valcode-Add MID |
| EQUIPMENT | EQUPIFIP | BriBor AJB |
| EQUIPMENT | EQUPINSG | VFI PCC5.10.1 NashSngl |
| EQUIPMENT | EQUPIZN4 | Posnet v4.0 RC NashISO |
| EQUIPMENT | EQUPJNCT | PayJunction Gateway |
| EQUIPMENT | EQUP13DE | Commerce Hub GTW |
| EQUIPMENT | EQUP13FM | 18/7_VAR49 |
| EQUIPMENT | EQUP13HI | Gilbarco ATL105 v21.0x |
| EQUIPMENT | EQUP13HX | Verifone SCA Engage RC |
| EQUIPMENT | EQUP13IL | eMerchantPay Gtwy RCMOTO |
| EQUIPMENT | EQUP13KE | Patch7-17-22 |
| EQUIPMENT | EQUP13L5 | GTWY Key CashFlow |
| EQUIPMENT | EQUP13MW | PLUGNPAY V4.2 RC DTW MS |
| EQUIPMENT | EQUP13N7 | ACI ISO RCS 5.x CA |
| EQUIPMENT | EQUP13ON | Magic RC GTW DW SRS SS |
| EQUIPMENT | EQUP13QM | Aurus AurusPay RC DW |
| EQUIPMENT | EQUP1YRS | PCCharge Server |
| EQUIPMENT | EQUP2090 | PTI-Nurit 2090 |
| EQUIPMENT | EQUP20O0 | Aloha-EDC |
| EQUIPMENT | EQUP20O8 | Retail POS |
| EQUIPMENT | EQUP20O9 | FDMS/NASHVILLE FRONT END |
| EQUIPMENT | EQUP20OG | LAC Vx680 3G |
| EQUIPMENT | EQUP20OS | Card Connect EC |
| EQUIPMENT | EQUP20QK | PAYware Connect |
| EQUIPMENT | EQUP20QZ | Canadian IWL2553G IntPinP |
| EQUIPMENT | EQUP20R2 | HYPERCOM T77S COMBO |
| EQUIPMENT | EQUP2FDT | Check21 FD GTWY |
| EQUIPMENT | EQUP32SE | Omni 3200 SE |
| EQUIPMENT | EQUP3312 | TenderMerchConv3.3.12 |
| EQUIPMENT | EQUP3750 | VERIF-OMNI 3750 POS TERM |
| EQUIPMENT | EQUP3C01 | HYPERCOM MININAC |
| EQUIPMENT | EQUP3COM | MAAS GLBL PYMNTSITE ECOM |
| EQUIPMENT | EQUP40PR | VIVOPAY 4000 PROXIMITY READER |
| EQUIPMENT | EQUP5000 | Hypercom ICE T5000 |
| EQUIPMENT | EQUP50AA | FD-50 |
| EQUIPMENT | EQUP5700 | Hypercom ICE 5700 |
| EQUIPMENT | EQUPACHS | Chase-Peachtree |
| EQUIPMENT | EQUPACT1 | MPACT1 Gateway |
| EQUIPMENT | EQUPADGM | CLASS B ExaDigm NX2200 |
| EQUIPMENT | EQUPAM01 | DINE-AMIC SOFTWARE INC |
| EQUIPMENT | EQUPAMIT | amit update |
| EQUIPMENT | EQUPAPPL | XpientCCApplv4.00.43 |
| EQUIPMENT | EQUPARTG | SMartage |
| EQUIPMENT | EQUPATGS | AltametricsBuypassATL105 |
| EQUIPMENT | EQUPAUTH | PTI Authorizer |
| EQUIPMENT | EQUPAVO8 | Dejavoo V-8+ |
| EQUIPMENT | EQUPBIV1 | /nsoftwareIBizIntegratV1 |
| EQUIPMENT | EQUPBLIN | Global Commerce2000 |
| EQUIPMENT | EQUPBRV6 | Cybersource CPM v6.5 |
| EQUIPMENT | EQUPBTOB | SurePay B to B |
| EQUIPMENT | EQUPBX2W | ACCEL PMNTS |
| EQUIPMENT | EQUPCA30 | Casio 3000 |
| EQUIPMENT | EQUPCB12 | MS-POS |
| EQUIPMENT | EQUPCBJR | Global ISO TransArmor |
| EQUIPMENT | EQUPCC01 | GSC COMPUTER SERVICES |
| EQUIPMENT | EQUPCC52 | Princtonpaycardconnct52 |
| EQUIPMENT | EQUPCDV1 | Slim CD v1 |
| EQUIPMENT | EQUPCECA | Hypercom ICE5700 W/ECA |
| EQUIPMENT | EQUPCHGE | Ride Charge |
| EQUIPMENT | EQUPCICV | IC Verify PC Software --EDC |
| EQUIPMENT | EQUPCLBR | LVCC Library District (Innovations) |
| EQUIPMENT | EQUPCMGA | Hypercom ICE5700 W/GUAR |
| EQUIPMENT | EQUPCNTP | DATACAP NETePay4.0 N |
| EQUIPMENT | EQUPCOM1 | Sicom |
| EQUIPMENT | EQUPCOSP | LycoShop (g/w) |
| EQUIPMENT | EQUPCR10 | Paymate 1000 ECR w/Thermal Printer |
| EQUIPMENT | EQUPCSEC | Victoria Secret Direct EC |
| EQUIPMENT | EQUPCSHH | PTI-ECR |
| EQUIPMENT | EQUPCSP6 | CyberSourceCPMv6.4SP6 |
| EQUIPMENT | EQUPCT7 | CT7 Terminal |
| EQUIPMENT | EQUPCU01 | ACCU$ELL |
| EQUIPMENT | EQUPCVDS | DVDS |
| EQUIPMENT | EQUPCYGS | ACCESSO GATEWAY |
| EQUIPMENT | EQUPD680 | Datacard 680ST Terminal |
| EQUIPMENT | EQUPDDDD | 1234 |
| EQUIPMENT | EQUPDECQ | DATACASH GTWY EC RC |
| EQUIPMENT | EQUPDGW1 | Board GTW TA RC DW |
| EQUIPMENT | EQUPDH3K | PassportEDHv8.02.23.03K |
| EQUIPMENT | EQUPDH3L | PassportEDHv8.02.23.03L |
| EQUIPMENT | EQUPDH3M | PassportEDHv8.02.23.03M |
| EQUIPMENT | EQUPDOTE | MA DOT -  RETAIL |
| EQUIPMENT | EQUPDPZQ | DATACASH GTWY RC |
| EQUIPMENT | EQUPDRS1 | eFunds Retail Solutions |
| EQUIPMENT | EQUPDTDR | BPD Tender Retail |
| EQUIPMENT | EQUPDTST | PTI-Datacard 680 ST. |
| EQUIPMENT | EQUPDV53 | ISD Pay Switch UNIX v5.3 |
| EQUIPMENT | EQUPEN01 | OPEN RETAIL SYSTEMS, INC |
| EQUIPMENT | EQUPER01 | THERMEON |
| EQUIPMENT | EQUPESD5 | Dcap NETePay 5.0 Bpass |
| EQUIPMENT | EQUPFINA | NCO - FINANCIAL SYSTEMS INC (G/W) |
| EQUIPMENT | EQUPFIND | Defender Industries Retail Pro SYNARO 11.5 |
| EQUIPMENT | EQUPFINE | NCO - FINANCIAL SYSTEMS INC (G/W) |
| EQUIPMENT | EQUPFTP | Envoy FTP Terminal |
| EQUIPMENT | EQUPFWZG | GoVolution RC GTW EC |
| EQUIPMENT | EQUPGA01 | MEGASYS TECHNICAL SUPP |
| EQUIPMENT | EQUPGECM | EZIC Inc Gateway ECOM |
| EQUIPMENT | EQUPGENL | Ingenico Elite 510 No LAN |
| EQUIPMENT | EQUPGM01 | EXADIGM, INC |
| EQUIPMENT | EQUPGSTG | OLSTS GTWY ECOM SECyber |
| EQUIPMENT | EQUPGTY5 | OLSTS GTWY |
| EQUIPMENT | EQUPGWEC | Paythru Gateway Ecom |
| EQUIPMENT | EQUPGWVG | SOFTVOYAGE GTWY ECOM |
| EQUIPMENT | EQUPHAE3 | NCR Aloha EDC v12.3  |
| EQUIPMENT | EQUPHPN2 | MRCH PRTNR GWY SINGL STL |
| EQUIPMENT | EQUPHYP4 | CT4 Terminal |
| EQUIPMENT | EQUPIC09 | v2.60 ICV Win Setup |
| EQUIPMENT | EQUPIELE | EpicorEaglePOS-RDGv34-RC |
| EQUIPMENT | EQUPIGTW | ACI Postilion GTWY |
| EQUIPMENT | EQUPILML | Agilysys LMS v7.3 multi |
| EQUIPMENT | EQUPIMEA | Prime Access Gateway |
| EQUIPMENT | EQUPINKR | BRINKER AJB DUAL VPNs |
| EQUIPMENT | EQUPINSL | VFI PCC5.10.0 NashSngl |
| EQUIPMENT | EQUPINST | Merchantec Terminal |
| EQUIPMENT | EQUPIPRO | CIT-PRO |
| EQUIPMENT | EQUPIPSB | Tiffany and Company |
| EQUIPMENT | EQUPIPWG | VFI PWT3.2.4NashSingle |
| EQUIPMENT | EQUPIPWS | VFI PWT3.2.4NashSingleEC |
| EQUIPMENT | EQUPIRMS | CIT-RMS |
| EQUIPMENT | EQUPISBA | CIT-SBA |
| EQUIPMENT | EQUPISY2 | AMIGO (E-commerce) |
| EQUIPMENT | EQUPIVEC | EGIVING EC |
| EQUIPMENT | EQUPK2OM | Datapak Gateway ECOM |
| EQUIPMENT | EQUPKCEN | KeyCentrix |
| EQUIPMENT | EQUPKMBL | PARKMOBILE GTWY ECOM |
| EQUIPMENT | EQUPKYRU | Kyrus |
| EQUIPMENT | EQUP13NF | Voyager on Luxe 1.x MS |
| EQUIPMENT | EQUP20OQ | INTRIX Technology Inc. VAR E-comm |
| EQUIPMENT | EQUPAMER | PCAMERICA CUSTOMER OWNED |
| EQUIPMENT | EQUPAPD1 | ScanNet 4.1 |
| EQUIPMENT | EQUPBLST | AJBLSTRAVELPC |
| EQUIPMENT | EQUPBU01 | DATA BUSINESS SYSTEMS |
| EQUIPMENT | EQUPC582 | Vrfne PCChg 5.8.2 |
| EQUIPMENT | EQUPCNL4 | REWARD FUEL CONTROLLER 4 |
| EQUIPMENT | EQUPDIR1 | PAYWAY DIRECT GATEWAY - DIRECT MARKETING |
| EQUIPMENT | EQUPDS6R | DataSym 6000RT |
| EQUIPMENT | EQUPEDLN | SPEEDLINE POS EDC V6.4 |
| EQUIPMENT | EQUPF100 | FD-100 |
| EQUIPMENT | EQUPGV20 | RADIANT CPGATEWAY V2.0 |
| EQUIPMENT | EQUPHOXD | JETRO HOLDINGS |
| EQUIPMENT | EQUPHPUP | COHPU OFFICIAL PAYMENTS |
| EQUIPMENT | EQUPIC02 | v2.60 ICV D-W S-User Up |
| EQUIPMENT | EQUPIC12 | v2.60 ICV Valcode-Chg Pro |
| EQUIPMENT | EQUPIGEC | ACI Postilion ECOM GTWY |
| EQUIPMENT | EQUPINVX | Innovax |
| EQUIPMENT | EQUPISER | Kaiser ACI |
| EQUIPMENT | EQUPIZSW | iBiz Software |
| EQUIPMENT | EQUPLAC1 | LAC Vx510 - Dual IP/Dial |
| EQUIPMENT | EQUPLDGW | CALEDON GATEWAY |
| EQUIPMENT | EQUPLEAS | NetVERIFY Leased Line |
| EQUIPMENT | EQUPHDT1 | Southern DataComm |
| EQUIPMENT | EQUPI302 | VFIRiTAv3.0.2 |
| EQUIPMENT | EQUP13DK | 15/4_VAR85 |
| EQUIPMENT | EQUP20R3 | Key Corp K23 1 |
| EQUIPMENT | EQUP13I2 | TAP ON PHONE SOLUTION |
| EQUIPMENT | EQUP13L4 | GTW TrustCommerce |
| EQUIPMENT | EQUP20O6 | First data Payment Products |
| EQUIPMENT | EQUP3103 | LOC SMS v3.1.0.3 |
| EQUIPMENT | EQUPABUS | DBSTransAction+7.5.1RCDW |
| EQUIPMENT | EQUPAEPA | USAePay Gateway |
| EQUIPMENT | EQUPANST | Beanstream EC (G/W) |
| EQUIPMENT | EQUPBYSS | AUTOGASBUYPASSAT105V6.1 |
| EQUIPMENT | EQUPCGAT | SECURENET GATEWAY |
| EQUIPMENT | EQUPCLBJ | AJBLSPC LS TRAVEL |
| EQUIPMENT | EQUPDIAG | OMNIMEDIA GATEWAY ECOM |
| EQUIPMENT | EQUPIFPY | Verient InfiniPAY RC |
| EQUIPMENT | EQUP13FG | Jersey Mikes DWRC SRS OG |
| EQUIPMENT | EQUP13JY | Sunmi v01 RC |
| EQUIPMENT | EQUP13M3 | UMS UCHARGE GwRcSrsSs |
| EQUIPMENT | EQUP13OT | Move5000 Class B |
| EQUIPMENT | EQUP20Q0 | CONCORD SERVICING (Merchant) |
| EQUIPMENT | EQUP20R6 | VX670 GPRS WIRELESS-CANADA |
| EQUIPMENT | EQUP4GRP | NCO Group CMP GTWY ECOM |
| EQUIPMENT | EQUP4SUU | Ver 4.00 ICVERIFY Windows Single User Up |
| EQUIPMENT | EQUP8RLS | Vx805 |
| EQUIPMENT | EQUPAC01 | ORACLE |
| EQUIPMENT | EQUPAD01 | EPAYMENTS DIRECT INC |
| EQUIPMENT | EQUPALC1 | RETAILDECRED1 GTWY |
| EQUIPMENT | EQUPAYCC | VPAY v5.10.523 |
| EQUIPMENT | EQUPCCAP | Xpient CCAppl v4.00.108 |
| EQUIPMENT | EQUPCHEK | ENCHECK 2500-CHECK READR |
| EQUIPMENT | EQUPCMER | KFCMeritNash EDC |
| EQUIPMENT | EQUPCRNS | Sonte Corp RC pc nails |
| EQUIPMENT | EQUPCRQS | TFPay RC GTW EC |
| EQUIPMENT | EQUPCTEX | PTI-Nurit 3010 Cell Trek Expel |
| EQUIPMENT | EQUPEB01 | SPECIALIZED BUS SOLUTION |
| EQUIPMENT | EQUPECPR | Priority Pymts GTW EC |
| EQUIPMENT | EQUPES01 | FREEDOM SYSTEM |
| EQUIPMENT | EQUPFDMB | FD Mobile Pay 2 App Version |
| EQUIPMENT | EQUPG2AY | Plug n Pay Gateway ECOM |
| EQUIPMENT | EQUPGECS | Skipjack ISO GTW EC |
| EQUIPMENT | EQUPGLCM | Toshiba ACE Buypass V7R4  |
| EQUIPMENT | EQUPGP50 | Nurit 8000 GPRS PCI M50 |
| EQUIPMENT | EQUPGPR6 | VX510 GPRS 6 Meg |
| EQUIPMENT | EQUPHBHM | PTI-Tellan MAC HUB 10 Pk HDC |
| EQUIPMENT | EQUPHDCN | PTI-Nurit 2085 HDC |
| EQUIPMENT | EQUPHLVG | Cashier Live GTWY |
| EQUIPMENT | EQUPHNTL | Merchant Engine Leased Line |
| EQUIPMENT | EQUPHPDC | Fresh Produce (KWI) |
| EQUIPMENT | EQUPHS4M | PAYEEZY GATEWAY HOSTEDPAYMENTECOMM |
| EQUIPMENT | EQUPIC07 | v2.60 ICV S-M-User Up |
| EQUIPMENT | EQUPIC10 | v2.60 ICV Additional User |
| EQUIPMENT | EQUPICOM | ACI Retail Com v5.0 |
| EQUIPMENT | EQUPISGY | TNS NASH ISO GATEWAY |
| EQUIPMENT | EQUPKYWD | Crickory Wood POS 1.1 RC |
| EQUIPMENT | EQUPLE01 | TELEMAC CELLULAR CORP |
| EQUIPMENT | EQUPB419 | NUCLEUS V4.0 BASE 19 |
| EQUIPMENT | EQUPCRPC | HFT Epicor V6.3 |
| EQUIPMENT | EQUPCRTR | CreditCardTracker (Internet) |
| EQUIPMENT | EQUPECR | ECR Cash Register |
| EQUIPMENT | EQUPFBVX | ELAVN FUSEBX GW RESTLODG |
| EQUIPMENT | EQUPFVR2 | n Software v2.0 |
| EQUIPMENT | EQUPI510 | Ingenico i5100 Dial/IP |
| EQUIPMENT | EQUPINSC | VFI PCC5.10.0 NashSnglEC |
| EQUIPMENT | EQUPBSPD | Club speed POS V1.0 |
| EQUIPMENT | EQUPGTWC | Argus Pymt GTW  EC |
| EQUIPMENT | EQUPDYGD | GOODYGOODYLQRS |
| EQUIPMENT | EQUPGSPS | SAGE SPS GATEWAY ECOM |
| EQUIPMENT | EQUPHOOS | Yahoo |
| EQUIPMENT | EQUPESMS | IATS Gateway E-COM SMS |
| EQUIPMENT | EQUPFFUE | EnfaticaFusion RC GTY EC |
| EQUIPMENT | EQUP100 | C/O CSI GT100 TERMINAL |
| EQUIPMENT | EQUP100H | Aero-AJB V1 |
| EQUIPMENT | EQUP100V | Orthobanc |
| EQUIPMENT | EQUP1013 | Louis Vuitton-AJB V1 |
| EQUIPMENT | EQUP101D | Herbalife ISO 8583 HDC |
| EQUIPMENT | EQUP101E | OnlineShoesVS10.3Ecomtry |
| EQUIPMENT | EQUP101I | Sleepys TA RC V1.0 |
| EQUIPMENT | EQUP101M | D2SolutionsGrpv4RCDW |
| EQUIPMENT | EQUP101N | D2SolutionsGrpv4RCDWECOM |
| EQUIPMENT | EQUP101O | Speed Commerce GTWY |
| EQUIPMENT | EQUP101P | EPICOR ESDM2.4.1RC TCPIP |
| EQUIPMENT | EQUP102D | INVAPAY COMPASS |
| EQUIPMENT | EQUP1030 | SUMMITFINANCIAL EC DW RC |
| EQUIPMENT | EQUP1036 | JPMC Virtual EC RC |
| EQUIPMENT | EQUP1063 | Point SCA - Verifone |
| EQUIPMENT | EQUP109U | Nash3Mar13 |
| EQUIPMENT | EQUP100Y | MidEXslipstream4.5DW |
| EQUIPMENT | EQUP101H | YCS PR CORP RC v3.1 |
| EQUIPMENT | EQUP101T | Avangate |
| EQUIPMENT | EQUP102A | CreditCall Ltd RC EC PTS |
| EQUIPMENT | EQUP102H | CANARY ON CHROME RCDW |
| EQUIPMENT | EQUP102X | TenderRetMCon v5.0 EC RC |
| EQUIPMENT | EQUP1032 | FTD CCAS EC RC |
| EQUIPMENT | EQUP1033 | InstaMed Direct RTL |
| EQUIPMENT | EQUP1035 | AJB RST v4 Swi Books Mil |
| EQUIPMENT | EQUP1038 | SICOM SL Series v2.610 |
| EQUIPMENT | EQUP103R | XpientCCA TPENASH 4.6mul |
| EQUIPMENT | EQUP103T | Casual Male AJB RTS |
| EQUIPMENT | EQUP103U | Alacriti v5.0 RC MOTO |
| EQUIPMENT | EQUP103W | Port of Seattle |
| EQUIPMENT | EQUP103Y | Barri Money Transfer |
| EQUIPMENT | EQUP1042 | MRL POSNET GTW DW RC |
| EQUIPMENT | EQUP104B | EPICOR ESDM241SP1RCTCPIP |
| EQUIPMENT | EQUP104E | TempusGTWmulti |
| EQUIPMENT | EQUP104M | SixPmt SixCd GTW ECmulti |
| EQUIPMENT | EQUP1053 | TouchnetUcom6.5 RC DW EC |
| EQUIPMENT | EQUP105A | Point SCA |
| EQUIPMENT | EQUP105F | AJB-Fin Feather Fur |
| EQUIPMENT | EQUP105I | SMITHCO FBPRTRST1 RCPTDW |
| EQUIPMENT | EQUP105Q | ChargeIt Pro RC EC v5.0 |
| EQUIPMENT | EQUP1060 | CYBERSOURCE ICS2 GTWY |
| EQUIPMENT | EQUP106O | Nash5Mar4 |
| EQUIPMENT | EQUP107G | MAGNOLIAVAR RC |
| EQUIPMENT | EQUP1089 | AURUS GTWY DW RC |
| EQUIPMENT | EQUP108C | ANYWCOM GTWY RC DW EC |
| EQUIPMENT | EQUP108X | Vindicia Cashbox GTW |
| EQUIPMENT | EQUP109Z | CompassMar13 |
| EQUIPMENT | EQUP10AG | Deepmala13thmarcompass |
| EQUIPMENT | EQUP10EM | Nash6Mar21 |
| EQUIPMENT | EQUP10EP | BuypassMar21 |
| EQUIPMENT | EQUP10FI | BuypassMar24 |
| EQUIPMENT | EQUP10IL | Nash04Apr21 |
| EQUIPMENT | EQUP10IO | CardnetApr21 |
| EQUIPMENT | EQUP10XX | Voltage_VAR |
| EQUIPMENT | EQUP110D | Shift4$$$OnNet GTW RC |
| EQUIPMENT | EQUP110H | GOOGLE GTW EC DW RC |
| EQUIPMENT | EQUP110I | INDEX SYS GTW DW RC |
| EQUIPMENT | EQUP1113 | FD400GT CDMA DW |
| EQUIPMENT | EQUP111L | LOCOMOBI DW RC |
| EQUIPMENT | EQUP1129 | ACI RCS 5.1 EC |
| EQUIPMENT | EQUP112T | HIGHRADIUS GTWY DW RC |
| EQUIPMENT | EQUP11BC | WORLDNET GTW DW RC |
| EQUIPMENT | EQUP1027 | Drake Software RC DW EC |
| EQUIPMENT | EQUP102F | ACI Retail Com v5.0 EC |
| EQUIPMENT | EQUP103O | TranzGate RC GWY DW |
| EQUIPMENT | EQUP103P | XpientCCA TPE FDMS v4.6 |
| EQUIPMENT | EQUP104L | 3C Pmt GTW ms |
| EQUIPMENT | EQUP104N | SixPmt SixCdGTW ECsingle |
| EQUIPMENT | EQUP104S | NB. South Migration |
| EQUIPMENT | EQUP105R | ChargeIt PRO RCMO Retail |
| EQUIPMENT | EQUP1062 | Penske Rental Net |
| EQUIPMENT | EQUP1064 | AMDOCS EC GTWY |
| EQUIPMENT | EQUP1066 | ComboFeb28 |
| EQUIPMENT | EQUP106D | One, Inc. |
| EQUIPMENT | EQUP106F | TENERUM  GTW RT RC |
| EQUIPMENT | EQUP1074 | OLU Zeamster v2.0 RC EC |
| EQUIPMENT | EQUP108E | BF PayConex GTW RC EC |
| EQUIPMENT | EQUP108I | CardnetMar10 |
| EQUIPMENT | EQUP108Y | CardConnect RC v5.2 EC |
| EQUIPMENT | EQUP109F | Red Lobster GTW |
| EQUIPMENT | EQUP109J | EpicorRSGESDMV2.4.1 |
| EQUIPMENT | EQUP10A0 | BuypassMar13 |
| EQUIPMENT | EQUP10AY | Nash3Mar14 |
| EQUIPMENT | EQUP10B1 | Nash6Mar14 |
| EQUIPMENT | EQUP10B6 | All1Mar14 |
| EQUIPMENT | EQUP10C1 | Nash3Mar17 |
| EQUIPMENT | EQUP10C2 | Nash4Mar17 |
| EQUIPMENT | EQUP10CY | Nash06Mar18 |
| EQUIPMENT | EQUP10DK | AllMar19 |
| EQUIPMENT | EQUP10E1 | Nash1Mar20 |
| EQUIPMENT | EQUP10EA | Nash6Mar20 |
| EQUIPMENT | EQUP10EN | CardnetMar21 |
| EQUIPMENT | EQUP10EQ | AllMar21 |
| EQUIPMENT | EQUP10FB | Nash2Mar24 |
| EQUIPMENT | EQUP10IF | Nash1Apr21 |
| EQUIPMENT | EQUP10IS | Buypass02Apr21 |
| EQUIPMENT | EQUP10O1 | Nash |
| EQUIPMENT | EQUP10O9 | CardMar11 |
| EQUIPMENT | EQUP10YQ | OMNI 3740 |
| EQUIPMENT | EQUP10YR | Vx 510 |
| EQUIPMENT | EQUP10Z6 | Home Depot Canadian Processing |
| EQUIPMENT | EQUP1108 | EMS AJB RTS |
| EQUIPMENT | EQUP1112 | FD410DW |
| EQUIPMENT | EQUP111A | EpicorGTW 3.X RC |
| EQUIPMENT | EQUP111B | Micros x-store VS 7.01 |
| EQUIPMENT | EQUP111C | VERIENT INFINI EC DW RC |
| EQUIPMENT | EQUP111G | DRB DW RC |
| EQUIPMENT | EQUP111N | DTCP NETePAY 5.05 GTW RC |
| EQUIPMENT | EQUP111Z | KIS Microsale 9.0 RC DW |
| EQUIPMENT | EQUP1127 | Monetra 2.1.0 EC |
| EQUIPMENT | EQUP112F | TransResCdDog GtwDwRcEc |
| EQUIPMENT | EQUP112H | PYMNT EX GTWY EC DW RC |
| EQUIPMENT | EQUP112I | NetworkMerchant GTWY |
| EQUIPMENT | EQUP112X | POSBANK USA RC DW |
| EQUIPMENT | EQUP1138 | USTOY DW RC |
| EQUIPMENT | EQUP113A | CSG SYSTEMS DW RC |
| EQUIPMENT | EQUP113Q | AJB FIPAY EPS v2.2 SS RC |
| EQUIPMENT | EQUP113V | TOUCHNET DW EC RC |
| EQUIPMENT | EQUP114F | GreenLight GTW DW RC |
| EQUIPMENT | EQUP114H | CLASS B ExaDigm NX2200E |
| EQUIPMENT | EQUP114W | ACI RCS GTW RC EC SS |
| EQUIPMENT | EQUP115C | VSECURE DW SRS RC |
| EQUIPMENT | EQUP115P | VIVONET 1.15 DW RC |
| EQUIPMENT | EQUP115V | COMPRISE T GTW EC DW RC |
| EQUIPMENT | EQUP115Y | KFC INGENICO RC |
| EQUIPMENT | EQUP1161 | LAC Opensol Vx820 V.01A |
| EQUIPMENT | EQUP1162 | LAC Opensol Vx680 V.01A |
| EQUIPMENT | EQUP1166 | GreenLight GTW RC DW |
| EQUIPMENT | EQUP116E | PAX BPOS VPN RC |
| EQUIPMENT | EQUP116M | TKTTECH ULTRA 2.0 DW RC |
| EQUIPMENT | EQUP116R | Century 21 Xstore |
| EQUIPMENT | EQUP1173 | CSG SYSTEMS GTW RC |
| EQUIPMENT | EQUP117W | VDS EC RC DW SRS |
| EQUIPMENT | EQUP119I | INIT eFare v0.1 DwSrsRc |
| EQUIPMENT | EQUP119P | AJB FIPAYEPSv2.2RCSRS SS |
| EQUIPMENT | EQUP119U | VDS RC DW SRS |
| EQUIPMENT | EQUP11A2 | FEXCO OpenConnect GwDwSs |
| EQUIPMENT | EQUP11AB | BASYS IQ GTW EC RC SRS |
| EQUIPMENT | EQUP11AF | CHING GTW V1 DW EC |
| EQUIPMENT | EQUP11AL | BF PayConexPlus GtwRc |
| EQUIPMENT | EQUP11AN | PaySpan GTW RC SRS |
| EQUIPMENT | EQUP11BA | Comp Soln Order Power |
| EQUIPMENT | EQUP11BJ | Upfront POS RC SRS |
| EQUIPMENT | EQUP11BX | PAX S300 RC SRS EDC |
| EQUIPMENT | EQUP11C7 | Point SCA 3.1.xx DWRCSRS |
| EQUIPMENT | EQUP11CA | Mexico IPG GTW MOTO |
| EQUIPMENT | EQUP11CL | FD CANADA RC SRS |
| EQUIPMENT | EQUP11CM | Epicor CloudGTWYTCPIP RC |
| EQUIPMENT | EQUP11CP | MHC MOTORETAIL V1 RC SRS |
| EQUIPMENT | EQUP11Q1 | Mexico IWL220 Int PinPad |
| EQUIPMENT | EQUP11QA | CAC IPG GTW MOTO |
| EQUIPMENT | EQUP11QP | FD OMAHA RC NO VAR SHEET |
| EQUIPMENT | EQUP11R1 | VX520 64mb terminal |
| EQUIPMENT | EQUP11TH | MidniteExSlipstream5.0DW |
| EQUIPMENT | EQUP11U0 | Mexico PayPoint GT EC |
| EQUIPMENT | EQUP11WS | CR1008751_VAR |
| EQUIPMENT | EQUP11XZ | TMobile RC SRS |
| EQUIPMENT | EQUP11Y8 | CA MPOS Comsgate v2.6 |
| EQUIPMENT | EQUP11YN | Payvision GTW DL Host |
| EQUIPMENT | EQUP11ZB | JACK HENRY GTW RC SS |
| EQUIPMENT | EQUP11ZJ | Amadeus APP GTW RC EC |
| EQUIPMENT | EQUP1223 | GREEN DOT RC |
| EQUIPMENT | EQUP1226 | CR1038731_Var |
| EQUIPMENT | EQUP123U | Element Pmnt Svc GTWY SS |
| EQUIPMENT | EQUP1275 | Mexico Engage V200T DW |
| EQUIPMENT | EQUP127P | WF ISO8583 VPN EC |
| EQUIPMENT | EQUP128K | ILToll ATS RC EC DW |
| EQUIPMENT | EQUP1292 | CR1093731-VAR |
| EQUIPMENT | EQUP129Q | Seamless GTW HdcSrsSsEc |
| EQUIPMENT | EQUP129T | Seamless GTW HdcSrsMs |
| EQUIPMENT | EQUP12AV | Aurus GW RC VPN DS SS |
| EQUIPMENT | EQUP12BK | TRANSACTIS GTW SRS RC MS |
| EQUIPMENT | EQUP12BY | CURBSTONE EC SRS RC MS |
| EQUIPMENT | EQUP12CQ | SITECONTR CFC v8 RC SRS |
| EQUIPMENT | EQUP12CR | InfoNet TPS v2.2 RC SRS |
| EQUIPMENT | EQUP12LE | FTD CCAPI v.3.0.1 RC SRS |
| EQUIPMENT | EQUP12MG | ACI POST v6.1 RC SS EC |
| EQUIPMENT | EQUP12MM | CRQ000000020591_Var |
| EQUIPMENT | EQUP12N3 | Wendys ACI RCS 5.1 SS RC |
| EQUIPMENT | EQUP12NV | Affinipay GTW SMS DW |
| EQUIPMENT | EQUP12OH | Rocketgate ECOM-SMS |
| EQUIPMENT | EQUP12OL | ChargeLogic4.0 RcSrsMsEc |
| EQUIPMENT | EQUP12P2 | ApplGtw RC EC |
| EQUIPMENT | EQUP12P5 | AlacriGWOrbipV8.5RCSRSEC |
| EQUIPMENT | EQUP12RB | Money2India RC EC GTW |
| EQUIPMENT | EQUP12SC | AURUS GTW RC VPN MS |
| EQUIPMENT | EQUP12W7 | One Inc RC |
| EQUIPMENT | EQUP106I | POSLynx220TraNet2.14DWEC |
| EQUIPMENT | EQUP107P | FD Payeezy GTW RC |
| EQUIPMENT | EQUP108L | Nash3Mar10 |
| EQUIPMENT | EQUP108O | Nash4Mar10 |
| EQUIPMENT | EQUP108Q | Nash5Mar10 |
| EQUIPMENT | EQUP1099 | TBMble RC |
| EQUIPMENT | EQUP10A2 | All1Mar13 |
| EQUIPMENT | EQUP10C6 | BuypassMar17 |
| EQUIPMENT | EQUP10IN | Nash6Apr21 |
| EQUIPMENT | EQUP10Z4 | IMS Merchant Link (Welcome Kit only) |
| EQUIPMENT | EQUP1103 | GALLS RC |
| EQUIPMENT | EQUP110T | Jackrabbit V1.0 RC MO |
| EQUIPMENT | EQUP110Y | SecureOne v0.1 MO RC |
| EQUIPMENT | EQUP110Z | LEXISNEXIS GTW EC DW RC |
| EQUIPMENT | EQUP1116 | OmniTkt BUCCS 1.0 RC |
| EQUIPMENT | EQUP1117 | VENTEK TRANSIT RTL DW RC |
| EQUIPMENT | EQUP111Q | PAXBROADPOSPAYv1.0 RC DW |
| EQUIPMENT | EQUP111X | Plug n Pay v1.0 RR RC |
| EQUIPMENT | EQUP112R | CENPOS GTWY SRS DW RC |
| EQUIPMENT | EQUP1131 | Syn-Tech FuelMast 1.1.3.1 |
| EQUIPMENT | EQUP1139 | ATT Wireless |
| EQUIPMENT | EQUP114Z | ACI RCS GTW RC EC MS |
| EQUIPMENT | EQUP1156 | Instamed PPS Internet |
| EQUIPMENT | EQUP115D | VSECURE DW SRS EC RC |
| EQUIPMENT | EQUP116N | WesternUnion GTY |
| EQUIPMENT | EQUP1199 | SS IDTechSecure MSR DWRC |
| EQUIPMENT | EQUP119C | ROAM DATA GTW RC |
| EQUIPMENT | EQUP119K | MC MPGS01 GTW RC SRS |
| EQUIPMENT | EQUP119M | BioTech EC RC SRS |
| EQUIPMENT | EQUP119Q | AJB FIPAYEPSv2.2RCSRS MS |
| EQUIPMENT | EQUP11A0 | FEXCO OpenConectGwDwEcSs |
| EQUIPMENT | EQUP11A9 | Med Staff Echo RC SRS |
| EQUIPMENT | EQUP11B4 | MTDATA SMS DW EC |
| EQUIPMENT | EQUP11BY | PAX S300 RC SRS ISO PTS |
| EQUIPMENT | EQUP11C4 | Viper 8.01.00 VPN RC |
| EQUIPMENT | EQUP11PO | Canadian iCT250 PinPad |
| EQUIPMENT | EQUP11Q7 | Delego V2.5.4 EC RC SRS |
| EQUIPMENT | EQUP11RH | Stripe |
| EQUIPMENT | EQUP11TK | BridgePay GTW RC |
| EQUIPMENT | EQUP11V5 | BCBG Torex 1.5.10 |
| EQUIPMENT | EQUP11VL | Crimson 1.26 RC SRS MS |
| EQUIPMENT | EQUP11VY | AJB FIPAY 2.3 RC SRS SS |
| EQUIPMENT | EQUP11WX | MYCARD GTW RC SRS EC |
| EQUIPMENT | EQUP11X7 | CR1010425_VAR |
| EQUIPMENT | EQUP11Y0 | Viper 8.03.00 VPN RC |
| EQUIPMENT | EQUP11Y4 | PRISMPAY GTW RC SRS EC |
| EQUIPMENT | EQUP11Y7 | TouchNetUC6.5 RCSRSEC MS |
| EQUIPMENT | EQUP11YA | ISO Global RCSRS |
| EQUIPMENT | EQUP11YC | EDC RCSRS |
| EQUIPMENT | EQUP11Z3 | Voltage_Var |
| EQUIPMENT | EQUP11ZA | JACK HENRY GTW RC EC MS |
| EQUIPMENT | EQUP11ZM | Equinox Apollo EMV DW |
| EQUIPMENT | EQUP11ZX | AJB FIPAY EPS v2.3 |
| EQUIPMENT | EQUP122Y | PandaNovadine3D RCSRS EC |
| EQUIPMENT | EQUP126Q | MTDATA SMS DW Retail |
| EQUIPMENT | EQUP127D | MEXICO LANE7000 DW |
| EQUIPMENT | EQUP127R | WF ISO8583 MPLS EC |
| EQUIPMENT | EQUP1288 | CR1076601_var |
| EQUIPMENT | EQUP1289 | LAUREATE GMA RC DWSRS |
| EQUIPMENT | EQUP128M | Bill 1st GTWY DS EC |
| EQUIPMENT | EQUP128Y | PINNACLE NIM 3.0 RC SRS |
| EQUIPMENT | EQUP1295 | VeriFone V400c Plus Terminal |
| EQUIPMENT | EQUP1299 | Navitaire GTW RC EC |
| EQUIPMENT | EQUP129Z | Radial GTW RC EC |
| EQUIPMENT | EQUP12A5 | 4DPayments v16 RcSrsMsEc |
| EQUIPMENT | EQUP12AW | SiteLinkWebEd1.5GTWRCSRS |
| EQUIPMENT | EQUP12B1 | TransparencyX1.0GTWSRSRC |
| EQUIPMENT | EQUP12B9 | FIPAY EPS v2.3 ECOMM |
| EQUIPMENT | EQUP12BD | Paymotion EC SS |
| EQUIPMENT | EQUP12BG | ExaDigm T2 |
| EQUIPMENT | EQUP12BQ | VESTA MX RC ECOMMERCE |
| EQUIPMENT | EQUP12BX | EIGEN MiraServ GTW RC   |
| EQUIPMENT | EQUP12BZ | CURBSTONE EC SRS RC SS |
| EQUIPMENT | EQUP12C6 | Fareportal GTW RC EC |
| EQUIPMENT | EQUP12CA | VeriFone P200 PINPad |
| EQUIPMENT | EQUP12CC | Flight Center DM |
| EQUIPMENT | EQUP12CP | Toshiba ACE v7R5 RC SRS |
| EQUIPMENT | EQUP12K4 | Far Point Systems |
| EQUIPMENT | EQUP12KB | aiCorp RC GW DW SS |
| EQUIPMENT | EQUP12KD | aiCorp RC GW DW EC SS |
| EQUIPMENT | EQUP12KI | ATT CyberSource |
| EQUIPMENT | EQUP12KQ | CR1146132_var |
| EQUIPMENT | EQUP12KU | EIGEN MiraServ GTW RC |
| EQUIPMENT | EQUP12L9 | Cousinsco RC GW DWSRS EC |
| EQUIPMENT | EQUP12LG | TOUCHPEAK 2.8 RCSRS SS |
| EQUIPMENT | EQUP12LH | TOUCHPEAK 2.8 RCSRS MS |
| EQUIPMENT | EQUP12MZ | Rocketgate ECOM-SMS |
| EQUIPMENT | EQUP12ND | tranzpayecdtwrc |
| EQUIPMENT | EQUP12NO | ElectronicPaymentsGTWEC |
| EQUIPMENT | EQUP12O4 | INGENICO FDRC 2.0 GW DW |
| EQUIPMENT | EQUP12O6 | CRQ000000072822_Var |
| EQUIPMENT | EQUP12OF | TRIPLE E v5.2130 RC |
| EQUIPMENT | EQUP12OQ | RC PSN GTW CC 1.2.0 |
| EQUIPMENT | EQUP12OV | Payrix GW RcSrsMsEc |
| EQUIPMENT | EQUP12OX | ApplGtw RC |
| EQUIPMENT | EQUP12P7 | EHI IBMGTW RCCRD ONLY |
| EQUIPMENT | EQUP12PC | Trovato v7 RC DW |
| EQUIPMENT | EQUP12Q4 | PG GTW RC DW |
| EQUIPMENT | EQUP12QO | PAYMENTWALL SRS RC |
| EQUIPMENT | EQUP12QS | CRQ000000152217&CRQ000000151874_Var |
| EQUIPMENT | EQUP12QW | eBay ISO8583 EC |
| EQUIPMENT | EQUP12QZ | Verifone V400M terminal  |
| EQUIPMENT | EQUP12RJ | PayScoutGTWRC SRS EC |
| EQUIPMENT | EQUP12RP | Gilbarco ATL105 v12.0x |
| EQUIPMENT | EQUP12RR | Aptos Pymt 2017.3 RC SRS |
| EQUIPMENT | EQUP12RU | Flight System USA RC MS |
| EQUIPMENT | EQUP12S0 | DUNM RT V2.08 RCTA DWSRS |
| EQUIPMENT | EQUP12S8 | AURUS GTW RC EC VPN MS |
| EQUIPMENT | EQUP12SD | LOYALE GTW RC EC SRS |
| EQUIPMENT | EQUP12TN | Vitu RC EC GTW |
| EQUIPMENT | EQUP12TS | EIGEN MiraServ PTS EC |
| EQUIPMENT | EQUP12TW | N5   v.08.011.XXX |
| EQUIPMENT | EQUP12U0 | ICS CAGE6.0.0.35 RcSrsSs |
| EQUIPMENT | EQUP12U7 | FACGTW ISO ECOMM |
| EQUIPMENT | EQUP12U9 | Viper 8.02.00 RC SRS |
| EQUIPMENT | EQUP12UD | Pineapple GTW RC EC MS |
| EQUIPMENT | EQUP12UF | Pineapple GTW RC EC SS |
| EQUIPMENT | EQUP12UL | Epicor Cloud GTW RC EC |
| EQUIPMENT | EQUP12W0 | GGS GTW ECOMM RC HDC |
| EQUIPMENT | EQUP12W3 | Blue Parasol SRS RC |
| EQUIPMENT | EQUP12WB | Ingenico Lane7000 pp  |
| EQUIPMENT | EQUP12WD | EB MANHATTAN RC EC DWSRS |
| EQUIPMENT | EQUP12WL | Bill Matrix 4.0 GTW EC |
| EQUIPMENT | EQUP12WO | CRQ000000244659_VAR |
| EQUIPMENT | EQUP12WW | Paypoint GTW RC EC |
| EQUIPMENT | EQUP12XA | Ingenico MOVE5000 |
| EQUIPMENT | EQUP1084 | NCR Ecomm RC v3.10 |
| EQUIPMENT | EQUP1137 | NorweiganCL CNP v4 DW RC |
| EQUIPMENT | EQUP119D | Cmps Batch Auth 2.28 |
| EQUIPMENT | EQUP119J | MC MPGS01 GTW EC RC SRS |
| EQUIPMENT | EQUP11BD | WORLDNET GTW EC DW RC |
| EQUIPMENT | EQUP11BL | YARDI SYS GTW EC RC SRS |
| EQUIPMENT | EQUP11W3 | Eddie Bauer RC SRS MOTO |
| EQUIPMENT | EQUP11WZ | HRADIUS GTW HC RC SRS EC |
| EQUIPMENT | EQUP126E | Verifone VX 820 |
| EQUIPMENT | EQUP129D | FIRSTDATAGATEWAY EC |
| EQUIPMENT | EQUP129O | PLXIS GTW RC SS |
| EQUIPMENT | EQUP129V | CR1102105-VAR |
| EQUIPMENT | EQUP12BW | CR18.02_VAR |
| EQUIPMENT | EQUP12KE | aiCorp RC GW DW EC MS |
| EQUIPMENT | EQUP12L6 | CR1157770_VAR |
| EQUIPMENT | EQUP12N0 | Teller 21 |
| EQUIPMENT | EQUP12NX | xpressecgtwrc |
| EQUIPMENT | EQUP12OD | Triple E Technologies |
| EQUIPMENT | EQUP12OK | FocusPOS v10.1 SRS ms |
| EQUIPMENT | EQUP12PJ | advmobilepymtdtwrc |
| EQUIPMENT | EQUP12QA | March Release_1 |
| EQUIPMENT | EQUP12QB | PecanSolutionsV2.0 RC |
| EQUIPMENT | EQUP12QG | Gilbarco ATL105 v11.04IP |
| EQUIPMENT | EQUP12QJ | MEXICO LINK2500 BT |
| EQUIPMENT | EQUP12QX | FD150 |
| EQUIPMENT | EQUP12RT | Flight System USA RC SS |
| EQUIPMENT | EQUP12S6 | AURUS GTW RC EC SRS MS |
| EQUIPMENT | EQUP12SK | CRQ000000172914_VAR |
| EQUIPMENT | EQUP12SO | Gateway MID |
| EQUIPMENT | EQUP12UU | Softheon GTW RC EC |
| EQUIPMENT | EQUP12WC | UCom Buypass Gateway |
| EQUIPMENT | EQUP12WN | BluefinGateway Gw |
| EQUIPMENT | EQUP12X3 | Sabre RSA007 MC CNP RC |
| EQUIPMENT | EQUP12XB | APG VERIFONE RC   |
| EQUIPMENT | EQUP1177 | CSG SYSTEMS GTW RC   |
| EQUIPMENT | EQUP12R0 | SpeedyCash RC EC |
| EQUIPMENT | EQUP108B | ANYWCOM GTWY RC DW |
| EQUIPMENT | EQUP108K | CompassMar10 |
| EQUIPMENT | EQUP10YY | IBM (Global) ISO 8583 Lease Line |
| EQUIPMENT | EQUP115U | VIVONET 1.15 RC DW |
| EQUIPMENT | EQUP11AY | TCxGravity v2.1.4 RC SRS |
| EQUIPMENT | EQUP11C8 | SPARROWONEGTW RC SRS |
| EQUIPMENT | EQUP11SV | CONNECTX GTW RCSRS SS |
| EQUIPMENT | EQUP1222 | CR1020046_VAR 2 |
| EQUIPMENT | EQUP12A1 | FIPAY EPS v2.3 DW |
| EQUIPMENT | EQUP113H | GNC 01 RC |
| EQUIPMENT | EQUP11QM | FD OMAHA RC |
| EQUIPMENT | EQUP11U8 | Pac Life Genius CC RCSRS |
| EQUIPMENT | EQUP123P | E PROC NET GTW OTC RC |
| EQUIPMENT | EQUP123Q | Palm Coast Data GTW EC |
| EQUIPMENT | EQUP12CN | P97 v1 RC IP |
| EQUIPMENT | EQUP12L8 | Billhighway RC EC |
| EQUIPMENT | EQUP12LK | SI DCAP Cousinsco |
| EQUIPMENT | EQUP12MF | ACI POST v6.1 RC SS IP |
| EQUIPMENT | EQUP12O1 | gSwitch v.2.0. software |
| EQUIPMENT | EQUP12PO | XAC XPAY v1.0 RcSrsSs |
| EQUIPMENT | EQUP12QD | Paycertify GTW SS |
| EQUIPMENT | EQUP12R1 | Wirecard RC SRSGTWYDW EC |
| EQUIPMENT | EQUP12RI | ADYEN GATEWAY |
| EQUIPMENT | EQUP12RQ | Dataline GTW Comp |
| EQUIPMENT | EQUP12T0 | VF Trio-CAGE-RC DW SRS |
| EQUIPMENT | EQUP12T5 | HOLLAND NASH ISO8583 |
| EQUIPMENT | EQUP12TZ | Currencypay GTW RC |
| EQUIPMENT | EQUP12U4 | CRQ000000207963_Class var |
| EQUIPMENT | EQUP12WJ | 0216_VAR |
| EQUIPMENT | EQUP116A | Payfirma GTW RC DW EC |
| EQUIPMENT | EQUP116W | IT Retail DW RC SRS |
| EQUIPMENT | EQUP128D | OnePay GTW SRS RC |
| EQUIPMENT | EQUP128F | FAREPORTAL RC EC DWSRS |
| EQUIPMENT | EQUP129A | Navitaire GTW RC MoTo |
| EQUIPMENT | EQUP12LM | LOCOMOBI303 DW RC |
| EQUIPMENT | EQUP12Y5 | Invenco tbrixpay1 RC SRS |
| EQUIPMENT | EQUP12YD | Monetra8.x NativeSRS EC |
| EQUIPMENT | EQUP12YF | UCOM GTW ECOM RC DW |
| EQUIPMENT | EQUP12YG | EQUINOX 1.x RC SS |
| EQUIPMENT | EQUP12YH | GK Trans+ V8 RC SRS |
| EQUIPMENT | EQUP12YY | ISO 8583 Lease Line Auto |
| EQUIPMENT | EQUP12Z5 | 10/9_VAR4 |
| EQUIPMENT | EQUP12Z9 | Worldpay FIS v2.X PRJ507 |
| EQUIPMENT | EQUP12ZB | 20/9_VAR3 |
| EQUIPMENT | EQUP12ZE | 20/9_VAR1 |
| EQUIPMENT | EQUP12ZL | 1stMileZ3PRDC GTW RC EC  |
| EQUIPMENT | EQUP13AB | 11/08_VAR |
| EQUIPMENT | EQUP13AT | Datawire - compass north |
| EQUIPMENT | EQUP13B0 | AuthCore RC Compass Nort |
| EQUIPMENT | EQUP13B8 | 16/1_VAR6 |
| EQUIPMENT | EQUP13BK | Tempus GTW ISO 8583 EC |
| EQUIPMENT | EQUP13CI | 21/2_VAR78 |
| EQUIPMENT | EQUP13CU | GTW Tempus |
| EQUIPMENT | EQUP13IZ | Freedom Freeway V4.0 ISO |
| EQUIPMENT | EQUP13L1 | Linga CP (Magensa |
| EQUIPMENT | EQUP12ZA | Privacy.Com EC |
| EQUIPMENT | EQUP13AC | 11/08_VAR_01 |
| EQUIPMENT | EQUP13AV | Direct Send Compass Nort |
| EQUIPMENT | EQUP13BA | 16/1_VAR6 |
| EQUIPMENT | EQUP13BH | Presto Payment App v2.0 |
| EQUIPMENT | EQUP13BN | Yapstone RC SRS |
| EQUIPMENT | EQUP13CP | GTW for Card Connect |
| EQUIPMENT | EQUP13D3 | Pineapple V1.8.0 GTW RC |
| EQUIPMENT | EQUP13DN | 17/4_VAR40 |
| EQUIPMENT | EQUP13DV | PNC CyberSource MOTO |
| EQUIPMENT | EQUP13E2 | BBPOS Wisepad 2 |
| EQUIPMENT | EQUP13F0 | MIDAX EFT v3.2 RC SRS |
| EQUIPMENT | EQUP13FF | GKTRANS+V8 RC-SRS-MS |
| EQUIPMENT | EQUP13FI | 15/7_VAR28 |
| EQUIPMENT | EQUP13FW | PaymentPro 2.0 RC |
| EQUIPMENT | EQUP13G6 | Vx690 ISO DUAL |
| EQUIPMENT | EQUP13IG | AAFES Stargate RC SRS |
| EQUIPMENT | EQUP13J8 | UIC vL31A1001 RC SRS MS |
| EQUIPMENT | EQUP13LE | NMI OmniGTWY ISO |
| EQUIPMENT | EQUP13N4 | WeVend GTW RC SRS SS |
| EQUIPMENT | EQUP13O0 | WizarPOSFiservApp 0.1 RC |
| EQUIPMENT | EQUP3ECA | ECA LINKPOINT 3000 |
| EQUIPMENT | EQUPACRP | KMAC CORP RC |
| EQUIPMENT | EQUPATES | cGATE |
| EQUIPMENT | EQUP12Z7 | USAT ePort 1.0 RC EC |
| EQUIPMENT | EQUP13A5 | Wildblue EC |
| EQUIPMENT | EQUP13CM | MagensaDandF RCSRS Petro |
| EQUIPMENT | EQUP13CN | VF Viper 8.11.00 RC VPN  |
| EQUIPMENT | EQUP13D9 | SWBC EC |
| EQUIPMENT | EQUP13FQ | DYNAMPAYM EC SRS RC |
| EQUIPMENT | EQUP13GH | Monetra8 EDC SrsMs |
| EQUIPMENT | EQUP13HM | Verfione V400 Eigen Reta |
| EQUIPMENT | EQUP13IX | Pace Software RC EC |
| EQUIPMENT | EQUP13JJ | CastletechV1.1.3SRSRCNSV |
| EQUIPMENT | EQUP13KW |  Gilbarco ATL105 v22 SRS |
| EQUIPMENT | EQUP13KY | Patch 9-18-22 |
| EQUIPMENT | EQUP13O3 | Pay Theory RC DW 2.x |
| EQUIPMENT | EQUP13OB | 06/22_UI_Release  |
| EQUIPMENT | EQUP13Q4 | Gilbarco ATL105 v23 SRS |
| EQUIPMENT | EQUPDLIC | Pro Add MID License |
| EQUIPMENT | EQUPGMCB | CLASS B ExaDigm NX1200 |
| EQUIPMENT | EQUPHPN1 | MRCH PRTNR GWY SINGLE EC |
| EQUIPMENT | EQUP13HH | VeriFone SCA Engage |
| EQUIPMENT | EQUPISMD | CSTARS Dimondscan v1.0 |
| EQUIPMENT | EQUP12YL | 08_16_VAR |
| EQUIPMENT | EQUP13FU | PNC EPC |
| EQUIPMENT | EQUP12Y9 | BraintreeWellsSP Retail  |
| EQUIPMENT | EQUP12ZY | Target EC Compass North |
| EQUIPMENT | EQUP13A4 | PineappleV.1.2.0 GTW RC |
| EQUIPMENT | EQUP13AO | COMPASS NORTH XML  |
| EQUIPMENT | EQUP13BP | CORECOMMERCESRSRC |
| EQUIPMENT | EQUP13BQ | CORECOMM SRS EC RC |
| EQUIPMENT | EQUP13CO | Biller Genie RC |
| EQUIPMENT | EQUP13CR | GTWY Cybersource |
| EQUIPMENT | EQUP13DJ | Sample_PC04 |
| EQUIPMENT | EQUP13J7 | Pace Software RC EC MS |
| EQUIPMENT | EQUP13JN | 17/5_VAR24 |
| EQUIPMENT | EQUP13JU | FIS Chevron RC GTW SS |
| EQUIPMENT | EQUP13LX | Toshiba EleraPay RC SRS |
| EQUIPMENT | EQUP380X | Omni 380 X2 |
| EQUIPMENT | EQUP4VAM | Ver 4.00 ICVERIFY Val Code - Add MIDs |
| EQUIPMENT | EQUP13B1 | Pineapple GTW RC EC1.3.0 |
| EQUIPMENT | EQUP13BD | 17/1_VAR91 |
| EQUIPMENT | EQUP13BJ | iZettle RC DW  |
| EQUIPMENT | EQUP13BR | Autobooks RC |
| EQUIPMENT | EQUP13D1 | 21/3_VAR22 |
| EQUIPMENT | EQUP13EB | 20/5_VAR54 |
| EQUIPMENT | EQUP13ED | FIVESTARS SRS RC |
| EQUIPMENT | EQUP13EG | Bill Subscription |
| EQUIPMENT | EQUP13F4 | PAX A920 Pro |
| EQUIPMENT | EQUP13FV | IT Retail GTW RC |
| EQUIPMENT | EQUP13HG | Wex 3Delta Systems  |
| EQUIPMENT | EQUP13HR | ElectronicPay RC GTWY |
| EQUIPMENT | EQUP13I5 | Ingenico USIv2 RcSrsSs |
| EQUIPMENT | EQUP13IY | eMerchantPay RC |
| EQUIPMENT | EQUP13JI | Aurus Auruspay RC MPLS |
| EQUIPMENT | EQUP13MA | CAD Move5000 PCI6 RC |
| EQUIPMENT | EQUP13MJ | CardConnect GTW MS |
| EQUIPMENT | EQUP13MP | Orbipay EC GTW RC v66.0 |
| EQUIPMENT | EQUP13MQ | Liquid Payments CC |
| EQUIPMENT | EQUP13MS | PLUGNPAY V4.2 RC DTW |
| EQUIPMENT | EQUP13NL | 05/11_Var_Prod123 |
| EQUIPMENT | EQUP13NP | 12/5_VAR12_Prod123 |
| EQUIPMENT | EQUP13NQ | Switchio GTWTRAN ISO8583 |
| EQUIPMENT | EQUP13OH | ACI RCS v5.2 BUYP GTW IP |
| EQUIPMENT | EQUP13OQ | Key Accept Sync w CardCo |
| EQUIPMENT | EQUP13OX | PayArc RC |
| EQUIPMENT | EQUP13Q6 | Verifone GLB Pymt GTW RC |
| EQUIPMENT | EQUP13QL | Payology DS RC V1 |
| EQUIPMENT | EQUP1C01 | HYPERCOM T7 SOFTWARE |
| EQUIPMENT | EQUP1CLD | 911 CLOUD 9 PMNTS GTWY |
| EQUIPMENT | EQUP20OB | USAA (E-Commerce) |
| EQUIPMENT | EQUP20OL | Mexico Vx520 Duo |
| EQUIPMENT | EQUP20OR | ABC Financial |
| EQUIPMENT | EQUP20OX | Beanstream ICMP |
| EQUIPMENT | EQUP20Q8 | Sicom Systems w EMV |
| EQUIPMENT | EQUP20QT | Canadian MX925 IntPinPad |
| EQUIPMENT | EQUP20QW | Canadian ISMP IntPinPad |
| EQUIPMENT | EQUP20QX | Canadian IWL222 IntPinPad |
| EQUIPMENT | EQUP300Z | FD300 Terminal |
| EQUIPMENT | EQUP3MNT | Element Pmnt Svc GTWY |
| EQUIPMENT | EQUP3S01 | GO SOFTWARE JAVACARD |
| EQUIPMENT | EQUP4VCM | Ver 4.00 ICVERIFY Val Code-Change MID or Processor |
| EQUIPMENT | EQUP5PKH | PTI-Tellan MAC HUB 5Pk TDC |
| EQUIPMENT | EQUP70DC | VX570 |
| EQUIPMENT | EQUPACSE | TELECHECK ACCELERA SE |
| EQUIPMENT | EQUPAIM1 | AIM |
| EQUIPMENT | EQUPAINT | Braintree GTWY |
| EQUIPMENT | EQUPAMAC | PTI-Tellan MAC Auth HDC |
| EQUIPMENT | EQUPAR01 | DESCARTES, INC |
| EQUIPMENT | EQUPAXSW | RC PAX BROAD POS V1.0.0 |
| EQUIPMENT | EQUPAYG9 | MPAY Gateway |
| EQUIPMENT | EQUPBERT | THE SHUBERT ORG GATEWAY |
| EQUIPMENT | EQUPC0M2 | Incomm EC |
| EQUIPMENT | EQUPCA01 | SBC SOLUTIONS |
| EQUIPMENT | EQUPCBJD | ISO LL Global with Full Tid and no Purc/Com |
| EQUIPMENT | EQUPCD3C | SLIM CD GATGEWAY ECOM |
| EQUIPMENT | EQUPCDPD | PTI-Nurit 3010 CDPD |
| EQUIPMENT | EQUPCR0S | Micros D5v1 6 |
| EQUIPMENT | EQUPCSFW | LOCBPATL105 V3.4.0 |
| EQUIPMENT | EQUPDNL7 | Cardinal Comm RC GTW |
| EQUIPMENT | EQUPDRB1 | DRB |
| EQUIPMENT | EQUPDV52 | ISD Pay Switch Ste v5.2 |
| EQUIPMENT | EQUPDVD2 | Board Vend TA RC DW EC |
| EQUIPMENT | EQUPDXMR | INDEX GTWY MULTI SETL RC |
| EQUIPMENT | EQUPED26 | AldeloEDC6.1.0.26 |
| EQUIPMENT | EQUPFT4T | SHIFT4 $$$ GATEWAY |
| EQUIPMENT | EQUPILG2 | RETAILDECRED1 GTWY ECOM |
| EQUIPMENT | EQUP13KK | VF FIPAY CYBER GTW  |
| EQUIPMENT | EQUP13LN | CompuTop GTWY RC EC |
| EQUIPMENT | EQUP13MN | LiquidPayments |
| EQUIPMENT | EQUP20OW | Beanstream DM (G/W) singel settlement |
| EQUIPMENT | EQUP20Q1 | CalendonCardServices Ret/DM Authonly-G/W |
| EQUIPMENT | EQUP20QU | Canadian ICMP IntPinPad |
| EQUIPMENT | EQUP4C01 | HYPERCOM NAC-1A |
| EQUIPMENT | EQUP77GT | HYPERCOM T77G-T |
| EQUIPMENT | EQUP8PCI | NURIT 8400 TERMINAL |
| EQUIPMENT | EQUPANIS | Brinkman ISO GTWY |
| EQUIPMENT | EQUPAPLC | Verifone Payware VAR Applicaion |
| EQUIPMENT | EQUPCA51 | Casio 5100 |
| EQUIPMENT | EQUPCBJC | ISO LL Global with Full Tid and Purc/Com |
| EQUIPMENT | EQUPCLSY | Sacramento Regional Transit |
| EQUIPMENT | EQUPCLUX | Micros X Store LUX |
| EQUIPMENT | EQUPCLYT | Official Payments GTW |
| EQUIPMENT | EQUPCO52 | Princtonpaycardconecom52 |
| EQUIPMENT | EQUPCOES | Express Scripts |
| EQUIPMENT | EQUPCRDS | CreditCl Crdease GTWY EC |
| EQUIPMENT | EQUPDCAN | CANTALOUPE SEED GATEWAY |
| EQUIPMENT | EQUPDV65 | ISD PAY SWITCH JAVA V6.5 |
| EQUIPMENT | EQUPEOST | KFC Merit POS |
| EQUIPMENT | EQUPG1A1 | 1and1 Internet Gateway |
| EQUIPMENT | EQUPGEN1 | PC-Generic |
| EQUIPMENT | EQUPGWNC | NC Gateway |
| EQUIPMENT | EQUPINGT | VFI PWC NashMultiGtwyEC |
| EQUIPMENT | EQUPIPOS | Envoy IPOS Cash Register |
| EQUIPMENT | EQUPIV40 | Xpient v4.00.15 |
| EQUIPMENT | EQUP8974 | 125555 |
| EQUIPMENT | EQUPDCNA | CardCana Corp (G/W)  |
| EQUIPMENT | EQUPEPOS | PrecidiaPOSLYNXMini |
| EQUIPMENT | EQUPIC05 | v2.60 ICV Win M-User Up |
| EQUIPMENT | EQUPIMC1 | Slim CD |
| EQUIPMENT | EQUPINT2 | Verisign Retail/MOTO |
| EQUIPMENT | EQUP13G9 | Motion BAMS CNP |
| EQUIPMENT | EQUP13MR | Liquid Payments CC |
| EQUIPMENT | EQUPBLDR | eWebuilder (g/w) |
| EQUIPMENT | EQUP13BW | Caleres GetPAN RC |
| EQUIPMENT | EQUP13D8 | EIGEN DEV PTS 2 GTW |
| EQUIPMENT | EQUP13F5 | PAX A920 mobile |
| EQUIPMENT | EQUP13F8 | 17/6_VAR33 |
| EQUIPMENT | EQUP13FX | SOLUPAY RC GTW EC |
| EQUIPMENT | EQUP13G1 | 19/8_VAR48 |
| EQUIPMENT | EQUP13J5 | PDI EXC EFC v8.0 RC VPN |
| EQUIPMENT | EQUP13M8 | NCR AlohaEDC v19.6 SRS |
| EQUIPMENT | EQUP13Q3 | Gilbarco ATL105 v23 IP |
| EQUIPMENT | EQUP13Q7 | Paypoint GTW RC NV |
| EQUIPMENT | EQUP20OC | ChargeIt! |
| EQUIPMENT | EQUP20OK | Canadian Vx820 |
| EQUIPMENT | EQUP20OT | IMS Merchant Link |
| EQUIPMENT | EQUP20QQ | CenPos MX915 |
| EQUIPMENT | EQUP20QY | Canadian IWL252 IntPinPad |
| EQUIPMENT | EQUP3564 | 34563 |
| EQUIPMENT | EQUP395D | OMNI 395 Dial |
| EQUIPMENT | EQUP4NMU | Ver 4.00 ICVERIFY Windows New Multi User |
| EQUIPMENT | EQUP4WSU | Ver 4.00 ICVERIFY Windows Setup |
| EQUIPMENT | EQUP8474 | 88888 |
| EQUIPMENT | EQUP8GPR | NURIT 8000 GPRS PCI |
| EQUIPMENT | EQUPAGPP | AutoGas Pay-At-The-Pump |
| EQUIPMENT | EQUPALTM | Official Payments GTW EC |
| EQUIPMENT | EQUPAMCA | PCAM POS Suite12.603Nash |
| EQUIPMENT | EQUPAQUA | AQUA Dial |
| EQUIPMENT | EQUPAYEC | VPAY v5.10.523 EC |
| EQUIPMENT | EQUPBDX5 | DejavooX-5 |
| EQUIPMENT | EQUPBER2 | AssurePay IntegriCharge (g/w) |
| EQUIPMENT | EQUPBITP | Orbit PayLink Gateway |
| EQUIPMENT | EQUPBUYP | Buypass Generic Pay-At-The-Pump |
| EQUIPMENT | EQUPC581 | Vrfne PCChg 5.8.1 |
| EQUIPMENT | EQUPCBJQ | EDC TransArmor |
| EQUIPMENT | EQUPCBKV | Hlhost (LL) with Full Tid & Purc/com card |
| EQUIPMENT | EQUPCKMT | IVI CHKMT ENCHECK3000 |
| EQUIPMENT | EQUPCM2F | PAYwarTransactECOMM3.2.4 |
| EQUIPMENT | EQUPCO01 | CLEARCOMMERCE CORP |
| EQUIPMENT | EQUPCRET | MICROS Retail R.C. |
| EQUIPMENT | EQUPCRMT | MagTek MiniMicr Check Reader |
| EQUIPMENT | EQUPCSC1 | Decision Systems (LL) |
| EQUIPMENT | EQUPCT6 | CT6 Terminal |
| EQUIPMENT | EQUPCV64 | CYBRSOURCE CPM V6.4 ECOM |
| EQUIPMENT | EQUPDASY | QS/1 Data Systems |
| EQUIPMENT | EQUPEKSR | Softek RC |
| EQUIPMENT | EQUPELIC | Pro Add User License |
| EQUIPMENT | EQUPES82 | MTXWinEPSv826.1 |
| EQUIPMENT | EQUPFINT | ASF Retail |
| EQUIPMENT | EQUPGNUS | FTS Cygnus POS 4.01 |
| EQUIPMENT | EQUPGPAY | Plug and Pay Gateway |
| EQUIPMENT | EQUPGTWY | Innotrac CRMS GTWY |
| EQUIPMENT | EQUPIPA4 | VeriFone PAYware Mobile |
| EQUIPMENT | EQUPIZNT | Posnet v1.0 RC NashISO |
| EQUIPMENT | EQUPKPNT | Bank Point Pin Pad |
| EQUIPMENT | EQUP13FR | DYNAMPAYM SRS RC |
| EQUIPMENT | EQUP13O2 | 06/08_VAR12_Prod123 |
| EQUIPMENT | EQUP13Q5 | Payway Inc EC GTW |
| EQUIPMENT | EQUP200P | FD200 |
| EQUIPMENT | EQUP2085 | PTI-Nurit 2085 |
| EQUIPMENT | EQUP20OM | Mexico Vx675 3G |
| EQUIPMENT | EQUP20OY | RM3 South |
| EQUIPMENT | EQUP20Q6 | Element P S VX820 |
| EQUIPMENT | EQUP20Q7 | Wal-Mart Canada |
| EQUIPMENT | EQUP20QC | Ann Taylor AJB |
| EQUIPMENT | EQUP20QD | Zale Corp. AJB Mx880 |
| EQUIPMENT | EQUP20QH | AJB American Eagle e315 |
| EQUIPMENT | EQUP20QJ | Six Payment Solutions VX820 |
| EQUIPMENT | EQUP20QM | TMC |
| EQUIPMENT | EQUP20S1 | LAC Migration |
| EQUIPMENT | EQUP20S2 | LAC OpenSolutions Vx510 Ver.04D |
| EQUIPMENT | EQUP2V01 | ICVERIFY PREV CYBERCASH |
| EQUIPMENT | EQUP300W | FD300 WiFi  |
| EQUIPMENT | EQUP30PR | VIVOPAY 3000 PROXIMITY READER |
| EQUIPMENT | EQUP3100 | EN-TOUCH 3100 |
| EQUIPMENT | EQUP3210 | VERIF-OMNI 3210 TERM FDR |
| EQUIPMENT | EQUP3740 | Omni 3740 |
| EQUIPMENT | EQUP395L | Omni 395 LAN |
| EQUIPMENT | EQUP4ECM | SHIFT4 $$$ GATEWAY ECOM |
| EQUIPMENT | EQUP4MUU | Ver 4.00 ICVERIFY Windows Multi User Up |
| EQUIPMENT | EQUP4SUR | Shift4 Software 4$URE |
| EQUIPMENT | EQUP670G | VX670 GPRS WIRELESS |
| EQUIPMENT | EQUP8888 | 25635578689/9/9/ |
| EQUIPMENT | EQUP9999 | zfcasfasf |
| EQUIPMENT | EQUPALDS | REDFALLS GATEWAY ECOM |
| EQUIPMENT | EQUPAMEC | AAA Midatlantic ECRC |
| EQUIPMENT | EQUPAMRP | PC America Restaurant Pro |
| EQUIPMENT | EQUPANSC | Transact Leased Line |
| EQUIPMENT | EQUPANTS | JCP Proprietary Software |
| EQUIPMENT | EQUPATGT | TGATE GTWY |
| EQUIPMENT | EQUPATP | Envoy ATP |
| EQUIPMENT | EQUPAULS | WebAuthorize LL Solaris |
| EQUIPMENT | EQUPBALF | Herbalife |
| EQUIPMENT | EQUPBLCO | ENablerPGW Nash RCECV1.0 |
| EQUIPMENT | EQUPBPGS | Buypass Generic Integrated Solution |
| EQUIPMENT | EQUPBRTS | SEARS AJB RTS SWITCH (VAR) |
| EQUIPMENT | EQUPBTEC | KFC ONOSYS GTWY EC |
| EQUIPMENT | EQUPBUY3 | DATACAP DialTran3.0 BUYP |
| EQUIPMENT | EQUPBYR2 | Cybersource ICS2 (Ecom) |
| EQUIPMENT | EQUPC001 | RESTAURANT DAA CONCEPTS |
| EQUIPMENT | EQUPC0M1 | Incomm |
| EQUIPMENT | EQUPC2MT | IP Commerce Gateway ECOM |
| EQUIPMENT | EQUPCASH | Cash Register |
| EQUIPMENT | EQUPCB11 | Pinnacol |
| EQUIPMENT | EQUPCBKN | VP Term with Full tid and Purc/Com card |
| EQUIPMENT | EQUPCCTE | CCIS Tech |
| EQUIPMENT | EQUPCGRL | Dataexchange 6.3 |
| EQUIPMENT | EQUPCHUB | MacAuth Hub Internet Dial |
| EQUIPMENT | EQUPCL01 | DRY CLEANING COMPTR SYS |
| EQUIPMENT | EQUPCLIS | LJS COMPRIS CARDNET |
| EQUIPMENT | EQUPCM2G | FIS CLEARCMRCE GTWY ECOM |
| EQUIPMENT | EQUPCPV4 | EDGCAPTURE V4.0 |
| EQUIPMENT | EQUPCT5 | CT5 Terminal |
| EQUIPMENT | EQUPCV83 | Radiant Counterpt v8.3 |
| EQUIPMENT | EQUPCWFB | Wells Fargo SVT |
| EQUIPMENT | EQUPD123 | equipsetup4 |
| EQUIPMENT | EQUPDCFD | AAA_AO DUAL 256K MPLS  |
| EQUIPMENT | EQUPDCIA | Vindicia Gateway ECOM |
| EQUIPMENT | EQUPDEC1 | LiveProcessor |
| EQUIPMENT | EQUPDESE | CreditCall Crdease GTWY |
| EQUIPMENT | EQUPDGRD | BridgePayGuard ISO GTW |
| EQUIPMENT | EQUPDJC5 | Dejavoo C-5 |
| EQUIPMENT | EQUPDMZT | PITNEY BOWES/ IBM DIRECT / IMS |
| EQUIPMENT | EQUPDOAK | RedOak VPN v.1.0 RC |
| EQUIPMENT | EQUPDOTR | MA DOT - ECOM |
| EQUIPMENT | EQUPDQZW | RTD Scheidt-Bachman |
| EQUIPMENT | EQUPDV90 | DVM90 Digital Voice Multiplexer |
| EQUIPMENT | EQUPDVD1 | Board Vend TA RC DW |
| EQUIPMENT | EQUPDXSS | INDEX GTWY SINGL SETL RC |
| EQUIPMENT | EQUPDYD7 | BenseronEvol Bevo v2.01 |
| EQUIPMENT | EQUPEBLD | Dream Builders |
| EQUIPMENT | EQUPEV7X | HotSauceTechnologyEVS7.0 |
| EQUIPMENT | EQUPEWRD | mPayMe DW RC GTWY |
| EQUIPMENT | EQUPEXVM | RC IDEXX NASH DV MAX V8 |
| EQUIPMENT | EQUPFH01 | RAMSEY SOLUTIONS HOSPITA |
| EQUIPMENT | EQUPFRLS | Styles for LessEpicor |
| EQUIPMENT | EQUPFSMH | Golfsmith RC |
| EQUIPMENT | EQUPFTJ2 | Envoy FTP JR II |
| EQUIPMENT | EQUPFTP4 | Envoy FTP4 |
| EQUIPMENT | EQUPFXWY | Infonox Gateway |
| EQUIPMENT | EQUPG2WY | ELAVON FUSEBOX  |
| EQUIPMENT | EQUPG911 | 911 software |
| EQUIPMENT | EQUPGANW | CHARGEANYWHERE V2.0.0 |
| EQUIPMENT | EQUPGECO | ELEC PMNT PG GTWY ECOM |
| EQUIPMENT | EQUPGIC1 | Logic Solutions Inc |
| EQUIPMENT | EQUPGICN | LogicNet Gateway |
| EQUIPMENT | EQUPGIL1 | Edgil (Reatil/MOTO) |
| EQUIPMENT | EQUPGMIC | Ingram Micro |
| EQUIPMENT | EQUPGRCE | Hermes of Paris - Ingenico - 16780 |
| EQUIPMENT | EQUPGTCM | Intellipay Gateway ECOM |
| EQUIPMENT | EQUPGTRT | U Bookstore U District |
| EQUIPMENT | EQUPGYEC | Imprezzio Gateway Ecom |
| EQUIPMENT | EQUPHAV4 | ALOHA SUITE V6.4 |
| EQUIPMENT | EQUPHUB | HUB - Spare ID |
| EQUIPMENT | EQUPI5PR | VIVOPAY I5PR PROXIMITY READER |
| EQUIPMENT | EQUPIAJB | Scoop Management AJB/KWI |
| EQUIPMENT | EQUPIC04 | v2.60 ICV Win S-User Up |
| EQUIPMENT | EQUPIFT4 | ON THE NET |
| EQUIPMENT | EQUPIG7Y | PSiGate Gateway ECOM |
| EQUIPMENT | EQUPILSG | Agilysys LMS v7.3 single |
| EQUIPMENT | EQUPINN1 | PC Innovations |
| EQUIPMENT | EQUPINTS | Integrated Services (ISI) |
| EQUIPMENT | EQUPIRST | BRINK POS Rest RC |
| EQUIPMENT | EQUPISGW | TrustCom ISO GTW |
| EQUIPMENT | EQUPISY1 | Amigo Systems (Retail/Moto) |
| EQUIPMENT | EQUPIY01 | UNICOMP |
| EQUIPMENT | EQUP20S0 | Plug and Pay Gateway EMV |
| EQUIPMENT | EQUP8320 | NURIT 8320 TERMINAL |
| EQUIPMENT | EQUPBPWM | Basspoint w/EFT Manager |
| EQUIPMENT | EQUPBRE1 | Sabre |
| EQUIPMENT | EQUPCA20 | Casio 2000 |
| EQUIPMENT | EQUPCHE1 | NDC Health |
| EQUIPMENT | EQUPCMAT | IP Commerce Gateway |
| EQUIPMENT | EQUPCTCM | E-xact Compass GTWY |
| EQUIPMENT | EQUPCWRE | ORCC PAYWRE GATEWAY |
| EQUIPMENT | EQUPCXPM | 3C Payment GTW ms EC |
| EQUIPMENT | EQUPDSTM | Rapid info sys RC |
| EQUIPMENT | EQUPDSYS | Radiant Epsilon ATL105 |
| EQUIPMENT | EQUPET01 | SPECTRUM TECHNOLOGIES |
| EQUIPMENT | EQUPFV10 | Syn-TechFuelMasterv1.0 |
| EQUIPMENT | EQUPHDGW | ACH Direct(Trans Processor)E-comm-G/W |
| EQUIPMENT | EQUPHLIV | NovaLibra1.3  EC |
| EQUIPMENT | EQUPIPSE | Eclipse ECA Capable |
| EQUIPMENT | EQUPIS01 | CORNERSTONE IS |
| EQUIPMENT | EQUPFISC | Fiscal Systems |
| EQUIPMENT | EQUP13OD | Epicor 2023 R1 GTW RC |
| EQUIPMENT | EQUP1S01 | GO SOFTWARE PCCHARGEPRO |
| EQUIPMENT | EQUPC211 | PinnacleCAVNIMv2.1.1 |
| EQUIPMENT | EQUPCA40 | Xpient CCAppl v4.0 |
| EQUIPMENT | EQUPCSWR | LOC Buypass ATL105 SMS V3.3 |
| EQUIPMENT | EQUPCWXZ | VFI RC PC Charge |
| EQUIPMENT | EQUPDH3N | PassportEDHv8.02.23.03N |
| EQUIPMENT | EQUP13IK | Canadian VFI V400m RC |
| EQUIPMENT | EQUP13L7 | Everlink GW |
| EQUIPMENT | EQUP20QN | Mexico On Nashville |
| EQUIPMENT | EQUP20QS | Canadian MX915 IntPinPad |
| EQUIPMENT | EQUP301M | Lipman 3010 Motient |
| EQUIPMENT | EQUP3DLT | 3Delta Gateway |
| EQUIPMENT | EQUP8583 | ISO 8583 Lease Line |
| EQUIPMENT | EQUP9GTE | LAT19 GTWY ECOM    |
| EQUIPMENT | EQUPAEPY | USA ePay |
| EQUIPMENT | EQUPAMAT | AAA Midatlantic RC |
| EQUIPMENT | EQUPBATD | Web Authorize Dial |
| EQUIPMENT | EQUPBFIP | Vanilla Sky AJB |
| EQUIPMENT | EQUPBPWP | Basspoint w/P2K |
| EQUIPMENT | EQUPCV60 | TicTech Rev Cont v6.08 |
| EQUIPMENT | EQUPDI01 | ADVANCED DIST SYSTEMS |
| EQUIPMENT | EQUPDJM3 | Dejavoo M-3 |
| EQUIPMENT | EQUPDSTK | Wordstock CCA V 8.00EDC |
| EQUIPMENT | EQUPELST | CENTURY 21 |
| EQUIPMENT | EQUPENEC | Adyen GTW EC |
| EQUIPMENT | EQUPEV62 | Speedline v6.2 |
| EQUIPMENT | EQUPFONE | VERIFONE GATEWAY |
| EQUIPMENT | EQUPGAWE | ChargeAnywhere RC EC GTY |
| EQUIPMENT | EQUPGBOY | Gasboyy Integrated |
| EQUIPMENT | EQUPGEPS | SAGE PMNT SOLUT GTWY |
| EQUIPMENT | EQUPGT8Y | XIGN GATEWAY |
| EQUIPMENT | EQUPGWYZ | ROAMDATAGATEWAY |
| EQUIPMENT | EQUPHDEM | ACH Direct Gateway ECOM |
| EQUIPMENT | EQUPHE01 | ARGUS HEALTH TECHNOLOGIE |
| EQUIPMENT | EQUPHISO | WordstockCCA V 8.00 |
| EQUIPMENT | EQUPHLU1 | Magic Terminals |
| EQUIPMENT | EQUPIECM | Kaiser ACI EC |
| EQUIPMENT | EQUPIMC2 | SLIM CD (GATEWAY) |
| EQUIPMENT | EQUPIX01 | TPI SOFTWARE |
| EQUIPMENT | EQUPJASV | Dejavoo V-9+ |
| EQUIPMENT | EQUPLC01 | BOOKLOG/COMPUTERWORKS |
| EQUIPMENT | EQUPBLSD | $inBank (Leased Line/Windows) |
| EQUIPMENT | EQUPBPX8 | Class B PAX S58  |
| EQUIPMENT | EQUPC631 | CyberSourceCPMv6.3.1 |
| EQUIPMENT | EQUPCBOP | BAMS TSYS equiptype - DATACARD PIN PAD |
| EQUIPMENT | EQUPCKET | ROCKETGATE GATEWAY ECOM |
| EQUIPMENT | EQUPCS3W | 3C Payment GTW ms |
| EQUIPMENT | EQUPCSFT | CECSoft |
| EQUIPMENT | EQUPDGW2 | Board GTW TA RC DW EC |
| EQUIPMENT | EQUPDMCN | TenderMerchConv4.2.12 |
| EQUIPMENT | EQUPECTR | Paytrace GTW EC |
| EQUIPMENT | EQUPFUJI | FUJI Cash Register |
| EQUIPMENT | EQUPGLDG | Edgil EdgCapture v4.014 |
| EQUIPMENT | EQUPJAVC | Dejavoo V-8 |
| EQUIPMENT | EQUPL4CS | AppliedMicros104 |
| EQUIPMENT | EQUPGRV5 | Payment Manager v6.5 |
| EQUIPMENT | EQUPGNI6 | VeriSign6000 |
| EQUIPMENT | EQUPHHUB | PTI-Tellan PC HUB 20 Pk HDC |
| EQUIPMENT | EQUPDC01 | ESD, INC |
| EQUIPMENT | EQUPDMDA | DHD MEDIA GATEWAY |
| EQUIPMENT | EQUPHAV2 | ALOHA SUITE V6.2 |
| EQUIPMENT | EQUPDXSE | INDEX GTWY EC SINGLE RC |
| EQUIPMENT | EQUPLETW | Mobile Comm RC GTW EC |
| EQUIPMENT | EQUPLFPR | Card Gateway V0.1 RC SRS |
| EQUIPMENT | EQUPLGWY | Global Collect Gateway |
| EQUIPMENT | EQUPLI01 | ECLIPSE SOFTWARE |
| EQUIPMENT | EQUPLI54 | RetailDLiveprocessor5.4.2 |
| EQUIPMENT | EQUPLINC | Govolution Inc Gateway |
| EQUIPMENT | EQUPLLST | Wells StoreFront PC |
| EQUIPMENT | EQUPLMEC | VisualMatrix V 4.2.0 EC |
| EQUIPMENT | EQUPLNAO | Wells NAO |
| EQUIPMENT | EQUPLP2K | LinkPoint 2000 |
| EQUIPMENT | EQUPLV25 | DELEGO V2.5.1 |
| EQUIPMENT | EQUPLYCP | Splyce Payment Pro v3.9 |
| EQUIPMENT | EQUPMAS1 | INTUIT QBMAS SFTW |
| EQUIPMENT | EQUPMATA | Instamed Ecomm SP |
| EQUIPMENT | EQUPMBRN | Rest SOL CPU MONITOR BRN |
| EQUIPMENT | EQUPMECO | TenderMerchConv3.3.8.1 |
| EQUIPMENT | EQUPMHTI | Network Mrcht GTW ISO  |
| EQUIPMENT | EQUPMICN | MicroNode 960 as Petro |
| EQUIPMENT | EQUPMPMU | FD Mobile Pay Multi-User |
| EQUIPMENT | EQUPMRC4 | SPOS32_3.1-T4220,T4230,M4230,M4240,T4100 |
| EQUIPMENT | EQUPMSSG | MSS Global |
| EQUIPMENT | EQUPOMGC | VERIF-OMNI 3750 DC GC |
| EQUIPMENT | EQUPLNET | NelnetQuikPay GWY RC DW |
| EQUIPMENT | EQUPLSLS | CSOKI Gateway v.1 RC |
| EQUIPMENT | EQUPLTPS | Salon UltimateV12 DW WEB |
| EQUIPMENT | EQUPMC01 | IBM CORPORATION |
| EQUIPMENT | EQUPMCV3 | Tdr Ret Mer Con v3.3.1 |
| EQUIPMENT | EQUPMIEN | Micro Enginetics |
| EQUIPMENT | EQUPMILT | Hamilton |
| EQUIPMENT | EQUPMMKK | PTI-Tellan PC HUB 20Pk TDC |
| EQUIPMENT | EQUPMNN8 | Innovations - G3 BAM COV/EOL |
| EQUIPMENT | EQUPMPAY | FreedomPay Gateway |
| EQUIPMENT | EQUPMRC2 | Trustcommerce |
| EQUIPMENT | EQUPMRCT | Switch Commerce GTWY |
| EQUIPMENT | EQUPMRKP | Cinemark/Penny |
| EQUIPMENT | EQUPMRW8 | Cardinal Comm RC GTW EC |
| EQUIPMENT | EQUPMV50 | Touchnet Comm Mgt v5.0 |
| EQUIPMENT | EQUPMVES | Element Pmnt Svc GTWY EC |
| EQUIPMENT | EQUPNDTC | Lindt Chocolate |
| EQUIPMENT | EQUPNGZW | MICRODYNONLINE GTWY ECOM |
| EQUIPMENT | EQUPNISC | NISC gateway |
| EQUIPMENT | EQUPNIW9 | FTNI ETRAN GTWY  |
| EQUIPMENT | EQUPNPRC | CENPOS GTWY DW RC |
| EQUIPMENT | EQUPNT01 | POINT INTERNATIONAL INC |
| EQUIPMENT | EQUPNX01 | LYNXTOUCH SOLUTIONS CORP |
| EQUIPMENT | EQUPNXAZ | MAGTEK MAGENSA GTWY |
| EQUIPMENT | EQUPODSO | FoodTEC Solutions |
| EQUIPMENT | EQUPOFDL | State of Delaware |
| EQUIPMENT | EQUPOGOM | YAHOO GATEWAY ECOM |
| EQUIPMENT | EQUPOMV5 | ACI Retail Com v5.0 EC |
| EQUIPMENT | EQUPOSEC | PROSOL TSEND9.4.6 DWRCEC |
| EQUIPMENT | EQUPP104 | PAYwarePCv1.0.4 |
| EQUIPMENT | EQUPP112 | PAYwarePCv1.1.2 |
| EQUIPMENT | EQUPP900 | Verifone P900 Printer |
| EQUIPMENT | EQUPPL21 | STAR PLUS V7.21 |
| EQUIPMENT | EQUPPL81 | Star-Plusv8.1 |
| EQUIPMENT | EQUPPL86 | RetailProEFTLinkv8.6 |
| EQUIPMENT | EQUPPTS1 | Enterprise software |
| EQUIPMENT | EQUPMNTS | United Pymt Serv Gateway |
| EQUIPMENT | EQUPMODE | Wnet Card Modules  v2.0 |
| EQUIPMENT | EQUPMST1 | Comstar Gateway v 2.0 |
| EQUIPMENT | EQUPN8I1 | EMN8, Inc |
| EQUIPMENT | EQUPNDRO | SYNDERO - ECOMM |
| EQUIPMENT | EQUPNECM | Panera 5.00 k.3. EC. |
| EQUIPMENT | EQUPNEEC | Aone Pos v1.0 RC EC |
| EQUIPMENT | EQUPNHAM | Honey Baked Ham |
| EQUIPMENT | EQUPNISO | MRCH PRTNRS NASH ISO GWY |
| EQUIPMENT | EQUPNMPK | TranscoreMassDOT4.2RCEC |
| EQUIPMENT | EQUPNPFP | Verisign PayFlow Pro VAp |
| EQUIPMENT | EQUPNSMT | Brandsmart Millennium |
| EQUIPMENT | EQUPNSV2 | Precidia Vx810 PP XPI 4.27D |
| EQUIPMENT | EQUPNTDC | PTI-Nurit 2060 TDC |
| EQUIPMENT | EQUPNTSY | SynTech FuelMast 2.1.3.1 |
| EQUIPMENT | EQUPNU01 | MENUSOFT SYSTEMS CORP |
| EQUIPMENT | EQUPNVAP | Verisign SurePay VrtlApp |
| EQUIPMENT | EQUPNWAR | Dinerware2.9 Single Settle |
| EQUIPMENT | EQUPNXPS | TNS TransXpress.Net (g/w) |
| EQUIPMENT | EQUPNXSP | Equinox SPOS32 3.3.179 |
| EQUIPMENT | EQUPO470 | Omni 470 Terminal |
| EQUIPMENT | EQUPOECA | ECA LinkPoint AIO |
| EQUIPMENT | EQUPOG01 | PROGRESSIVE SOFTWARE |
| EQUIPMENT | EQUPOGAW | NCO Group Gateway |
| EQUIPMENT | EQUPOMLK | Micros without Merch Link |
| EQUIPMENT | EQUPONEG | Ogone Gateway |
| EQUIPMENT | EQUPOSYS | ONOSYS GTWY EC RC DW |
| EQUIPMENT | EQUPOV67 | Alohav6.7 |
| EQUIPMENT | EQUPOXP3 | MICROS XSTORE7.0 DW RC |
| EQUIPMENT | EQUPP107 | PAYwarePCv1.0.7 |
| EQUIPMENT | EQUPPC20 | CFG PC2000 |
| EQUIPMENT | EQUPPCPS | C/O PC + |
| EQUIPMENT | EQUPPCRT | PCRT PC Retail |
| EQUIPMENT | EQUPPFE1 | CARD NOT PRESENT FE |
| EQUIPMENT | EQUPPFPB | MS POS Full Prod Bundle |
| EQUIPMENT | EQUPPIOC | Accept IO RC |
| EQUIPMENT | EQUPPL01 | CYPLEX |
| EQUIPMENT | EQUPPO73 | IslandPacificOnePoint7.3 |
| EQUIPMENT | EQUPPO74 | FocusPOAv7.4 |
| EQUIPMENT | EQUPPORS | BAMS TSYS equiptype - PP3010  |
| EQUIPMENT | EQUPPRPS | Torchmark Prop Software |
| EQUIPMENT | EQUPPSFE | JCP Proprietary Software- Ecommerce |
| EQUIPMENT | EQUPPV12 | PC America POS Ste v12 |
| EQUIPMENT | EQUPPVS3 | TEMPUS GATEWAY Nash Ecom |
| EQUIPMENT | EQUPPWR2 | ORCC PAYWRE GATEWAY ECOM |
| EQUIPMENT | EQUPQBP1 | QBPOS Software Package |
| EQUIPMENT | EQUPREBT | NCREpsilonATL105v2013EBT |
| EQUIPMENT | EQUPRFUE | Verifunds  DW RC EC GTWY |
| EQUIPMENT | EQUPRICA | PCAmerica Nash |
| EQUIPMENT | EQUPRICG | PAYMETRIC GATEWAY |
| EQUIPMENT | EQUPRIPE | Epicor RC |
| EQUIPMENT | EQUPRITA | Rita |
| EQUIPMENT | EQUPRLIV | Gardens Alive |
| EQUIPMENT | EQUPRNSH | XCR POS v1.0 RC Nashville |
| EQUIPMENT | EQUPRNT2 | eProcessing Network (Retail and Mo/To)  |
| EQUIPMENT | EQUPRREP | NCREPS105V2.0.1131-2031  |
| EQUIPMENT | EQUPRT01 | PERFORMANCE TELECOM, INC |
| EQUIPMENT | EQUPRT8M | NURIT 8000 TERMINAL |
| EQUIPMENT | EQUPRTL4 | TendRetail MerchCon v4.2 |
| EQUIPMENT | EQUPRTRC | PayRight Tran ServRCDW |
| EQUIPMENT | EQUPRV70 | NCR Adv Rest v7.05.02 |
| EQUIPMENT | EQUPRZ01 | KARZ SYSTEMS |
| EQUIPMENT | EQUPSA01 | NUSABLE |
| EQUIPMENT | EQUPSCOE | Discover eStores |
| EQUIPMENT | EQUPSCOP | GENESCO - ISO BUYPASS |
| EQUIPMENT | EQUPSEDC | ICSTreatware4.9 |
| EQUIPMENT | EQUPSG01 | CIBER CUSTOM SOLUTIONS |
| EQUIPMENT | EQUPSIV8 | KISMicrosalev8.0.853 |
| EQUIPMENT | EQUPSNSV | Trans Net Serv Gateway |
| EQUIPMENT | EQUPSPAE | YESPAY EASY VT GTWY EC |
| EQUIPMENT | EQUPSPV1 | MBS POS v1 |
| EQUIPMENT | EQUPSPZ3 | Class B PAX SP30  |
| EQUIPMENT | EQUPSSOL | FTS Solutions HDC EBT V2.01 |
| EQUIPMENT | EQUPSSYS | Travstar/NEDOS10.00.01 |
| EQUIPMENT | EQUPSTEX | Mainstreet RC monetra EC |
| EQUIPMENT | EQUPSTIR | SOUND TRANSIT |
| EQUIPMENT | EQUPSTMD | Instamed SP |
| EQUIPMENT | EQUPSTWA | PC Authorize Win Software |
| EQUIPMENT | EQUPSV20 | SICOM SLSeries v2.0 |
| EQUIPMENT | EQUPT1ET | Hypercom T7P Thermal |
| EQUIPMENT | EQUPTCOT | PetcoTransArmor Software |
| EQUIPMENT | EQUPTFIT | NATIONAL FITNESS |
| EQUIPMENT | EQUPTLTW | Dgtl Rvr WrldPymt GTW |
| EQUIPMENT | EQUPTME1 | Network Merchant |
| EQUIPMENT | EQUPTPOS | Netpos RC |
| EQUIPMENT | EQUPTR7A | MainstreetMonetra7 |
| EQUIPMENT | EQUPTST6 | PROTOBASE SUITE 6.0 |
| EQUIPMENT | EQUPTSUN | Xerox atlas app sunrail |
| EQUIPMENT | EQUPUC01 | IN TOUCH CORP |
| EQUIPMENT | EQUPUPEC | BLUEPAY ISO8583 GTWY EC |
| EQUIPMENT | EQUPUTSP | Argus PYMT GTW |
| EQUIPMENT | EQUPV3CP | Ver 3.10 ICV ValCode-Chng Mer# or Proce |
| EQUIPMENT | EQUPVA03 | PaymentNet Hospitality-VNI002 |
| EQUIPMENT | EQUPVA23 | Xstore v 3.00.00.18-VDV005 |
| EQUIPMENT | EQUPVA24 | Square One v 5.03.08-VCO001 |
| EQUIPMENT | EQUPVA45 | ICVerify v 1.5.3 SP13-VIV006 |
| EQUIPMENT | EQUPVA58 | Galaxy v 1.8.17.26-VGT001 |
| EQUIPMENT | EQUPVA61 | Monetra v 6.1-VMS003 |
| EQUIPMENT | EQUPVA63 | Credit Line-VHS001 |
| EQUIPMENT | EQUPVA70 | InFusion v 3.50/PCCharge v 5.7.1 SP8C-VPA001 |
| EQUIPMENT | EQUPVA75 | ICE 5500 Plus & !SPOSIE v 08A -VHY010 |
| EQUIPMENT | EQUPVA77 | ICE 5500 Plus & SQSRIE v 02Q-VHY012 |
| EQUIPMENT | EQUPVA82 | NAC-1A-VHY017 |
| EQUIPMENT | EQUPVB38 | The Server v 2005-VPT001 |
| EQUIPMENT | EQUPVB91 | RiTA Server v 3.0-VVF004 |
| EQUIPMENT | EQUPVE32 | v3.00 ICV SETUP |
| EQUIPMENT | EQUPVF8C | VFI PCChrg 5.8.2 Nash EC |
| EQUIPMENT | EQUPVONT | Vivonet RC |
| EQUIPMENT | EQUPVT29 | Midax-VMX001 |
| EQUIPMENT | EQUPWTRT | PaywareTransactEDCv3.2.4 |
| EQUIPMENT | EQUPX300 | Zon XL 300 Terminal |
| EQUIPMENT | EQUPXCLB | AMEX Hyp T7 Plus/T4210 |
| EQUIPMENT | EQUPMTXE | ITRetalw/MTXEPSv8/2006 |
| EQUIPMENT | EQUPOSY1 | Hotel Software Systems (HSS) |
| EQUIPMENT | EQUPP105 | PAYwarePCv1.0.5 |
| EQUIPMENT | EQUPP111 | PAYwarePCv1.1.1 |
| EQUIPMENT | EQUPP137 | PC Charge v5.9.2 |
| EQUIPMENT | EQUPPAC2 | Synaro Payment Processor (E-comm) |
| EQUIPMENT | EQUPPCEN | Envoy PC--EDC |
| EQUIPMENT | EQUPPCO1 | SPOS32_4.1.38 T4220XML |
| EQUIPMENT | EQUPPCO3 | SPOS32_4.1.38 M4230XML |
| EQUIPMENT | EQUPPJ1K | Skipjack Gateway ECOM |
| EQUIPMENT | EQUPPPV4 | POSPartnerPOSePayv4 |
| EQUIPMENT | EQUPPV11 | PPP ChargeITPro v1.1 |
| EQUIPMENT | EQUPPXML | NETEPAY XML V4 |
| EQUIPMENT | EQUPPYMT | DIALECT PAYMENT GATEWAY |
| EQUIPMENT | EQUPQPTU | World Bcard RC GTW EC |
| EQUIPMENT | EQUPQURL | SquirrelSystems1.6/6.0 |
| EQUIPMENT | EQUPRC01 | MERCHANT-LINK, INC |
| EQUIPMENT | EQUPRCTV | GCIEC |
| EQUIPMENT | EQUPRDR1 | FD Vx520 - Dial and IP |
| EQUIPMENT | EQUPRLNK | DIRECT LINK (G/W) |
| EQUIPMENT | EQUPRLT8 | STAR LITE V8 |
| EQUIPMENT | EQUPRP01 | SONANT CORPORATION |
| EQUIPMENT | EQUPRSBL | Sable ECR |
| EQUIPMENT | EQUPRSRC | CYBERSOURCE GATEWAY |
| EQUIPMENT | EQUPRTEC | PayRightTranServRCECDW |
| EQUIPMENT | EQUPRZGT | AUTH.NET GATEWAY  |
| EQUIPMENT | EQUPSAEX | SASI Experience |
| EQUIPMENT | EQUPSAPI | GW WEBSVC API RTL/MOTO |
| EQUIPMENT | EQUPSCBR | Cybercash Internet Software |
| EQUIPMENT | EQUPSERV | Pure Payments Service Gateway |
| EQUIPMENT | EQUPSL01 | STS SYSTEMS LTD |
| EQUIPMENT | EQUPSLT6 | RMS Solution v6.2 |
| EQUIPMENT | EQUPSM1Y | PCCharge PRO |
| EQUIPMENT | EQUPSMPM | MAPP Miscellaneous PC Software-EDC |
| EQUIPMENT | EQUPSPMT | OMSPayments1.0 RC |
| EQUIPMENT | EQUPSPRK | PassportPark2 v3.0 EC RC |
| EQUIPMENT | EQUPSRCT | Mainstreet RC monetra |
| EQUIPMENT | EQUPSSEC | FTS Sln HDC EBT V2.01 EC |
| EQUIPMENT | EQUPST3Y | DIRECT INSITE GTWY |
| EQUIPMENT | EQUPSTPO | Store Point |
| EQUIPMENT | EQUPSTWR | ICSTreatware4.10 |
| EQUIPMENT | EQUPSV32 | LOC SMS v3.2 |
| EQUIPMENT | EQUPT212 | POSLyx220w/transnet2.12 |
| EQUIPMENT | EQUPT314 | PayWareTransactv3.1.4 |
| EQUIPMENT | EQUPT340 | Tranz 340 Terminal |
| EQUIPMENT | EQUPT7PL | Hypercom T7 Plus Terminal |
| EQUIPMENT | EQUPT7PM | Hypercom T7Plus 1 Meg Terminal |
| EQUIPMENT | EQUPTA01 | DATACAP SYSTEMS |
| EQUIPMENT | EQUPTATH | Talento Term ETC Type 4 |
| EQUIPMENT | EQUPTATK | C/O TALTEK 727 |
| EQUIPMENT | EQUPTC56 | TEC 5600 |
| EQUIPMENT | EQUPTCAP | Dcap NETePay 5.03 Bpass |
| EQUIPMENT | EQUPTCDM | FD400Ti CDMA |
| EQUIPMENT | EQUPTCHP | Exatouch PaymtEngine 2.0 |
| EQUIPMENT | EQUPTDC2 | PTI-Nurit 2090 TDC |
| EQUIPMENT | EQUPTGGC | Proprietary Rooms to Go |
| EQUIPMENT | EQUPTHEC | SWITCH COMRCE GTWY EC RC |
| EQUIPMENT | EQUPTIWF | FD200Ti Wi-Fi |
| EQUIPMENT | EQUPTL31 | Telrad Tip 31 |
| EQUIPMENT | EQUPTMIC | Ulta - Micros |
| EQUIPMENT | EQUPTMOT | Creative Mobile Technologies via Payment GTWY 3.0  |
| EQUIPMENT | EQUPTMRK | Avanti Markets |
| EQUIPMENT | EQUPTN01 | HOTEL INFORMATION SYS |
| EQUIPMENT | EQUPTRPT | STS - Sunrise EDC |
| EQUIPMENT | EQUPTSC1 | National Systems Corporation |
| EQUIPMENT | EQUPTTEC | PC-Charge thru T3 |
| EQUIPMENT | EQUPTUIT | Wells Fargo Intuit |
| EQUIPMENT | EQUPTV21 | POSLynx 220 wTRANS v2.12 |
| EQUIPMENT | EQUPTV2L | Precida POSLynx 220 w/Transnet |
| EQUIPMENT | EQUPTWTF | TFPay RC GTW |
| EQUIPMENT | EQUPTZQY | VFI RC Pay Conn GTW EC |
| EQUIPMENT | EQUPUAPA | AquaPay (g/w) GlobalAdmin |
| EQUIPMENT | EQUPUM01 | ATOMIC SOFTWARE |
| EQUIPMENT | EQUPUR01 | HEURISTIC COMPUTER |
| EQUIPMENT | EQUPUSNP | Bluesnap |
| EQUIPMENT | EQUPUSPC | BLUESNAPGATEWAY |
| EQUIPMENT | EQUPV301 | VFIRiTAv3.0.1 |
| EQUIPMENT | EQUPV3MU | Ver 3.10 ICVERIFY Windows Multi User Up |
| EQUIPMENT | EQUPV770 | Storenxt ISS45 v7.7.0.52 |
| EQUIPMENT | EQUPVA02 | CreditLine v 2.22-VNI001 |
| EQUIPMENT | EQUPVA06 | Adonix X3 v. 136-VAD001 |
| EQUIPMENT | EQUPVA10 | PS2DENV v 11D -VAM003 |
| EQUIPMENT | EQUPVA11 | Purchase Expert(Earlier PymntLink/ExpPymnt)-VAM004 |
| EQUIPMENT | EQUPVA14 | ARG 9600 Batch-VAR001 |
| EQUIPMENT | EQUPVA22 | Store21 v 4.70-VDV004 |
| EQUIPMENT | EQUPVA25 | Retail Saas v 1.3-VDG001 |
| EQUIPMENT | EQUPVA26 | EdgCapture 4.0-VED002 |
| EQUIPMENT | EQUPVA59 | Ingepay v 3.00 with i5100-VIG004 |
| EQUIPMENT | EQUPVA64 | Monetra v 6.3-VMS004 |
| EQUIPMENT | EQUPVA67 | TAXFDNBD2A-VHY002 |
| EQUIPMENT | EQUPVA71 | InFusion v 3.50/Monetra v 6.2.2-VPA002 |
| EQUIPMENT | EQUPVA73 | XiPay v 3.0-VPM002 |
| EQUIPMENT | EQUPVA76 | T7Plus & !SPOS07E v 08A-VHY011 |
| EQUIPMENT | EQUPVA86 | Enterprise Edition for Windows v 1.5 -VIV002 |
| EQUIPMENT | EQUPVA88 | Visual Matrix v 1.4.4-VIT001 |
| EQUIPMENT | EQUPVA91 | Ingepay U32 v 1.07 -VIG001 |
| EQUIPMENT | EQUPVA92 | CMS2 v 2.00.00-VPD002 |
| EQUIPMENT | EQUPVB01 | KARZ v 11.2    -VKS001 |
| EQUIPMENT | EQUPVB06 | CellTrek Explorer-VLM003 |
| EQUIPMENT | EQUPVB12 | MBS 4680,4690-VMB001 |
| EQUIPMENT | EQUPVB45 | POS*Liberty v 7.70-VRT001 |
| EQUIPMENT | EQUPVB52 | RMS Touch v 2.07-VRM001 |
| EQUIPMENT | EQUPVB53 | Trovato v 4.12 -VSP001 |
| EQUIPMENT | EQUPVB64 | CounterPro ePay v 10.1.4-VSL001 |
| EQUIPMENT | EQUPVB67 | Squirrel POS v 1.41.04382-VSQ001 |
| EQUIPMENT | EQUPVB73 | Prime Trex v 1.1.0 -VTT001 |
| EQUIPMENT | EQUPVB79 | TotaLink v 2.0 -VTC001 |
| EQUIPMENT | EQUPVB81 | Payment Server v 2.x-VTP001 |
| EQUIPMENT | EQUPVB86 | USALive v 3.1-VUS001 |
| EQUIPMENT | EQUPVBSE | Servebase Ecomm RC |
| EQUIPMENT | EQUPVDIN | NovaDine 2.5 v5393  |
| EQUIPMENT | EQUPVE30 | v3.00 ICV VERIF ADD USER |
| EQUIPMENT | EQUPVE39 | v3.00 ICV CONV SU-MU WO |
| EQUIPMENT | EQUPVE40 | Ver 4.00 ICVERIFY Windows New Single User |
| EQUIPMENT | EQUPVER1 | v2.46 ICV Win New M-User |
| EQUIPMENT | EQUPVER3 | v2.46 ICV Win S-User Up |
| EQUIPMENT | EQUPVER6 | v2.46 ICV S-M-User Up |
| EQUIPMENT | EQUPVISI | NaviSite ProApps Gateway |
| EQUIPMENT | EQUPVNPB | Elavon Protobase v6.01 |
| EQUIPMENT | EQUPVOPR | 4500M-4500 WITH MAGSTRIPE |
| EQUIPMENT | EQUPVSTR | Travstar v9.0 |
| EQUIPMENT | EQUPVT04 | Compris v 6.01.01.48-VCT001 |
| EQUIPMENT | EQUPVT05 | ChargeAnywhere v 1.0.0.1-VCN001 |
| EQUIPMENT | EQUPVT08 | Wayne Nucleus AFP v 2.10F-VDW002 |
| EQUIPMENT | EQUPVT26 | MicroEnginetics v 2.0-VMP001 |
| EQUIPMENT | EQUPVT31 | FuelForce FF814 v 1.00-VML001 |
| EQUIPMENT | EQUPVT34 | ACS v 5.0.0.26-VNC003 |
| EQUIPMENT | EQUPVT40 | RSG Latitude v 2-VRG001 |
| EQUIPMENT | EQUPVT41 | Storeline v 8-VRX001 |
| EQUIPMENT | EQUPVT46 | InfoPilot using Trans Eng.v7.2 with NCR Sca-VSJ001 |
| EQUIPMENT | EQUPVT54 | Triversity TransactionWire v 5.2.4.18-VTV001 |
| EQUIPMENT | EQUPWECO | IATS Gateway Ecom |
| EQUIPMENT | EQUPWES1 | NEWEDGE Services Inc |
| EQUIPMENT | EQUPWFPT | FD-100 WIFI POS TERMINAL |
| EQUIPMENT | EQUPWRXS | T8315 CPU/MONITOR WORKSTATION-Retail |
| EQUIPMENT | EQUPWXRS | mPayMe DW RC EC GTWY |
| EQUIPMENT | EQUPXSTO | DATAVANTAGE XSTORE |
| EQUIPMENT | EQUPYPC4 | SPOS32_3.1-T4220,T4230,M4230,M4240,T4100 YPC4 |
| EQUIPMENT | EQUPYWRL | WorldSpy (g/w) |
| EQUIPMENT | EQUPZONJ | Verifone Zon Jr + Terminal |
| EQUIPMENT | EQUPNTXP | MidEXslipstream4.0Nash |
| EQUIPMENT | EQUPSPOR | CIT-POSPORT |
| EQUIPMENT | EQUPT077 | Hypercom T77 Thermal |
| EQUIPMENT | EQUPT38X | Tranz 380X2 Terminal |
| EQUIPMENT | EQUPTVFI | Xpient VFI TPEBPASS v4.6  |
| EQUIPMENT | EQUPUNOX | Equinox SPOS32_3.3.99 |
| EQUIPMENT | EQUPV112 | Radiant Epsilon v1129 |
| EQUIPMENT | EQUPV11C | Radnt Epsilon v1129 CORE |
| EQUIPMENT | EQUPVA42 | ICVerify 4.0.3. SP1-VIV005 |
| EQUIPMENT | EQUPVA46 | ICVerify v 1.5.3 SP1-VIV007 |
| EQUIPMENT | EQUPVB02 | SmartPay-VKI001 |
| EQUIPMENT | EQUPVB65 | Protobase 4.83-VSD001 |
| EQUIPMENT | EQUPVB94 | Business Navigator - Retail Edition-VVE001 |
| EQUIPMENT | EQUPVC02 | PDQ version 5.0-VPD003 |
| EQUIPMENT | EQUPVE35 | v3.00 ICV WIN MUL UPGD |
| EQUIPMENT | EQUPVE36 | v3.00 ICV VALCODE CHNG |
| EQUIPMENT | EQUPVJV9 | Dejavoo V-9 |
| EQUIPMENT | EQUPVREA | VIVOPAY DTC |
| EQUIPMENT | EQUPVT21 | IT Retail 2005-VIR002 |
| EQUIPMENT | EQUPXEPS | Retalix/MTX SRVREPS GTWY |
| EQUIPMENT | EQUPYGTW | Paythru Gateway |
| EQUIPMENT | EQUPYMIL | Keystone Millenium App |
| EQUIPMENT | EQUPYNEC | USAEPAY NASH ISO GTWY EC |
| EQUIPMENT | EQUPYSY1 | Way Systems |
| EQUIPMENT | EQUPZREX | SMART BIZTECH DIREX GTWY |
| EQUIPMENT | EQUPT77G | HYPERCOM T77G-F |
| EQUIPMENT | EQUPMPAN | Campana Axis0.1 RC DW |
| EQUIPMENT | EQUPNPEC | CENPOS GTWY EC DW RC |
| EQUIPMENT | EQUPPAIO | LinkPoint AIO |
| EQUIPMENT | EQUPPART | COPART |
| EQUIPMENT | EQUPPCA1 | MSPCA |
| EQUIPMENT | EQUPPOS2 | onePOSv4.0 |
| EQUIPMENT | EQUPPPA5 | DATACAP NETePay NSH/N |
| EQUIPMENT | EQUPPTA1 | SEPTA |
| EQUIPMENT | EQUPPV33 | Paymetric XiPay v3.3 |
| EQUIPMENT | EQUPRMIC | Micros HMS |
| EQUIPMENT | EQUPRTDG | SECURE TRADING GTWY |
| EQUIPMENT | EQUPS453 | XpientTPEBPASS4.5.3 |
| EQUIPMENT | EQUPSGRC | eGenuity v6 single RC |
| EQUIPMENT | EQUPSXT9 | Class B PAX S90  |
| EQUIPMENT | EQUPTRGP | Target- RGP |
| EQUIPMENT | EQUPVB30 | onePOS.com Payment Processing v 1.50-VOP001 |
| EQUIPMENT | EQUPVC05 | Payment Server v 2.x-VTP001 |
| EQUIPMENT | EQUPVER0 | v2.46 ICV Valcode-Add MID |
| EQUIPMENT | EQUPPGRD | Pro Unlimited User Upgrd |
| EQUIPMENT | EQUPPWNC | EZ Pawn Corp |
| EQUIPMENT | EQUPRBAS | Servebase GTWY RC |
| EQUIPMENT | EQUPSEA1 | BOSE ECOM |
| EQUIPMENT | EQUPSIGC | Mx830 Sig Capture |
| EQUIPMENT | EQUPSTD2 | VersiTouch10.10.22 Dial |
| EQUIPMENT | EQUPSTN2 | MainStreet NashEDCv2013 |
| EQUIPMENT | EQUPSUNT | Suntronics SM 3000 |
| EQUIPMENT | EQUPTJTJ | jtyjtyjty |
| EQUIPMENT | EQUPTON1 | PRINCETON ECOMM GATEWAY |
| EQUIPMENT | EQUPTRBP | Dcap TwTran 3.0 Bpass |
| EQUIPMENT | EQUPTREE | PEACHTREE/VERUS GATEWAY  |
| EQUIPMENT | EQUPUI01 | SQUIRRIL SYSTEMS |
| EQUIPMENT | EQUPUT01 | SOTHERN DATACOMM |
| EQUIPMENT | EQUPV141 | Squirrel v1.41 |
| EQUIPMENT | EQUPV145 | Squirrel v1.45 |
| EQUIPMENT | EQUPV3ST | Ver 3.10 ICVERIFY Windows Setup |
| EQUIPMENT | EQUPV582 | PCChargev5.8.2 |
| EQUIPMENT | EQUPV590 | PC Charge v5.9.0 |
| EQUIPMENT | EQUPVA39 | Tradewind v 8.9 -VDV003 |
| EQUIPMENT | EQUPVA51 | ICVerify v 4.0.3 SP2-VIV008 |
| EQUIPMENT | EQUPVA74 | TSAMX7A v 01P for T7Plus-VHY009 |
| EQUIPMENT | EQUPVAM4 | ICV4.4 Add MID |
| EQUIPMENT | EQUPVC22 | TREVANCE V2.2 |
| EQUIPMENT | EQUPVCSW | Invenstar TouchSuite GTW |
| EQUIPMENT | EQUPVE37 | v3.00 ICV UPGD DOS/WIN S |
| EQUIPMENT | EQUPVMU4 | ICV4.4 Multi User |
| EQUIPMENT | EQUPVSU4 | ICV4.4 Single User |
| EQUIPMENT | EQUPVT19 | ICS v 5.0-VIE002 |
| EQUIPMENT | EQUPVT24 | Menusoft Digital Dining v 7.2.900-VMN001 |
| EQUIPMENT | EQUPVT43 | VIPOS with Ingenico eN Concert Store-VRO001 |
| EQUIPMENT | EQUPWP12 | VX510 Dual Comm 12 Meg |
| EQUIPMENT | EQUPWREM | Charganywhre Gatewy ECOM |
| EQUIPMENT | EQUPWXES | FD-55 Dial and IP |
| EQUIPMENT | EQUPXTEC | PAX Tech BroadPOS v1.0 |
| EQUIPMENT | EQUPXYTK | TZ380 64K - G3 BAM COV/EOL |
| EQUIPMENT | EQUPYDQ2 | PAYDQ GATEWAY |
| EQUIPMENT | EQUPYGAT | PayMover Gateway |
| EQUIPMENT | EQUPYST5 | Duffy's DBS T+ 7.5.1 |
| EQUIPMENT | EQUPYSYS | Way Systems Cell Phone Printer |
| EQUIPMENT | EQUPyram | 12345 |
| EQUIPMENT | EQUPSOLG | IP Merchant Sol Gateway |
| EQUIPMENT | EQUPV3UU | Ver 3.10 ICVERIFY Upg, DOS to Win MU |
| EQUIPMENT | EQUPVA12 | ChargeLogic v 3.0-VAV001 |
| EQUIPMENT | EQUPVB44 | Counterpoint v 7.5-VSY001 |
| EQUIPMENT | EQUPVT56 | PCCharge 5.7 x-VVF001 |
| EQUIPMENT | EQUPVT58 | Ruby v 4.04-VVF003 |
| EQUIPMENT | EQUPX001 | MICRONEX, INC |
| EQUIPMENT | EQUPX870 | MX870 Pin Pad |
| EQUIPMENT | EQUPYPT4 | SPOS32_3.1- T4210, T4205 (Dial Only)YPT4 |
| EQUIPMENT | EQUPTQMG | ALLIED WALLET GTWY |
| EQUIPMENT | EQUPUPRC | TeeItUp RC |
| EQUIPMENT | EQUPV504 | Vrfne BUYPACK v5.04 |
| EQUIPMENT | EQUPVB40 | Payware ERP v 4.3 -VPP001 |
| EQUIPMENT | EQUPTREK | Hypercom Cellular Terminal |
| EQUIPMENT | EQUPVT02 | Autogas AFP v 4.6-VAA001 |
| EQUIPMENT | EQUPWLZN | PITNEY BOWES/ LMS |
| EQUIPMENT | EQUP00TE | C100 TERMINAL |
| EQUIPMENT | EQUP100J | BassPro ACI TA |
| EQUIPMENT | EQUP100U | Micros X-Store (RL) |
| EQUIPMENT | EQUP100Z | USAePAYValuelink RC v1.0 |
| EQUIPMENT | EQUP1011 | AAA Carolinas EC-RC |
| EQUIPMENT | EQUP101A | Cavenders Micros-Retail |
| EQUIPMENT | EQUP101J | AndrZaksRetailv2RCDW |
| EQUIPMENT | EQUP101L | AOS RC DW EC |
| EQUIPMENT | EQUP101Y | ICG SFTWRv4.0 DW RC |
| EQUIPMENT | EQUP101Z | ICG SFTWRv4.0 MS DW RC |
| EQUIPMENT | EQUP1022 | Samsonite Micros Xpay |
| EQUIPMENT | EQUP1025 | POSBank Single RC |
| EQUIPMENT | EQUP102C | Academy Sports |
| EQUIPMENT | EQUP102G | ACI ISD Java Switch |
| EQUIPMENT | EQUP102P | PaxTech BroadPOS RC Mult |
| EQUIPMENT | EQUP1034 | Instamed Direct Internet |
| EQUIPMENT | EQUP1039 | FDC_FIN EC GTWY RC DW |
| EQUIPMENT | EQUP103J | Coach v1.0 EC RC |
| EQUIPMENT | EQUP103Q | XpientCCA TPENASH 4.6sin |
| EQUIPMENT | EQUP105V | Penske RentalNet |
| EQUIPMENT | EQUP106J | POSLynx220TraNet2.14DW |
| EQUIPMENT | EQUP106Y | TGATE GW EC |
| EQUIPMENT | EQUP1014 | TenderMercConMul4.2.12EC |
| EQUIPMENT | EQUP101K | AOS RC DW |
| EQUIPMENT | EQUP102B | EPS GTWY RC DW |
| EQUIPMENT | EQUP102U | TriPayments ECOMM RC |
| EQUIPMENT | EQUP1031 | FTD CCAS RC |
| EQUIPMENT | EQUP103V | Alacriti v5.0 RC EC |
| EQUIPMENT | EQUP1046 | Port Of Portlnd PWT 3.24 |
| EQUIPMENT | EQUP104C | EPICOR ESDM 241SP1RCDW |
| EQUIPMENT | EQUP104D | TempusGTWsingle |
| EQUIPMENT | EQUP104Z | Costa Cruise RC MO V.1.0 |
| EQUIPMENT | EQUP105D | Groowin eComm DW RC |
| EQUIPMENT | EQUP105K | Clover Mini 3G & Wi-Fi |
| EQUIPMENT | EQUP105P | Paperless Tran Corp GTW |
| EQUIPMENT | EQUP105W | TSDWeb GTW EC DW |
| EQUIPMENT | EQUP106H | Eigen Miraserv GTW |
| EQUIPMENT | EQUP106K | IT Retail V7 DW |
| EQUIPMENT | EQUP106L | COMPUTER INFO SYS RC DW |
| EQUIPMENT | EQUP106P | TGATE GTWY ECOM |
| EQUIPMENT | EQUP106S | Point SCA Verifone RC |
| EQUIPMENT | EQUP1081 | VESTA GTWY VPN RC |
| EQUIPMENT | EQUP108G | Nash1Mar10 |
| EQUIPMENT | EQUP108H | BF PayConex GTW RC |
| EQUIPMENT | EQUP1090 | CardConnect RC v5.2 MO |
| EQUIPMENT | EQUP109L | Card1Mar12 |
| EQUIPMENT | EQUP109O | Buy1Mar12 |
| EQUIPMENT | EQUP109W | Nash5Mar13 |
| EQUIPMENT | EQUP10C0 | Nash2Mar17 |
| EQUIPMENT | EQUP10DH | CompassMar19 |
| EQUIPMENT | EQUP10E8 | Nash4Mar20 |
| EQUIPMENT | EQUP10EY | FD40 X12 |
| EQUIPMENT | EQUP10FH | CompassMar24 |
| EQUIPMENT | EQUP112Q | VENTEK TRANSIT DW RC |
| EQUIPMENT | EQUP103E | VFI PAYwareConnect RC EC |
| EQUIPMENT | EQUP103H | Silverleaf RC DW |
| EQUIPMENT | EQUP103I | Coach v1.0 RC |
| EQUIPMENT | EQUP103K | Paradigm ISO GTW DW |
| EQUIPMENT | EQUP103X | Citizen Watch KWI |
| EQUIPMENT | EQUP1048 | McCoys Building POS |
| EQUIPMENT | EQUP104K | 3C Pmt GTW ss |
| EQUIPMENT | EQUP104Q | CreditCall LTD GTW RC |
| EQUIPMENT | EQUP104R | DB. South Migration |
| EQUIPMENT | EQUP104T | RM3 South Migration |
| EQUIPMENT | EQUP1050 | Parkmobile GTW DW |
| EQUIPMENT | EQUP1055 | ABC Financial Data Trak |
| EQUIPMENT | EQUP106C | Coach AJB RTS V4.1 Fipay |
| EQUIPMENT | EQUP106E | CryptPay RC EC DW  |
| EQUIPMENT | EQUP106M | AJB FIPAY RTS v4.1 |
| EQUIPMENT | EQUP106R | FreedomPay GTW EC multi |
| EQUIPMENT | EQUP106X | MSTS RC BUYPASS UMF |
| EQUIPMENT | EQUP1071 | NCR EPSilon v2.3.003 |
| EQUIPMENT | EQUP1076 | 2CPUSA 2C Processor USA, LLC |
| EQUIPMENT | EQUP107J | MTDATA-RETAIL DWRC |
| EQUIPMENT | EQUP107O | MTDATA EC DW RC |
| EQUIPMENT | EQUP107R | Cayan v1 RC MO |
| EQUIPMENT | EQUP107V | ACI Postilion GW Lodg |
| EQUIPMENT | EQUP1085 | NCR MO RC v3.10 |
| EQUIPMENT | EQUP1087 | CAYAN GTWY EC RC SRS |
| EQUIPMENT | EQUP108J | Nash2Mar10 |
| EQUIPMENT | EQUP108U | NCRAlohaEDCV14.2 |
| EQUIPMENT | EQUP1091 | JITB Hawaii |
| EQUIPMENT | EQUP1097 | Tillster v1.0 RC |
| EQUIPMENT | EQUP109D | PHOENIXMN GTW EC DW RC |
| EQUIPMENT | EQUP109I | SemnoxParafait V2.0.0 RC |
| EQUIPMENT | EQUP10AE | deepcardnet13thmar |
| EQUIPMENT | EQUP10AX | Nash2Mar14 |
| EQUIPMENT | EQUP10AZ | Nash4Mar14 |
| EQUIPMENT | EQUP10C7 | Buypass1Mar17 |
| EQUIPMENT | EQUP10C8 | CompassMar17 |
| EQUIPMENT | EQUP10DA | NashMar19 |
| EQUIPMENT | EQUP10DC | Nash3Mar19 |
| EQUIPMENT | EQUP10E4 | BuypassMar20 |
| EQUIPMENT | EQUP10E5 | AllMar20 |
| EQUIPMENT | EQUP10EF | Nash1Mar21 |
| EQUIPMENT | EQUP10FE | Nash5Mar24 |
| EQUIPMENT | EQUP10IH | Nash3Apr21 |
| EQUIPMENT | EQUP10IM | Nash05Apr21 |
| EQUIPMENT | EQUP10IU | AllApr21 |
| EQUIPMENT | EQUP10J2 | BuypassApr22 |
| EQUIPMENT | EQUP10K1 | fd60 |
| EQUIPMENT | EQUP10TZ | Wildfly_Var |
| EQUIPMENT | EQUP10YS | OMNI 3730 |
| EQUIPMENT | EQUP10YT | KeyCorp K23 PCI 1 |
| EQUIPMENT | EQUP10Z5 | Internet Gateway Connections |
| EQUIPMENT | EQUP1106 | hi_23 |
| EQUIPMENT | EQUP110J | INDEX SYS GTW EC DW RC |
| EQUIPMENT | EQUP110Q | La Fitness |
| EQUIPMENT | EQUP110U | Point SCA Verifone RC MS |
| EQUIPMENT | EQUP1110 | SecureOne v0.1 EC RC |
| EQUIPMENT | EQUP111J | Magensa MMPG v1 RC |
| EQUIPMENT | EQUP111V | PayPoint GTW DW RC |
| EQUIPMENT | EQUP111Y | CC Payments VDS |
| EQUIPMENT | EQUP112G | PYMNT EX GTWY DW RC |
| EQUIPMENT | EQUP112L | Canadian e335 IntPinPad |
| EQUIPMENT | EQUP112O | nSoftware v6 RC DW |
| EQUIPMENT | EQUP112P | nSoftware v6 RC DW EC |
| EQUIPMENT | EQUP112S | HIGHRADIUS GTWY EC DW RC |
| EQUIPMENT | EQUP1132 | NPCI ACI RCS 5.0 REST TA |
| EQUIPMENT | EQUP113B | CSG SYSTEMS ECOM RC DW |
| EQUIPMENT | EQUP113K | ACI RCS 5.1 RC EC SS |
| EQUIPMENT | EQUP113M | DATALINE GTWY EC RC DW |
| EQUIPMENT | EQUP114K | MyCheck GW RC DW EC MS |
| EQUIPMENT | EQUP114L | TPE 2.xx RC GTW EC |
| EQUIPMENT | EQUP114Q | NCR CP GW RC EC SS |
| EQUIPMENT | EQUP115B | PayLeap DW SRS RC |
| EQUIPMENT | EQUP115G | VSECURE DW EC SRS RC |
| EQUIPMENT | EQUP115W | COMPRISE T GTW DW RC |
| EQUIPMENT | EQUP1160 | Pizza Hut Verifone RC |
| EQUIPMENT | EQUP1164 | DTCP NETePay 5.1 RC DW |
| EQUIPMENT | EQUP116B | Payfirma GTW RC DW |
| EQUIPMENT | EQUP116D | Thermeon Cars FDC GTW |
| EQUIPMENT | EQUP116F | PhoenixMgNetwk GTW DW |
| EQUIPMENT | EQUP116S | Mood Media EC |
| EQUIPMENT | EQUP116U | CRDCallCdEase GTW SMS EC |
| EQUIPMENT | EQUP117V | VDS DW RC SRS |
| EQUIPMENT | EQUP117X | VIVONET 3.0 DW SRS RC |
| EQUIPMENT | EQUP1191 | SanwaCrimson DW |
| EQUIPMENT | EQUP1194 | AURUSPAY 5.1.5.30 GTW RC |
| EQUIPMENT | EQUP1196 | SitioUnoOneTip1.0HcSrsSs |
| EQUIPMENT | EQUP119S | M.M Retail Pro DW RC SRS |
| EQUIPMENT | EQUP119Z | FEXCO OpenConectGwDwEcMs |
| EQUIPMENT | EQUP11AA | BASYS IQ GTW RC SRS |
| EQUIPMENT | EQUP11AC | CYBRSRC TK GW RC SRS |
| EQUIPMENT | EQUP11AG | RIDS SOFTWARE |
| EQUIPMENT | EQUP11AW | ACI Pos Host EC SS GTW |
| EQUIPMENT | EQUP11AX | ACI Pos Host EC MS GTW |
| EQUIPMENT | EQUP11B1 | 3C Payment GTW |
| EQUIPMENT | EQUP11BT | Mexico GuestPlus DW |
| EQUIPMENT | EQUP11BZ | PAX S300 Pinpad |
| EQUIPMENT | EQUP11C2 | Crimson 1.25 TCPIP RC |
| EQUIPMENT | EQUP11SC | Monetra 8.x  SRS |
| EQUIPMENT | EQUP11SL | BILLMTRXNXT GTW RCSRS EC |
| EQUIPMENT | EQUP11SU | CONNECTX GTW RCSRS EC MS |
| EQUIPMENT | EQUP11UW | NCR EPS 2.5 DW |
| EQUIPMENT | EQUP11VO | IBM GTW EHI RC |
| EQUIPMENT | EQUP11VP | NCR EPS 2.5 SRS |
| EQUIPMENT | EQUP11VQ | Mexico PayPoint GT REC |
| EQUIPMENT | EQUP11VS | Payvision GTW EC DL HOST |
| EQUIPMENT | EQUP11W2 | Eddie Bauer RC SRS EC |
| EQUIPMENT | EQUP11X4 | CR1013481_VAR |
| EQUIPMENT | EQUP11XL | ACCERTIFY TKN RC SRS EC |
| EQUIPMENT | EQUP11XQ | ACCEPT BLUE GTW RC SRS |
| EQUIPMENT | EQUP11XR | ACCEPTBLUE GTW RC SRS EC |
| EQUIPMENT | EQUP11Y6 | TouchNetUC6.5 RCSRS MS |
| EQUIPMENT | EQUP11YD | DL Host RCSRS |
| EQUIPMENT | EQUP11Z9 | JACK HENRY GTW RC EC SS |
| EQUIPMENT | EQUP11ZN | PayPal PayFlow GTW RM3 |
| EQUIPMENT | EQUP11ZW | AJB FIPAY EPS v2.2 |
| EQUIPMENT | EQUP122X | Carnival Cruise Lines |
| EQUIPMENT | EQUP122Z | CONDUENT GTW EC |
| EQUIPMENT | EQUP1265 | TravStar 1 POS |
| EQUIPMENT | EQUP127B | MEXICO LANE3000 DW |
| EQUIPMENT | EQUP127F | WF RC VPN EC |
| EQUIPMENT | EQUP127N | WF DW RC EC |
| EQUIPMENT | EQUP128A | LAUREATE GMA RC EC DWSRS |
| EQUIPMENT | EQUP128J | Viper 9.00.00 RC SS VPN |
| EQUIPMENT | EQUP128R | PINNACLE NIM 3.0 SRS RC |
| EQUIPMENT | EQUP128Z | BYTEMARK GTW RC SRS SS |
| EQUIPMENT | EQUP12AE | AMT v1.4 GTW SRS RC SS |
| EQUIPMENT | EQUP12AM | Cayman EC GTW |
| EQUIPMENT | EQUP12B5 | Breadcrumbv1GTWmsRCSRS |
| EQUIPMENT | EQUP12B6 | Breadcrumbv1GTWssRCSRS |
| EQUIPMENT | EQUP12C0 | CURBSTONE 7.06 SRS RC SS |
| EQUIPMENT | EQUP12C2 | TRANSACTIS GTW ECSRSRC |
| EQUIPMENT | EQUP12CI | BrdgePy PayGuardian GW |
| EQUIPMENT | EQUP12CY | DiscountDrugMart Retail |
| EQUIPMENT | EQUP12K0 | Mexico Engage V200T 3G |
| EQUIPMENT | EQUP12L1 | ACI WW POSTILION RC GTW |
| EQUIPMENT | EQUP12L3 | CR1100294_VAR |
| EQUIPMENT | EQUP12L7 | ACCULYNKPAYSGTWV2.0RCSRS |
| EQUIPMENT | EQUP12NA | DSG RC EC  |
| EQUIPMENT | EQUP12NJ | tranzpaydtwrc |
| EQUIPMENT | EQUP12T1 | VF Duo-CAGE-RC DW SRS |
| EQUIPMENT | EQUP12UB | ICSCAGE6.0.0.35RcSrsSsEc |
| EQUIPMENT | EQUP12UN | GIVELIFY RC EC |
| EQUIPMENT | EQUP12W2 | NelnetQuikPay RC EC SRS |
| EQUIPMENT | EQUP1073 | 2CPUSA (2C Processor USA, LLC) |
| EQUIPMENT | EQUP108R | Nash6Mar10 |
| EQUIPMENT | EQUP109A | GSI eBay EC RC |
| EQUIPMENT | EQUP109N | Comp1Mar12 |
| EQUIPMENT | EQUP10AK | CardnetDeepmala13thmar2014 |
| EQUIPMENT | EQUP10C9 | AllMar17 |
| EQUIPMENT | EQUP10DG | CardnetMar19 |
| EQUIPMENT | EQUP10E9 | Nash5Mar20 |
| EQUIPMENT | EQUP10FG | CardnetMar24 |
| EQUIPMENT | EQUP10YW | Canadian Vx670 Wi-Fi |
| EQUIPMENT | EQUP10YZ | VerePay Technologies |
| EQUIPMENT | EQUP110E | Shift4$$$OnNet GTW RC EC |
| EQUIPMENT | EQUP110R | B2B GTW RTL DWVXN RC |
| EQUIPMENT | EQUP111M | ECRS Catapult 5.3 RC |
| EQUIPMENT | EQUP111W | SigmaPayments GTW DW EC |
| EQUIPMENT | EQUP112D | South Batch Auth 2000 |
| EQUIPMENT | EQUP112E | TransResCdDog GtwDwRC |
| EQUIPMENT | EQUP112K | Canadian e315 IntPinPad |
| EQUIPMENT | EQUP112N | PAYM01 v1.0 RC DW EC GTW |
| EQUIPMENT | EQUP112W | Freds OLS V1 |
| EQUIPMENT | EQUP112Z | Mrch Prtnrs GTW RC |
| EQUIPMENT | EQUP113D | Tempus GTWY |
| EQUIPMENT | EQUP113F | Cayan GTW RC |
| EQUIPMENT | EQUP113J | ACI RCS GTW RC MS |
| EQUIPMENT | EQUP113O | CSG SYSTEMS RC DW |
| EQUIPMENT | EQUP113W | TOUCHNET SRS DW EC RC |
| EQUIPMENT | EQUP1144 | Viper 8.00.00 RC |
| EQUIPMENT | EQUP1151 | Bill 1st GTW DW RC |
| EQUIPMENT | EQUP1153 | TOUCHNET DW RC |
| EQUIPMENT | EQUP115X | IQMETRIX EC DW SRS RC |
| EQUIPMENT | EQUP1168 | Payfirma GTW DW RC |
| EQUIPMENT | EQUP116O | USH TA Kiosks DW RC |
| EQUIPMENT | EQUP116Y | TPE 2.xx RC GTW |
| EQUIPMENT | EQUP1172 | CSG SYSTEMS GTW EC RC |
| EQUIPMENT | EQUP1178 | Direx X 10.0.0 GTW DW RC |
| EQUIPMENT | EQUP117A | TenderRet v5.0 RC SRS |
| EQUIPMENT | EQUP117C | CSC HNB RC DW SRS |
| EQUIPMENT | EQUP117Y | Cmps Batch Auth2.5 |
| EQUIPMENT | EQUP1192 | CREDITCALL HC RC |
| EQUIPMENT | EQUP1193 | CREDITCALL HC EC RC |
| EQUIPMENT | EQUP1195 | VGSsrl SnApp8.3.10 SRSrc |
| EQUIPMENT | EQUP119X | PAYWIRE GTW EC SRS RC |
| EQUIPMENT | EQUP119Y | ACI Postilion EC GTWY MS |
| EQUIPMENT | EQUP11A4 | DSG Synchrony RC SRS |
| EQUIPMENT | EQUP11AE | PAYDIANT BP GTW RC SRS |
| EQUIPMENT | EQUP11BF | Apriva Pay Plus Adrd 4.x |
| EQUIPMENT | EQUP11BH | 911SoftwareCloud9GtwRcEc |
| EQUIPMENT | EQUP11BI | 911SoftwareCloud9GtwRc |
| EQUIPMENT | EQUP11BV | CANADIAN VX 820 DUET EM |
| EQUIPMENT | EQUP11C5 | MOTIONSOFT GTWY SRS |
| EQUIPMENT | EQUP11CC | Six Flags RC |
| EQUIPMENT | EQUP11CK | TranSafe EDC GTW SRS |
| EQUIPMENT | EQUP11P2 | Parkmobile GTW EC RC SRS |
| EQUIPMENT | EQUP11SS | Ingenico iCT250 Terminal |
| EQUIPMENT | EQUP11TM | CURO FIN RC SRS |
| EQUIPMENT | EQUP11U1 | Mexico Vx520 DW |
| EQUIPMENT | EQUP11U9 | PAX Prolin 1.0 RC SRS |
| EQUIPMENT | EQUP11UC | HRADIUS GTW HC RC SRS |
| EQUIPMENT | EQUP11UX | NCR BYPS IP 2.2.2.16 DW |
| EQUIPMENT | EQUP11VK | DISH AUTH 1.0 RC MOTO |
| EQUIPMENT | EQUP11W9 | AJB FIPAY 2.3 RC SS |
| EQUIPMENT | EQUP11WU | 2CPUSA GTW ECOMM |
| EQUIPMENT | EQUP11WV | Penske GTW Retail |
| EQUIPMENT | EQUP11WW | MYCARD GTW RC SRS |
| EQUIPMENT | EQUP11X2 | PARKINGSFT GTW RC SRS EC |
| EQUIPMENT | EQUP11X9 | CR1010425_2 |
| EQUIPMENT | EQUP11XA | CR1010425_3 |
| EQUIPMENT | EQUP11XN | BEST BUY TA GETBIN RC EC |
| EQUIPMENT | EQUP11XV | Ann Taylor RC SRS |
| EQUIPMENT | EQUP11Y9 | CA MPOS Comsgate v2.6 EC |
| EQUIPMENT | EQUP11Z0 | CR1029878_Var |
| EQUIPMENT | EQUP11ZC | JACK HENRY GTW RC MS |
| EQUIPMENT | EQUP11ZT | Siong_Issue 2 |
| EQUIPMENT | EQUP11ZU | BYTEMARK GTW v2.2 RC SRS |
| EQUIPMENT | EQUP12 | ABC |
| EQUIPMENT | EQUP1200 | Tranzit 1200C Lan Controller |
| EQUIPMENT | EQUP123F | CRDCallReseller RC SS |
| EQUIPMENT | EQUP123I | CRDCallReseller EC RC MS |
| EQUIPMENT | EQUP123S | SETECS GTW EC RC SRS |
| EQUIPMENT | EQUP126G | DISH AUTH 1.0 RCSRS EC |
| EQUIPMENT | EQUP127G | WF MPLS RC |
| EQUIPMENT | EQUP127M | WF DW RC |
| EQUIPMENT | EQUP127X | NIC FD40 PIN Pad |
| EQUIPMENT | EQUP128H | WFPG Retail GTWY |
| EQUIPMENT | EQUP128L | ILToll ATS RC DW |
| EQUIPMENT | EQUP128X | AJB Custom EC |
| EQUIPMENT | EQUP129B | CD SmartSite3.0 Petro RC |
| EQUIPMENT | EQUP129F | CR1088824-VAR |
| EQUIPMENT | EQUP129P | PLXIS GTW RC MS |
| EQUIPMENT | EQUP129S | Seamless GTW HdcSrsSs |
| EQUIPMENT | EQUP129W | DelegoMXV2.5.4 EC RC SRS |
| EQUIPMENT | EQUP12A7 | 4DPayments v16 RcSrsMs |
| EQUIPMENT | EQUP12AD | VerisoftPOSv1 ms RC SRS |
| EQUIPMENT | EQUP12AX | SiteLinkWebEd1.5ECRCSRS |
| EQUIPMENT | EQUP12BA | InfoTouch GTW RC SRS |
| EQUIPMENT | EQUP12BB | Mexico Vx690 WiFi DW |
| EQUIPMENT | EQUP12BC | Mexico Vx690 3G DW |
| EQUIPMENT | EQUP12BH | ExaDigm G3 |
| EQUIPMENT | EQUP12BJ | Herbalife GTW |
| EQUIPMENT | EQUP12BN | TRANSACTIS GTWECSRSRCSS |
| EQUIPMENT | EQUP12BR | VESTA MX RC MOTO |
| EQUIPMENT | EQUP12BS | VESTA MX RC RECURRING |
| EQUIPMENT | EQUP12BT | NETePAYv5.06 ss RCSRSEC |
| EQUIPMENT | EQUP12C1 | CURBSTONE 7.06 SRS RC MS |
| EQUIPMENT | EQUP12CD | TWINOAKS GTW |
| EQUIPMENT | EQUP12CK | CR1132476_Var |
| EQUIPMENT | EQUP12CM | GILBCO SmartCRIND RCIPv1 |
| EQUIPMENT | EQUP12CS | UIC RC SRS vL31A1001 |
| EQUIPMENT | EQUP12CT | NCR EPS v2.7 ATL105 SRS |
| EQUIPMENT | EQUP12K2 | SiteLinkOmaha1.5GTWRCSRS |
| EQUIPMENT | EQUP12KM | GK TransAction+7.6RC SS |
| EQUIPMENT | EQUP12KS | EIGEN MiraServ EC |
| EQUIPMENT | EQUP12KT | EIGEN MiraServ MOTO |
| EQUIPMENT | EQUP12L0 | FORTE GTW ISO MS |
| EQUIPMENT | EQUP12L2 | Paysafe Pymt XP GTWECRC |
| EQUIPMENT | EQUP12LA | Canadian e355 IntPinPad |
| EQUIPMENT | EQUP12LN | INGENICO FDRC 1.0 GW DW |
| EQUIPMENT | EQUP12M7 | ViaTouch GTW RC SRS |
| EQUIPMENT | EQUP12M9 | AIO v1 ss RC SRS |
| EQUIPMENT | EQUP12MK | USAePay PayFus GwRcMs |
| EQUIPMENT | EQUP12ML | Avanti Markets2 |
| EQUIPMENT | EQUP12MW | CRQ000000029577_var |
| EQUIPMENT | EQUP12N8 | Electronic Payments GTW |
| EQUIPMENT | EQUP12NK | EQUINOX 1.0 RC SS |
| EQUIPMENT | EQUP12NW | Toshiba ACE V8R1 RC SRS |
| EQUIPMENT | EQUP12NY | xpressVARgtwrc |
| EQUIPMENT | EQUP12O2 | Payware GTW Omaha |
| EQUIPMENT | EQUP12O5 | Exadigm N5 NEXGO |
| EQUIPMENT | EQUP12O8 | OnePay Global GTW RC EC |
| EQUIPMENT | EQUP12OG | VeriFoneSCA 2.20.x RC DW |
| EQUIPMENT | EQUP12OO | ChargeLogic GW RcSrsMs |
| EQUIPMENT | EQUP12OU | CRQ000000106455 |
| EQUIPMENT | EQUP12OY | Blue Parasol DW RC |
| EQUIPMENT | EQUP12PB | HotSauce v7.2 SRS ms |
| EQUIPMENT | EQUP12PE | HR PMNTDEM MOTO RCDW GTW |
| EQUIPMENT | EQUP12PF | HR PMNTDEM ECOM RCDW GTW |
| EQUIPMENT | EQUP12PK | SI DCAP Cousinsco Nash |
| EQUIPMENT | EQUP12PL | uCom RC Gateway |
| EQUIPMENT | EQUP12PU | P400 IntegratedPinpad CA |
| EQUIPMENT | EQUP12QP | AxiaMed GTW RC SRS Singl |
| EQUIPMENT | EQUP12RD | LOC SMS v3 ATL105 SRS EC |
| EQUIPMENT | EQUP12RM | Diamondscan RC |
| EQUIPMENT | EQUP12RN | ADYEN GATEWAY ECOMM |
| EQUIPMENT | EQUP12RO | ADYEN GATEWAY |
| EQUIPMENT | EQUP12RW | GasPOS RC V4.2 SRS SS |
| EQUIPMENT | EQUP12S2 | EHI IBM iSMP4 RC CR GTW |
| EQUIPMENT | EQUP12S5 | AURUS GTW RC EC SRS SS |
| EQUIPMENT | EQUP12S7 | AURUS GTW RC EC VPN SS |
| EQUIPMENT | EQUP12SQ | AlacGWOrbipayV8.5SSRCSRS |
| EQUIPMENT | EQUP12SX | GreyWolf RC EC |
| EQUIPMENT | EQUP12SY | GreyWolf RC EC MS |
| EQUIPMENT | EQUP12U1 | FANDUEL TVGNETWORK RC EC |
| EQUIPMENT | EQUP12U5 | CRQ000000207963_Class Var1 |
| EQUIPMENT | EQUP12UC | Toshiba Elixer v1 RC SRS |
| EQUIPMENT | EQUP12UM | Epicor Cloud GTW RC  |
| EQUIPMENT | EQUP12UO | DejavooDvCreditRC1.20 |
| EQUIPMENT | EQUP12UP | Curb Mobility RC SRS |
| EQUIPMENT | EQUP12UV | Equinox Luxe 8500i |
| EQUIPMENT | EQUP12W1 | GGS GTW MOTO RC HDC |
| EQUIPMENT | EQUP12WE | EDDIE BAUER AWS RC EC |
| EQUIPMENT | EQUP12WF | TR MCM 5.0 DW TA |
| EQUIPMENT | EQUP12WQ | Ziosk PS v6 RC SRS |
| EQUIPMENT | EQUP12X8 | 0419_VAR |
| EQUIPMENT | EQUP12XC | APG VERIFONE RC ECOMM |
| EQUIPMENT | EQUP12XL | Gravity Direct GTW RC EC |
| EQUIPMENT | EQUP12XP | Funds Transfer RC |
| EQUIPMENT | EQUP12XS | Gilbarco ATL105 v20.0x |
| EQUIPMENT | EQUP12XT | Epicor Eagle GTW RC |
| EQUIPMENT | EQUP12XV | 06_21_VAR |
| EQUIPMENT | EQUP1174 | Touchsuite 2.0 RC DW SRS |
| EQUIPMENT | EQUP11BO | CDEARTH EC RC SRS |
| EQUIPMENT | EQUP11X0 | PARKINGSFT GTW RC SRS |
| EQUIPMENT | EQUP1286 | CBKC RC DW EC |
| EQUIPMENT | EQUP12AJ | BISGLOBAL GTWECSRSRCSS |
| EQUIPMENT | EQUP12BI | Herbalife EC |
| EQUIPMENT | EQUP12BM | TRANSACTIS GTWECSRSRCMS |
| EQUIPMENT | EQUP12CV | NCR EPS v2.9 ATL105 SRS |
| EQUIPMENT | EQUP12K5 | Arts People RC EC |
| EQUIPMENT | EQUP12KW | VF PW Conn RC GTW EC |
| EQUIPMENT | EQUP12LC | CHECKALT KLIK GTW |
| EQUIPMENT | EQUP12LT | MPGS GTW RC EC |
| EQUIPMENT | EQUP12MI | WU APOLLO RC GW |
| EQUIPMENT | EQUP12MY | ICS - Cage - EC RC |
| EQUIPMENT | EQUP12NG | GeoPagos QPM1 GTW RC SRS |
| EQUIPMENT | EQUP12ON | ChargeLogic GW RcSrsMsEc |
| EQUIPMENT | EQUP12P3 | Pronto Xi v740.x RC |
| EQUIPMENT | EQUP12PG | CUBIC GTW RC EC |
| EQUIPMENT | EQUP12PM | CKS EZ v2.2018 RC SRS |
| EQUIPMENT | EQUP12PT | AE_CAN_EC |
| EQUIPMENT | EQUP12Q3 | MERCHANTLINKGTWY ECOMM |
| EQUIPMENT | EQUP12QI | Paycertify GTW MOTO SS |
| EQUIPMENT | EQUP12QV | ACI RCS v5.2 GTW EC MS |
| EQUIPMENT | EQUP12R6 | CRQ000000152961_0205 |
| EQUIPMENT | EQUP12RS | PayScout GTWY RC SRS |
| EQUIPMENT | EQUP12SR | AlacGWOrbipV8.5SSRCSRSEC |
| EQUIPMENT | EQUP12TV | EIGEN DEV PTS GTW  |
| EQUIPMENT | EQUP12W6 | Presto RC |
| EQUIPMENT | EQUP12X9 | NAPSE RC CP |
| EQUIPMENT | EQUP12Y0 | ValorPay GTW RC SRS |
| EQUIPMENT | EQUP12Y1 | VALOR PAY EC GTW RC SRS |
| EQUIPMENT | EQUP12B8 | Breadcrumbv1GTWmsRCSRSEC |
| EQUIPMENT | EQUP12KO | BIS Global GTW |
| EQUIPMENT | EQUP102E | ACI ISD Java Switch EC |
| EQUIPMENT | EQUP1075 | OLU Zeamster v2.0 RC MO |
| EQUIPMENT | EQUP114I | CastleTechPrjMerv1.0DWRC |
| EQUIPMENT | EQUP116C | IPC InfineaPay v1.0 DWRC |
| EQUIPMENT | EQUP117Z | Jersey Mikes TA DWRC SRS |
| EQUIPMENT | EQUP119W | PAYWIRE GTW SRS RC |
| EQUIPMENT | EQUP11A5 | MSTS MultiSVC GTW MoToDW |
| EQUIPMENT | EQUP11B7 | MOTIONSOFT |
| EQUIPMENT | EQUP11C3 | LAMTA Cubic Tran GTW RC |
| EQUIPMENT | EQUP11QN | FD OMAHA RC DW |
| EQUIPMENT | EQUP127T | WF ISO8583 DW EC |
| EQUIPMENT | EQUP12AZ | ICS RC DWSRS |
| EQUIPMENT | EQUP12B4 | 4DPayments v16 RcSrsSs |
| EQUIPMENT | EQUP12O3 | Worldnet GTW VPN RC |
| EQUIPMENT | EQUP12QH | Paycertify GTW MOTO MS |
| EQUIPMENT | EQUP1126 | Monetra 1.0.0 EC |
| EQUIPMENT | EQUP11AK | EPICOR GTW IAB |
| EQUIPMENT | EQUP11CH | Gilbarco SmCrnd 1.0.x RC |
| EQUIPMENT | EQUP11QF | Mexico MOVE2500G DW |
| EQUIPMENT | EQUP11XJ | CARDNL GETTKN RC SRS EC |
| EQUIPMENT | EQUP123H | CRDCallReseller RC MS |
| EQUIPMENT | EQUP1250 | Omni 1250 Terminal |
| EQUIPMENT | EQUP128W | ILToll ATS RC PTS |
| EQUIPMENT | EQUP1293 | PM RC EC SRS GTW Multi |
| EQUIPMENT | EQUP129X | DelegoMXV2.5.4 RC SRS |
| EQUIPMENT | EQUP12AI | KCX v1.0.18 EC SRS RC MS |
| EQUIPMENT | EQUP12LQ | Aldelo EDC 7.0 SRS HC |
| EQUIPMENT | EQUP12NE | CRQ000000049450_Var |
| EQUIPMENT | EQUP12NI | tranzpayecdtwrc |
| EQUIPMENT | EQUP12NU | xpressgtwrc |
| EQUIPMENT | EQUP12P6 | EHI IBM GTW RC CRD ONLY |
| EQUIPMENT | EQUP12QQ | AxiaMed GTWRCSRS ECSingl |
| EQUIPMENT | EQUP12R2 | Wirecard RC SRS GTWY DW |
| EQUIPMENT | EQUP12RF | Auth.net Reseller/EPP |
| EQUIPMENT | EQUP12RY | Aptos Pymt 2017.3 RC VPN |
| EQUIPMENT | EQUP12SB | AURUS GTW RC SRS MS |
| EQUIPMENT | EQUP12SS | ALA GWOrbipayV8.5SSRCSRS |
| EQUIPMENT | EQUP12TM | Apriva BroadPOS PAX S300 |
| EQUIPMENT | EQUP12UI | Pineapple GTW RC SS |
| EQUIPMENT | EQUP12W9 | PaymentMate v2.1 Tempus |
| EQUIPMENT | EQUP12WM | BluefinGateway GwEc |
| EQUIPMENT | EQUP12XF | CYBRSRC TK GW RC EC |
| EQUIPMENT | EQUP12MJ | USAePay PayFus GwRcEcMs |
| EQUIPMENT | EQUP12S9 | AURUS GTW RC SRS SS |
| EQUIPMENT | EQUPLEPT | RC SalePointTrovato v7.0 RC |
| EQUIPMENT | EQUPLIEM | MultiLink |
| EQUIPMENT | EQUPLLAN | PTI-Tellan PC HUB 2Pk HDC |
| EQUIPMENT | EQUPLMCR | Natl Merchant Ctr |
| EQUIPMENT | EQUPLOGS | 5TH Dimension GTW RC DW |
| EQUIPMENT | EQUPLOHA | RadiantAloha7.0 |
| EQUIPMENT | EQUPLRCV | GoVolution RC GTW |
| EQUIPMENT | EQUPLS50 | LS50 L/US WIRE POS50 Cellular |
| EQUIPMENT | EQUPLSPS | Dell Shop Starter |
| EQUIPMENT | EQUPLTWB | Salon UltimateV12 DW POS |
| EQUIPMENT | EQUPM260 | ITSVisualMatrixv2.6.0 |
| EQUIPMENT | EQUPM413 | TorISISw/MTXWinEPSv4.13 |
| EQUIPMENT | EQUPMCIT | Simple Tran MCI Terminal--EDC |
| EQUIPMENT | EQUPMKHB | PTI-Tellan PC HUB 10 Pk TDC |
| EQUIPMENT | EQUPMNNQ | HYPERCOM T7PT COMBO - G3 BAM COV/EOL |
| EQUIPMENT | EQUPMTRX | MicroTrax PC Controller |
| EQUIPMENT | EQUPLR01 | ICL RETAIL SYSTEMS |
| EQUIPMENT | EQUPM248 | Tender Retail Multi Merch Connect V4.2.8 |
| EQUIPMENT | EQUPMAC5 | PTI-Tellan MAC HUB 5Pk HDC |
| EQUIPMENT | EQUPMCZX | TRADEWIND POS |
| EQUIPMENT | EQUPMETC | CCAserver 4.5.1 Rest RC |
| EQUIPMENT | EQUPMGYE | DATAMATX GATEWAY ECOM |
| EQUIPMENT | EQUPMNN5 | TRANZ 380 X 2 64k - G3 BAM COV/EOL |
| EQUIPMENT | EQUPMO01 | APRIVA |
| EQUIPMENT | EQUPMS01 | FIDELIO MICRO SYSTEMS |
| EQUIPMENT | EQUPMULT | MULT Multilane |
| EQUIPMENT | EQUPMVGW | PPI PayMover e-comm (G/W) |
| EQUIPMENT | EQUPMX01 | TOMAX |
| EQUIPMENT | EQUPNCR | NCR Falcon |
| EQUIPMENT | EQUPNGOM | XANGO - ECOMM |
| EQUIPMENT | EQUPNIPP | VFI OMNI 7000LE |
| EQUIPMENT | EQUPNLWG | GOVOLUTION NON EC GTWY  |
| EQUIPMENT | EQUPNMBL | EXXON MOBIL - ALOHA |
| EQUIPMENT | EQUPNNII | VERIFONE ZON II TERM. |
| EQUIPMENT | EQUPNTBT | Aurus GTW |
| EQUIPMENT | EQUPNTGA | eProcessing Network ePN Transaction v 3.5  |
| EQUIPMENT | EQUPOGWY | Olo Gateway |
| EQUIPMENT | EQUPOUC1 | POSitouch |
| EQUIPMENT | EQUPPBAE | GWAY CONNECT(ECOMMERCE) |
| EQUIPMENT | EQUPPCUO | MS POS Customer Owned |
| EQUIPMENT | EQUPPH03 | CINGULAR 2125 CELL PHONE |
| EQUIPMENT | EQUPPLDM | Plug&Play Direct Mkt |
| EQUIPMENT | EQUPPTN3 | DATACAP TWN/IPTrn3.0NRTH |
| EQUIPMENT | EQUPRC70 | NCRComprisv7.05.02 |
| EQUIPMENT | EQUPMP01 | COMPUTAC, INC |
| EQUIPMENT | EQUPMP3A | AAA Compass Recurring |
| EQUIPMENT | EQUPMSUP | FD Mobile Pay Single User |
| EQUIPMENT | EQUPNBKY | CORNER BAKERY XPIENT |
| EQUIPMENT | EQUPNSW1 | Synergy Software |
| EQUIPMENT | EQUPNWAM | Dinerware2.9 Multi Settle |
| EQUIPMENT | EQUPON01 | ADONIX TRANSCOMM |
| EQUIPMENT | EQUPPCM8 | Hypercom T8 |
| EQUIPMENT | EQUPPG01 | WFPG |
| EQUIPMENT | EQUPPGTE | TEMPUS GATEWAY |
| EQUIPMENT | EQUPPMPV | AM PM systems U-POS v1.0 |
| EQUIPMENT | EQUPR2CM | CYBERSOURCE GATEWAY ECOM |
| EQUIPMENT | EQUPRO01 | OMRON SYS OF AMERICA |
| EQUIPMENT | EQUPSIGE | TNS NASH ISO GATEWAY EC |
| EQUIPMENT | EQUPSTW8 | ICSTreatware4.8 |
| EQUIPMENT | EQUPT7PG | C/O Hypercom T7PG Terminal |
| EQUIPMENT | EQUPTL01 | TOTAL COMPUTING SOLUTION |
| EQUIPMENT | EQUPV400 | Xpient v4.00.99 |
| EQUIPMENT | EQUPVB66 | Keystroke POS-VSE001 |
| EQUIPMENT | EQUPTE01 | ALOHA TECHNOLOGIES |
| EQUIPMENT | EQUPLLNN | WebAuthorize Leased Line |
| EQUIPMENT | EQUPM2CM | Network Mer Gateway ECOM |
| EQUIPMENT | EQUPMNN6 | HYPERCOM T7E - G3 BAM COV/EOL |
| EQUIPMENT | EQUPMPEC | Campana Axis0.1 RC DW EC |
| EQUIPMENT | EQUPMSI1 | MSI |
| EQUIPMENT | EQUPLWRC | RT Lawrence Gateway |
| EQUIPMENT | EQUPM239 | DCMercuryplusv2.3.9 |
| EQUIPMENT | EQUPMAPP | MAPP 100 Terminal |
| EQUIPMENT | EQUPMOFD | AAA_ACMO Dual VPN |
| EQUIPMENT | EQUPMSP6 | IBMSurePOS6REL2 |
| EQUIPMENT | EQUPMXLM | SPOS32_4.0 EQUINOXM4230XMLB |
| EQUIPMENT | EQUPNCSH | SunCash (g/w) |
| EQUIPMENT | EQUPNDWS | Brandwise (g/w) |
| EQUIPMENT | EQUPNRON | BevolPad 2.01 MobRest RC |
| EQUIPMENT | EQUPOMRN | C/O OMRON 100A OR C/O OMRON 9812 CHECK RDR |
| EQUIPMENT | EQUPOMS1 | Storis Management Systems |
| EQUIPMENT | EQUPOPRO | Optimal Robotics |
| EQUIPMENT | EQUPPSP1 | Western Union Payment Services |
| EQUIPMENT | EQUPQU01 | SEQUOIA RETAIL SYSTEMS |
| EQUIPMENT | EQUPRAJB | ACCOR AJB SOFTWARE |
| EQUIPMENT | EQUPSTN1 | MainStreet NashEDCv2013 EC |
| EQUIPMENT | EQUPTFS1 | National Fulfillment Services |
| EQUIPMENT | EQUPME01 | AMERICAN EXPRESS MOTO |
| EQUIPMENT | EQUPMGRM | PAYPAL PAYFLOW GTWY ECOM |
| EQUIPMENT | EQUPMI01 | APPLIED MICRO TECHNOLOGY |
| EQUIPMENT | EQUPMICV | IC Verify PC Software - Multi-user Version |
| EQUIPMENT | EQUPMK20 | PTI-Tellan PC MAC HUB 20 Pk HDC |
| EQUIPMENT | EQUPMLLN | AAA - Southern California |
| EQUIPMENT | EQUPNA01 | SIERRA NATIONAL CORP |
| EQUIPMENT | EQUPNLGT | ThndrAndLight Lime3.4 RC |
| EQUIPMENT | EQUPNTNR | PTI-Nurit 2060 |
| EQUIPMENT | EQUPNTRY | SENTRYPMNT GTWY EC DW RC |
| EQUIPMENT | EQUPNU80 | NURIT 8000 GPRS |
| EQUIPMENT | EQUPO250 | Omron 250 Terminal--EDC |
| EQUIPMENT | EQUPOCMP | NCO Group CMP GTWY  |
| EQUIPMENT | EQUPOPT4 | Equinox T4205 |
| EQUIPMENT | EQUPORCE | Multiforce |
| EQUIPMENT | EQUPOTML | FD130 Duo |
| EQUIPMENT | EQUPOV73 | Island Pac Onepoint v7.3 |
| EQUIPMENT | EQUPP110 | PAYwarePCv1.1.0 |
| EQUIPMENT | EQUPP721 | Star-Plusv7.21 |
| EQUIPMENT | EQUPPIAL | DatacapDialTranNorth |
| EQUIPMENT | EQUPPISV | PAYEEZY GATEWAY WEBSERVICEAPIECOMM |
| EQUIPMENT | EQUPPK20 | PTI-Tellan PC HUB 20 Pk TDC |
| EQUIPMENT | EQUPPNMV | Curbstone v2.1 EC |
| EQUIPMENT | EQUPPO01 | SALES POINT SYSTEMS |
| EQUIPMENT | EQUPPSEP | Lamps Plus Epicor |
| EQUIPMENT | EQUPRCMV | VistaPaymentSerecom v4.2 |
| EQUIPMENT | EQUPRCPM | CYBERSOURCE CPM V6.4 |
| EQUIPMENT | EQUPRD4W | 4Ward Plastiq GTW EC |
| EQUIPMENT | EQUPRDWD | World Bcard RC GTW |
| EQUIPMENT | EQUPRGLG | CHARGELOGIC V3.0 |
| EQUIPMENT | EQUPRNEY | BNYMicrosRetailxSTORE6.0 |
| EQUIPMENT | EQUPRSGT | eProcessing ISO GTW |
| EQUIPMENT | EQUPS001 | JCS |
| EQUIPMENT | EQUPSBJ8 | Class B Dejavoo V-8S |
| EQUIPMENT | EQUPSE01 | CONFERENCE MGMT SERV |
| EQUIPMENT | EQUPSITB | Shift4 Software $$$ in the Bank |
| EQUIPMENT | EQUPSNLL | ISO 8583 Lease Line 123 |
| EQUIPMENT | EQUPST01 | MAIN STREET SOFWORKS |
| EQUIPMENT | EQUPSTWC | PC Charge Win Software |
| EQUIPMENT | EQUPSV28 | OnePOS POS System v2.8 |
| EQUIPMENT | EQUPSX01 | RMS TOUCH |
| EQUIPMENT | EQUPT4TP | PAYEEZY GATEWAY REALTIMEMGRRTLMOTO |
| EQUIPMENT | EQUPTCMG | First Atl Comrce Gateway |
| EQUIPMENT | EQUPTCPH | VersiTouch 12.12.1 |
| EQUIPMENT | EQUPTER1 | LinkPoint 3000 |
| EQUIPMENT | EQUPTIZA | FD130 |
| EQUIPMENT | EQUPTLAU | PTI-Tellan PC Authorize |
| EQUIPMENT | EQUPTPX3 | Class B PAX MT30  |
| EQUIPMENT | EQUPTR01 | INTRIX SYSTEMS GROUP |
| EQUIPMENT | EQUPTRI1 | PARCS |
| EQUIPMENT | EQUPTRTE | Trender Terminal |
| EQUIPMENT | EQUPTSEB | AT and T SecureBuy (g/w) |
| EQUIPMENT | EQUPTYRC | eGenuity v6 RC |
| EQUIPMENT | EQUPV101 | DATAVANTAGE STROE 21 |
| EQUIPMENT | EQUPV315 | Vrfne Paywre Tran v3.1.5 |
| EQUIPMENT | EQUPV531 | Tomax Rtlnet v5.3.1 |
| EQUIPMENT | EQUPVA13 | Amt.s v 4.0-VAP001 |
| EQUIPMENT | EQUPVA30 | Alliance WinCCA v 4.20.03-VCP001 |
| EQUIPMENT | EQUPVA31 | Passport v 6.01-VGL001 |
| EQUIPMENT | EQUPVA44 | DCCS-VDY001 |
| EQUIPMENT | EQUPVA98 | Squirrel POS v 1.41 Pay at the Table-VSQ003 |
| EQUIPMENT | EQUPVAGS | FIS METAVANTE GTWY |
| EQUIPMENT | EQUPVB34 | Oracle iPayment-VOR001 |
| EQUIPMENT | EQUPVB43 | Epsilon-VRA002 |
| EQUIPMENT | EQUPYSAT | CITY OF SEATTLE |
| EQUIPMENT | EQUPZKT1 | CHECK21 FDGTWY EC |
| EQUIPMENT | EQUPNWRK | PSN CCPrcsg GTW RC DW EC |
| EQUIPMENT | EQUPOSRC | PROSOL TSEND9.4.6 DW RC |
| EQUIPMENT | EQUPP120 | PAYwarePCv1.2.0 |
| EQUIPMENT | EQUPPCPP | Petrovend Pay-At-The-Pump |
| EQUIPMENT | EQUPRCY4 | SPOS32_3.1-T4220,T4230,M4230,M4240,T4100 RCY4 |
| EQUIPMENT | EQUPREND | Merchant Engine Dial |
| EQUIPMENT | EQUPRORC | RORC |
| EQUIPMENT | EQUPRPRO | Purity Products RC |
| EQUIPMENT | EQUPRVGW | APRIVA GATEWAY |
| EQUIPMENT | EQUPS9WT | WIRETRUST GATEWAY |
| EQUIPMENT | EQUPSAS9 | SASI SD-9 |
| EQUIPMENT | EQUPSBRI | Stack Bri |
| EQUIPMENT | EQUPSINT | Chase-Intuit |
| EQUIPMENT | EQUPSMTM | TRUSTCOMMERCE GTWY ECOM |
| EQUIPMENT | EQUPTC45 | TEC 4500 |
| EQUIPMENT | EQUPTL41 | Telrad Tip 41 |
| EQUIPMENT | EQUPTSEC | Xerox atlas apsunrailec |
| EQUIPMENT | EQUPTYEC | eGenuity v6 RC EC |
| EQUIPMENT | EQUPV671 | Aloha v6.7.1 |
| EQUIPMENT | EQUPVA19 | Booklog v 2.00-VBL001 |
| EQUIPMENT | EQUPVA38 | ICVerify v 4.0.3-VIV004 |
| EQUIPMENT | EQUPVT22 | POS Designer v3.6 with MTXEPS WinEPS v 8.14-VJP001 |
| EQUIPMENT | EQUPWIFI | FD200 WIFI |
| EQUIPMENT | EQUPWLYW | Llewellyn Worldwide EC |
| EQUIPMENT | EQUPTERM | UNKNOWN - TERM |
| EQUIPMENT | EQUPTHRC | SWITCH COMMERCE GTWY RC |
| EQUIPMENT | EQUPVA04 | ACR 2000 v 4.4-VAC001 |
| EQUIPMENT | EQUPVT49 | ScanMaster v 2.00.02.16 with MTXEPS WinEPS-VSX007 |
| EQUIPMENT | EQUPVB93 | PayFlow Pro v 3.0-VVS001 |
| EQUIPMENT | EQUPMOTX | PTI-Nurit 3010 Mobitex |
| EQUIPMENT | EQUPNU85 | PTI-Nurit 2085 TDC |
| EQUIPMENT | EQUPO395 | Omni 395 Terminal |
| EQUIPMENT | EQUPSECM | GW WEBSVC API ECOMM |
| EQUIPMENT | EQUPMCST | Bonnier |
| EQUIPMENT | EQUPMNN7 | PayPal  (Verisign) Payflow Link Reseller - G3 BAM |
| EQUIPMENT | EQUPMRV2 | The Sftwr Mill Roam v2.1 |
| EQUIPMENT | EQUPNCOD | FW Webb Direct Send |
| EQUIPMENT | EQUPNECO | ADN Ecomm |
| EQUIPMENT | EQUPNERC | Aone Pos v1.0 RC |
| EQUIPMENT | EQUPNKGW | ePayments Network GTWY |
| EQUIPMENT | EQUPNSPL | TRANSACTION PLUS V7.09 |
| EQUIPMENT | EQUPO460 | Omni 460 Terminal |
| EQUIPMENT | EQUPOM30 | MainstmonetraECOM3.0 |
| EQUIPMENT | EQUPPAPE | GWAY API(ECOMMERCE) |
| EQUIPMENT | EQUPPBAS | GWAY CONNECT (RTL/MOTO) |
| EQUIPMENT | EQUPPCC1 | CSI Linkpoint (g/w) |
| EQUIPMENT | EQUPPGTK | Skipjack ISO GTW |
| EQUIPMENT | EQUPPL92 | RetailPro EFTLink v9.2 |
| EQUIPMENT | EQUPPNIE | MRCH PRTNRS NASH ISO EC |
| EQUIPMENT | EQUPPREX | TECHTRX PRIMETREX S1.0.0 |
| EQUIPMENT | EQUPPV31 | Vrfne Payware PIM v3.10 |
| EQUIPMENT | EQUPPV36 | RATEX POSVR v36 |
| EQUIPMENT | EQUPRAHA | NCR Aloha  EDC v13.1 |
| EQUIPMENT | EQUPRASS | Radiant Softsense |
| EQUIPMENT | EQUPRIX2 | ImageTech Vmatrix 2.6.0 |
| EQUIPMENT | EQUPRNET | SECURENET GTWY ECOM |
| EQUIPMENT | EQUPRPCS | MILSOFT IVR |
| EQUIPMENT | EQUPRPOS | POS Port ECR--EDC |
| EQUIPMENT | EQUPRS01 | GERS |
| EQUIPMENT | EQUPRSCB | Retail Sol CPU Montr BRN |
| EQUIPMENT | EQUPSAS8 | SASI SD-8 |
| EQUIPMENT | EQUPSCEC | eGenuity v6 single RC EC |
| EQUIPMENT | EQUPSCRQ | Wells Service CRQ6 (BART) |
| EQUIPMENT | EQUPSFTY | Microsoft Dynamics RMS |
| EQUIPMENT | EQUPSH01 | COMPUTERIZED LODGING SYS |
| EQUIPMENT | EQUPSP5C | SAGE SPS GATEWAY ECOM |
| EQUIPMENT | EQUPSTAE | Vista POS v3.3.3  EC |
| EQUIPMENT | EQUPT380 | Tranz 380 Terminal |
| EQUIPMENT | EQUPT77S | Hypercom T77S Sprocket Fed Printer in 1 |
| EQUIPMENT | EQUPTCMA | TEC MA 1650 |
| EQUIPMENT | EQUPTOKH | Tokheim |
| EQUIPMENT | EQUPTPTS | Xerox State & Local GTW |
| EQUIPMENT | EQUPTRAN | UNKNOWN - TRAN |
| EQUIPMENT | EQUPV201 | DATAVANTAGE TRADEWIND |
| EQUIPMENT | EQUPV2PC | Verifone Payware PC v. 1.2.2 |
| EQUIPMENT | EQUPVA21 | Transaction+ v 7.14-VDB002 |
| EQUIPMENT | EQUPVA56 | Mate Plus is now called XD2000-VEX001 |
| EQUIPMENT | EQUPVA69 | SPOS32 v 1.4.49-VHY004 |
| EQUIPMENT | EQUPVA72 | SPOSG v 9.B -VHY007 |
| EQUIPMENT | EQUPVB26 | VPS/IS on-line auth v 2-VNN001 |
| EQUIPMENT | EQUPVB36 | XiPay-VPM001 |
| EQUIPMENT | EQUPVC06 | UpFront Software V19.4.3-VUF001 |
| EQUIPMENT | EQUPVT03 | BNA Banksys C-Zam V10000000 Java debit/cred-VBN001 |
| EQUIPMENT | EQUPVT15 | Gilbarco Passport v 4.01.23-VGL002 |
| EQUIPMENT | EQUPVT59 | Progressive Smart v 4.00.15-VXS001 |
| EQUIPMENT | EQUPWRLT | PTI-Nurit 2090 Wireless-Term |
| EQUIPMENT | EQUPXSP9 | PURCHASE EXPRESS 3.2 SP9 |
| EQUIPMENT | EQUPMOPA | FD MOBILE PAY APP VERSION |
| EQUIPMENT | EQUPNCAR | Ventek Car Gtwy RC DW |
| EQUIPMENT | EQUPNLYN | MICRODYNONLINE GTWY |
| EQUIPMENT | EQUPOM01 | TICKETS.COM |
| EQUIPMENT | EQUPOR01 | ASIST CORNERSTONE TECH |
| EQUIPMENT | EQUPPAYX | Parallel AuthPayX |
| EQUIPMENT | EQUPPJCK | Skipjack Gateway |
| EQUIPMENT | EQUPPK10 | PTI- Tellan PC HUB 10 PK TDC |
| EQUIPMENT | EQUPPWRE | Snapwire v1.0.0 RC |
| EQUIPMENT | EQUPPYV4 | DatacapDialTranNash |
| EQUIPMENT | EQUPQLTV | Uniqlo |
| EQUIPMENT | EQUPRE81 | ItechRetalvend21rms8.1.9 |
| EQUIPMENT | EQUPRLPR | SquirrelProfess v1.8/8.0 |
| EQUIPMENT | EQUPRLPS | General Parts Intl -DBS  |
| EQUIPMENT | EQUPRSP1 | Merchant Charge+ |
| EQUIPMENT | EQUPRWR2 | DINERWARE ENGINE V2.9 |
| EQUIPMENT | EQUPRX01 | PERFECT ORDER INC |
| EQUIPMENT | EQUPS5BW | XpientTPE_FDMS4.5.5 |
| EQUIPMENT | EQUPSFTW | BIG 5 CORP JDA SOFTWARE |
| EQUIPMENT | EQUPSGAT | CIRRUS CORPORATION  |
| EQUIPMENT | EQUPSN4V | Trans Net Serv GWY ECOM |
| EQUIPMENT | EQUPSOV2 | INISolutionsv2 |
| EQUIPMENT | EQUPSPNX | SPOS32_4.0 EQUINOXT4220XML |
| EQUIPMENT | EQUPSSO1 | INTERCEPT PAYMENT SOLUTIONS (Mo/To) |
| EQUIPMENT | EQUPSSO2 | INTERCEPT PAYMENT SOLUTIONS |
| EQUIPMENT | EQUPSSTY | ICSStyleware3.7 |
| EQUIPMENT | EQUPSSWR | Paradise Software RC |
| EQUIPMENT | EQUPSV13 | CDSmartSolutionsv1.3 |
| EQUIPMENT | EQUPSVIR | Banc One CollegeStudent Dial |
| EQUIPMENT | EQUPSWEN | SG Swenson & Sons RC |
| EQUIPMENT | EQUPSWYN | DWEMFusion6000LITEv2.1.3 |
| EQUIPMENT | EQUPTCSL | FoodtecRCNashV2013Res |
| EQUIPMENT | EQUPTECO | CENPOS GTWY ECOM |
| EQUIPMENT | EQUPTES1 | Visual Matrix v 1.7 |
| EQUIPMENT | EQUPTKTD | Automated Ticket Dispenser--EDC |
| EQUIPMENT | EQUPTL10 | Telrad Tip 10 |
| EQUIPMENT | EQUPTNFW | Systime/Versa POS/TNT Fireworks |
| EQUIPMENT | EQUPTON2 | PRINCETON GATEWAY (Mo/To) |
| EQUIPMENT | EQUPTRSA | Xpient RSA TPEBPASS v4.6  |
| EQUIPMENT | EQUPTSXT | SPOS32_3.3.179 T4100B |
| EQUIPMENT | EQUPTTTT | 1256 |
| EQUIPMENT | EQUPTWCN | Dcap TwTran 3.0 Cnet |
| EQUIPMENT | EQUPTWR6 | Treatware POS v4.6 |
| EQUIPMENT | EQUPTX01 | PHARMACEUTICAL TECH |
| EQUIPMENT | EQUPTXMS | DentalXchangeMS3.0 |
| EQUIPMENT | EQUPUFL1 | Software Under Flap |
| EQUIPMENT | EQUPUGPE | PlugNPay v4.2MO RC EC |
| EQUIPMENT | EQUPUREL | TrueReligionEpicorPOS6.4 |
| EQUIPMENT | EQUPUTIC | Nauticom |
| EQUIPMENT | EQUPUTS1 | Interactive Audiotext Services, Inc |
| EQUIPMENT | EQUPV3NS | Ver 3.10 ICVERIFY Windows New SU |
| EQUIPMENT | EQUPV3SM | Ver 3.10 ICV Conv from SU to Multi User |
| EQUIPMENT | EQUPV3SU | Ver 3.10 ICVERIFY Upgrade, DOS to Window |
| EQUIPMENT | EQUPVA01 | NOVA EXPERTISE SYSTEMS |
| EQUIPMENT | EQUPVA15 | PARCS-VAS001 |
| EQUIPMENT | EQUPVA20 | SellMate v 7.0.0-VBT001 |
| EQUIPMENT | EQUPVA36 | Gsite v 6.4.03-VGL002 |
| EQUIPMENT | EQUPVA41 | Dine-amics -VDI001 |
| EQUIPMENT | EQUPVA43 | Domain POS v 2.11-VDO001 |
| EQUIPMENT | EQUPVA57 | ScanNet v 4.1-VFA001 |
| EQUIPMENT | EQUPVA83 | BookStore Retail POS-VIB001 |
| EQUIPMENT | EQUPVA84 | Storepay-VIC001 |
| EQUIPMENT | EQUPVA89 | StoreManager ES v 2.5.-VIN001 |
| EQUIPMENT | EQUPVB03 | PaymentMate v 2.0-VTE002 |
| EQUIPMENT | EQUPVB09 | Roam v 11-VTF001 |
| EQUIPMENT | EQUPVB24 | UltraTMS v 6.9.7-VNS001 |
| EQUIPMENT | EQUPVB25 | T-REX Point of Sale v 3.2-VND001 |
| EQUIPMENT | EQUPVB47 | ImagInn -VRE001 |
| EQUIPMENT | EQUPVB69 | Storis v 7.3.3.3 -VSA001 |
| EQUIPMENT | EQUPVB71 | ccPay-VSG001 |
| EQUIPMENT | EQUPVB74 | Spectrum Payment Processing v 2.1.0-VTE001 |
| EQUIPMENT | EQUPVB77 | Credit Link 4000-VTS001 |
| EQUIPMENT | EQUPVB87 | Tangent POS v 2.0-VVO001 |
| EQUIPMENT | EQUPVB99 | Synaro Payment Processor v 5.2-VIP001 |
| EQUIPMENT | EQUPVE31 | v3.00 ICV WIN SU UPGRD |
| EQUIPMENT | EQUPVE38 | v3.00 ICV UPGD DOS/WIN M |
| EQUIPMENT | EQUPVMM4 | ICV4.4 Multi User MS |
| EQUIPMENT | EQUPVPRX | VIVOPAY 4500 |
| EQUIPMENT | EQUPVRFY | v2.46 ICV Win M-User Up |
| EQUIPMENT | EQUPVSDX | Class B Dejavoo V-8S+ |
| EQUIPMENT | EQUPVSM4 | ICV4.4 Single User MS |
| EQUIPMENT | EQUPVT09 | Wayne Plus III v 1.26B-VDW003 |
| EQUIPMENT | EQUPVT14 | Gilbarco G-Site v 6.1.04-VGL001 |
| EQUIPMENT | EQUPVT17 | SurePOS ACE Release 401 Level A049-VIC001 |
| EQUIPMENT | EQUPVT25 | Fuel Links PC2000 v 2.0-VMO001 |
| EQUIPMENT | EQUPVT30 | WinEPS v 817-VMW001 |
| EQUIPMENT | EQUPVT32 | FuelForce FF894 v 1.00-VML002 |
| EQUIPMENT | EQUPVT37 | Pharoh v 7.0.0.0-VPA002 |
| EQUIPMENT | EQUPVT47 | ISS45 with Ingenico eNConcert v8 on Atlanta-VSX002 |
| EQUIPMENT | EQUPVT48 | ISS45 with MTXEPS WinEPS v 8.0 on Atlanta-VSX004 |
| EQUIPMENT | EQUPW8TW | VRFNE PAYWARE GTWY ECOM |
| EQUIPMENT | EQUPWFDS | Flower Foods |
| EQUIPMENT | EQUPWHHO | Whitehouse |
| EQUIPMENT | EQUPWSDT | TSDWeb GTW |
| EQUIPMENT | EQUPWYDR | Wayne Dresser |
| EQUIPMENT | EQUPX830 | Ratner MX830 |
| EQUIPMENT | EQUPXDG3 | Midax eft manag v3.1 |
| EQUIPMENT | EQUPXMGN | PHOENIX MNGD NET GTWY DW         |
| EQUIPMENT | EQUPXXIC | EZIC Ver 2.5 |
| EQUIPMENT | EQUPY101 | KCS COMPUTER SYSTEMS |
| EQUIPMENT | EQUPYNSH | USAEPAY NASH ISO GTWY |
| EQUIPMENT | EQUPYP9S | SystimeVersPOS7.4.3.3Nsh |
| EQUIPMENT | EQUPYTXN | Reno Tahoe via Payware Transact V3.2.4 |
| EQUIPMENT | EQUPZONX | ZON JR XL Terminal |
| EQUIPMENT | EQUPNTWS | PITNEY BOWES / TANDEM |
| EQUIPMENT | EQUPTEWG | TrustCom ISO GTW EC |
| EQUIPMENT | EQUPVA08 | PAXFDNB x 02C-VAM007 |
| EQUIPMENT | EQUPVA18 | ChargeAnywhere v 2.0.0-VCI001 |
| EQUIPMENT | EQUPVA34 | NETePay ML/XML CT v 3.10-VDS001 |
| EQUIPMENT | EQUPVA68 | SPOS32 v 1.4.36 -VHY003 |
| EQUIPMENT | EQUPVAU4 | ICV4.4 Add User |
| EQUIPMENT | EQUPVB85 | Universal Payment v 4.12 -VUN001 |
| EQUIPMENT | EQUPVB95 | VersiTouch Credit v 3.043-VVT001 |
| EQUIPMENT | EQUPVB96 | TPE v 4.0 -VXS001 |
| EQUIPMENT | EQUPVC03 | Payware ERP v 4.3-VPP001 |
| EQUIPMENT | EQUPVEBS | SERVEBASE GATEWAY |
| EQUIPMENT | EQUPVER4 | IC Verify Dos/Dos Upgrade |
| EQUIPMENT | EQUPVR21 | Forever21 AJB DIRECT |
| EQUIPMENT | EQUPVT27 | Micros 8700 v 1.0.5-VMI001 |
| EQUIPMENT | EQUPVT51 | Aurora v 4.0.1 on Atlanta & Chicago-VSV001 |
| EQUIPMENT | EQUPVT53 | ISIS with MTXEPS WinEPS v 4.13-VTX001 |
| EQUIPMENT | EQUPWIP2 | Vx570 - FD POS |
| EQUIPMENT | EQUPYC01 | SOLUTIONS BY COMPUTERS |
| EQUIPMENT | EQUPVA55 | CRS Retail Store v 2.5 -VEO001 |
| EQUIPMENT | EQUPZKCL | SPOS32_3.3.179 M4240B |
| EQUIPMENT | EQUPVB05 | Nurit 3010 using RTS4 66D v. 4.09A-VLM002 |
| EQUIPMENT | EQUPNL11 | CashierliveNovaLibra1.1 |
| EQUIPMENT | EQUPPH01 | CELL TREK AUDIOVOX |
| EQUIPMENT | EQUPQCB2 | MRTUS PMNT XP GTWY ECOM |
| EQUIPMENT | EQUPRBLD | Storebuilder (g/w) |
| EQUIPMENT | EQUPS306 | SlipStreamv3.0.6 |
| EQUIPMENT | EQUPTLV5 | RMS Solution v6.2.5 |
| EQUIPMENT | EQUPVA85 | IC VERIFY |
| EQUIPMENT | EQUPVA90 | CMS1 v 8.00.00-VPD001 |
| EQUIPMENT | EQUPVB42 | Aloha v 6.1-VRA001 |
| EQUIPMENT | EQUPNS01 | INNSOFT SOFTWARE |
| EQUIPMENT | EQUPPHRE | SAPPHIRE 6.0 |
| EQUIPMENT | EQUPPRN5 | VFI PCCharge 5.10.0 CNet |
| EQUIPMENT | EQUPRF01 | PERFORMANCE CONCEPTS |
| EQUIPMENT | EQUPRSFD | FD410 |
| EQUIPMENT | EQUPSPA1 | GHSPA V110010 |
| EQUIPMENT | EQUPTHSL | FortTechBaseline3.5 RCDW |
| EQUIPMENT | EQUPTIV1 | Activant |
| EQUIPMENT | EQUPTLPK | PTI-Tellan PC HUB 5Pk HDC |
| EQUIPMENT | EQUPTNUV | Boston University |
| EQUIPMENT | EQUPTS8M | WIRETRUST GATEWAY ECOM |
| EQUIPMENT | EQUPTUNS | WESTUNION SPEEDPAY GWY |
| EQUIPMENT | EQUPTWFI | FD-100 WiFi TI |
| EQUIPMENT | EQUPVA27 | Solutions One HME Systems  v 8.7-VCU001 |
| EQUIPMENT | EQUPVA79 | ICE 500 Plus & SPOSIJ v. 07A-VHY014 |
| EQUIPMENT | EQUPVA94 | Message Sentry-VID001 |
| EQUIPMENT | EQUPVB27 | Communication Serv v4 for DOS 7.47-VNB001 |
| EQUIPMENT | EQUPVB98 | Domain POS v 2.11-VDO001 |
| EQUIPMENT | EQUPVE33 | v3.00 ICV WIN NEW S U |
| EQUIPMENT | EQUPVE3A | v3.00 ICV VER VALC ADD M |
| EQUIPMENT | EQUPVMED | Novant Medquest RC |
| EQUIPMENT | EQUPVNET | CIT-VNET |
| EQUIPMENT | EQUPVOCN | EnvocRC NASH Retail |
| EQUIPMENT | EQUPVPSL | Vista PointofSale v3.3.3 |
| EQUIPMENT | EQUPVT20 | IT Retail 2000 -VIR001 |
| EQUIPMENT | EQUPVT55 | Triversity 6.0 UNIX-VTV002 |
| EQUIPMENT | EQUPVT57 | RiTa v 2.0-VVF002 |
| EQUIPMENT | EQUPWNSH | nSoftwareDirPayIntV6.0EC |
| EQUIPMENT | EQUPYAIR | Payair RC DW EC GTWY |
| EQUIPMENT | EQUPYEAS | YESPAY EASY VT GATEWAY |
| EQUIPMENT | EQUPYENW | Adyen GTW |
| EQUIPMENT | EQUPYSUS | Toys R Us IBM  |
| EQUIPMENT | EQUPYT01 | SMYTH SYSTEMS |
| EQUIPMENT | EQUPPV21 | Tempus Pmtmate v2.1 |
| EQUIPMENT | EQUPSTOP | OneStopCommerce Software |
| EQUIPMENT | EQUPTRXW | MRTUS PMNT XP GTWY |
| EQUIPMENT | EQUPV3AM | Ver 3.10 ICVERIFY Val Code - Add MIDs |
| EQUIPMENT | EQUPVB54 | CounterPart v 8.0-VSB001 |
| EQUIPMENT | EQUPVER5 | v2.46 ICV D-W M-User Up |
| EQUIPMENT | EQUPVT16 | 911 CREDITLINE V4.1 |
| EQUIPMENT | EQUPVSG4 | ICV4.4 Single Upg |
| EQUIPMENT | EQUPRIT3 | NURIT 3010 Cell Trek Expel |
| EQUIPMENT | EQUP12Y2 | EpicPay .01 EC GTW RC |
| EQUIPMENT | EQUP12Y4 | ADVMOBILEPYMTS SRS RC |
| EQUIPMENT | EQUP12Y8 | Fiscal L1NXP v07. SRS SS |
| EQUIPMENT | EQUP12YB | 07_23_VAR |
| EQUIPMENT | EQUP12YE | NCR GTW EC RC SRS |
| EQUIPMENT | EQUP12YO | 08_16_VAR_02 |
| EQUIPMENT | EQUP12YP | GK Trans+ V8 RC EC |
| EQUIPMENT | EQUP12YV | AMT v1.4.2 GTW SRS RC SS |
| EQUIPMENT | EQUP12Z1 | 10/9_VAR5 |
| EQUIPMENT | EQUP12Z3 | 10/9_VAR5 |
| EQUIPMENT | EQUP12ZF | OLS Gateway |
| EQUIPMENT | EQUP12ZI | 6/10_VAR5 |
| EQUIPMENT | EQUP12ZM | CardKnox PEv1.0 RC EC |
| EQUIPMENT | EQUP12ZW | 20/10_VAR8 |
| EQUIPMENT | EQUP13A0 | ACI RCS GTW EC HDC IP |
| EQUIPMENT | EQUP13A6 | GRIZZLY EC |
| EQUIPMENT | EQUP13AG | 15/11_VAR6 |
| EQUIPMENT | EQUP13AK | MPGS GTW EC RC SRS |
| EQUIPMENT | EQUP13AN |  Presto Payment RC |
| EQUIPMENT | EQUP13AU | Direct Send EC compass N |
| EQUIPMENT | EQUP13AX | PAYTRACE GTW RC EC |
| EQUIPMENT | EQUP13BO | AMT v1.4.2 GTW SRS RC |
| EQUIPMENT | EQUP13C1 | AdvMobPymnt SRS RC |
| EQUIPMENT | EQUP13DY | USAePay GTW RC SS |
| EQUIPMENT | EQUP13EA | PAX A80 |
| EQUIPMENT | EQUP13EE | FIVESTARS SRS EC RC |
| EQUIPMENT | EQUP13GA | 29/8_VAR49 |
| EQUIPMENT | EQUP13HU | Cubic UMO Pay RetailMOTO |
| EQUIPMENT | EQUP13I6 | IngenicoFDRCsa&tsi4.1SRS |
| EQUIPMENT | EQUP12YU | 28/8_VAR6 |
| EQUIPMENT | EQUP12YW | CORECOMM SRS RC |
| EQUIPMENT | EQUP12YX | CORECOMM SRS EC RC |
| EQUIPMENT | EQUP12ZO | 18/10_VAR5 |
| EQUIPMENT | EQUP12ZU | 20/10_VAR7 |
| EQUIPMENT | EQUP13A7 | Childrens Place EC |
| EQUIPMENT | EQUP13AE | 12/11_VAR4 |
| EQUIPMENT | EQUP13AJ | MPGS GTW RC SRS |
| EQUIPMENT | EQUP13AL | UMS UCharge GW SRS RC SS |
| EQUIPMENT | EQUP13AM | BLUEPARAPARAGN SRS RC EC |
| EQUIPMENT | EQUP13AP | CellfiePaymentSRSRC |
| EQUIPMENT | EQUP13AY | LOYALE GTW RC SRS |
| EQUIPMENT | EQUP13B2 | Pineapple GTW RC 1.3.0 |
| EQUIPMENT | EQUP13B3 | Pineapple GTW RC MS1.3.0 |
| EQUIPMENT | EQUP13BB | 17/1_VAR20 |
| EQUIPMENT | EQUP13BE | LoanPaymentPro GTW RC EC |
| EQUIPMENT | EQUP13BZ | Amazon Compass North |
| EQUIPMENT | EQUP13C0 | Defenders Compass North |
| EQUIPMENT | EQUP13C5 | COREComSRSECRC |
| EQUIPMENT | EQUP13CH | 21/2_VAR91 |
| EQUIPMENT | EQUP13CL | Sabre MOTO MC CNP RC |
| EQUIPMENT | EQUP13D4 | Pineapple V1.8.0 GTW MS |
| EQUIPMENT | EQUP13DB | Sabre MC CNP RC |
| EQUIPMENT | EQUP13DC | InChargePay 1.0 RCECGTW |
| EQUIPMENT | EQUP13DZ | GoChip SDK Ver1.6.0 CPRC |
| EQUIPMENT | EQUP13E5 | Skrill RC  |
| EQUIPMENT | EQUP13EH | CenPOS GW RcSrsMsEc |
| EQUIPMENT | EQUP13EW | Azure Secure Payment RC |
| EQUIPMENT | EQUP13FT | PAYGISTIXGTYW OMAHA EC |
| EQUIPMENT | EQUP13GR | e285 mPOS |
| EQUIPMENT | EQUP13GX | VENTEK GTWY RC SRS |
| EQUIPMENT | EQUP13HT | Cubic UMO Pay GTWY EC |
| EQUIPMENT | EQUP13IC | Vanco EC |
| EQUIPMENT | EQUP13II | AA RIM vPay Inflight |
| EQUIPMENT | EQUP13L2 | NBS Buypass ISO GTW VPN |
| EQUIPMENT | EQUP13LW | Prodvalidation11-16-22 |
| EQUIPMENT | EQUP13MM | Liquid Payments |
| EQUIPMENT | EQUP13N8 | Everyware |
| EQUIPMENT | EQUP13NS | Monetra Buypass GTW SS |
| EQUIPMENT | EQUP13QC | Newegg EC Compass North |
| EQUIPMENT | EQUP20QB | Eigen Development VX 680 3G |
| EQUIPMENT | EQUP35PI | FD35 PIN Pad w NFC-EMV |
| EQUIPMENT | EQUPACLR | TELECHECK ACCELERA Terminal |
| EQUIPMENT | EQUP13AS | Datawire Compass project |
| EQUIPMENT | EQUP13B6 | Bulloch BT9000 v7 RC SRS |
| EQUIPMENT | EQUP13B7 | BridgePay, GTW, RC |
| EQUIPMENT | EQUP13BL | CENPOS GTWY SRS EC RC |
| EQUIPMENT | EQUP13BX | PaymentRouter V2 SRSRC |
| EQUIPMENT | EQUP13C6 | 18/2_VAR89 |
| EQUIPMENT | EQUP13CZ | 18/3_VAR70 |
| EQUIPMENT | EQUP13DD | InChargePay 1.0 RCMOTGTW |
| EQUIPMENT | EQUP13E0 | 29/4_VAR69 |
| EQUIPMENT | EQUP13E3 | Ingenico ePymt RC DW EC |
| EQUIPMENT | EQUP13E4 | Ingenico ePymt RC DW |
| EQUIPMENT | EQUP13E6 | 16/5_VAR20 |
| EQUIPMENT | EQUP13E8 | 16/5_VAR37 |
| EQUIPMENT | EQUP13ET | Canadian ISC250 Pinpad |
| EQUIPMENT | EQUP13F1 | COMDATA SmrtSl v3 RC SRS |
| EQUIPMENT | EQUP13FK | CreditCall GTW Omaha RC |
| EQUIPMENT | EQUP13FS | PAYGISTIXGTYW OMAHAETC |
| EQUIPMENT | EQUP13G5 | Blue Sparq RC 0.1.0 |
| EQUIPMENT | EQUP13G8 | Ravelin Get PAN |
| EQUIPMENT | EQUP13GD | LINK2500 AZUL |
| EQUIPMENT | EQUP13GE | V240M CAC  |
| EQUIPMENT | EQUP13GI | 14/9_VAR37 |
| EQUIPMENT | EQUP13GQ | Vail Resort Tera |
| EQUIPMENT | EQUP13H3 | Agave Paymentsite v3 RC |
| EQUIPMENT | EQUP13H4 | AgavePaymentsitev3 RC EC |
| EQUIPMENT | EQUP13H5 | Flowbird PMT SVR v18 RC |
| EQUIPMENT | EQUP13HB | Synchrony RC GET PAN |
| EQUIPMENT | EQUP13HD | AJB COACH e335 |
| EQUIPMENT | EQUP13HO | 18/11_VAR38 |
| EQUIPMENT | EQUP13IE | TABLESAFE EC SRS RC |
| EQUIPMENT | EQUP13IM | PDI EXC EFC v8.0 RC SRS |
| EQUIPMENT | EQUP13IN | Canadian VFI V400c RC |
| EQUIPMENT | EQUP13J2 | WorldnetGo v7 GTW RC VPN |
| EQUIPMENT | EQUP13J6 | Pace Software RC EC |
| EQUIPMENT | EQUP13JA | WalmartTokenEC |
| EQUIPMENT | EQUP13K8 | Ingenico Move 5000 |
| EQUIPMENT | EQUP13KF | Secure GTW DW SRS EC MS |
| EQUIPMENT | EQUP13KM | Monetra GTWY |
| EQUIPMENT | EQUP13KX |  Gilbarco ATL105 v22 IP |
| EQUIPMENT | EQUP13L0 | Linga eCom (NMI) |
| EQUIPMENT | EQUP13LC | EasyPay GW RC SRS 3.1 SS |
| EQUIPMENT | EQUP13LO | Computop GTWY CP RC |
| EQUIPMENT | EQUP13LS |  CoreCommerce for PointC |
| EQUIPMENT | EQUP13M0 | Aurus Gateway RC DW |
| EQUIPMENT | EQUP13MC | 23/1_VAR51 |
| EQUIPMENT | EQUP13ML | Blue Sparq RC V.0.1.0 |
| EQUIPMENT | EQUP13MU | WeVend GTW RC SRS EC SS |
| EQUIPMENT | EQUP13N0 | PaymentPro 2.2 RC Multi |
| EQUIPMENT | EQUP13N1 | Everyware Clvr |
| EQUIPMENT | EQUP13N5 | Zebra Pay RC GTW 1.0 |
| EQUIPMENT | EQUP13N9 | iPOSPay1.0 GTW RC SRS |
| EQUIPMENT | EQUP13NC | Olapay 1.0 EC RC |
| EQUIPMENT | EQUP13NH | Cardconnect 5.2 RC CA |
| EQUIPMENT | EQUP13NV | White Glove Linga CP |
| EQUIPMENT | EQUP13OA | Linga (PAX) |
| EQUIPMENT | EQUP13OE | OLS GTW ATL105v1.0 |
| EQUIPMENT | EQUP13OG | AurusPay5.x GTW RC DW |
| EQUIPMENT | EQUP13OW | WeVend GTW RC |
| EQUIPMENT | EQUP13Q8 | Verifone Viper 11.00.00 |
| EQUIPMENT | EQUP13Q9 | AJB VF Fipay2.x ISO GTW |
| EQUIPMENT | EQUP13QK | Apriva Payter GTW RC  |
| EQUIPMENT | EQUP19GT | LAT19 GTWY  |
| EQUIPMENT | EQUP200T | FD200Ti |
| EQUIPMENT | EQUP20MX | MX880 PIN PAD |
| EQUIPMENT | EQUP20O4 | Data Wire Leased Line |
| EQUIPMENT | EQUP20O7 | MERCHANT PARTNERS - GATEWAY |
| EQUIPMENT | EQUP20OA | USA ePay |
| EQUIPMENT | EQUP20OJ | LAC Vx520 - Dual IP/Dial |
| EQUIPMENT | EQUP20QF | AJB Microsoft Canada |
| EQUIPMENT | EQUP20QO | MX Migration |
| EQUIPMENT | EQUP20R1 | HYPERCOM T7 |
| EQUIPMENT | EQUP20R4 | HYPERCOM T7Plus 8x20 Disp Wide Paper 2MB |
| EQUIPMENT | EQUP20R5 | Key Corp K23 2 |
| EQUIPMENT | EQUP20R8 | Verifone PAYware PC Retail/Rest/MoTo |
| EQUIPMENT | EQUP2S01 | GO SOFTWARE RITA SERVER |
| EQUIPMENT | EQUP4240 | SPOS32_3.1-T4220,T4230,M4230,M4240,T4100 4240 |
| EQUIPMENT | EQUP4562 | trytrhytrhtrh |
| EQUIPMENT | EQUP4WBS | PAYEEZY GATEWAY WEBSERVICEAPI |
| EQUIPMENT | EQUP57RE | HYPERCOM 5700+ RED |
| EQUIPMENT | EQUP77GQ | HYPERCOM T77GQ-F |
| EQUIPMENT | EQUP8000 | NURIT 8000 ON USW |
| EQUIPMENT | EQUP83GP | NURIT 8320 GPRS |
| EQUIPMENT | EQUPACOM | Anacom SecurePay (g/w) |
| EQUIPMENT | EQUPACR1 | ACR |
| EQUIPMENT | EQUPACRE | PC America Cash Register Express |
| EQUIPMENT | EQUPACUS | Rodopi Payment Gateway |
| EQUIPMENT | EQUPAGTE | Kubra Gateway ECOM |
| EQUIPMENT | EQUPALLA | Chevron |
| EQUIPMENT | EQUPAPAK | DATAPAK SERVICES CORPORATION (G/W DM) |
| EQUIPMENT | EQUPBCNE | Scheidt & Bachmann E-Comm |
| EQUIPMENT | EQUPBER3 | Payment Manager 4.x |
| EQUIPMENT | EQUPBER4 | CPM ver 6.x |
| EQUIPMENT | EQUPBJSP | AJBRTS V4.0DIAL BUYPASS |
| EQUIPMENT | EQUPBS01 | RATEX BUSINESS SOLUTIONS |
| EQUIPMENT | EQUPBSFT | CHARMING SHOPPES AJB |
| EQUIPMENT | EQUPC400 | IVI FLASH/ENCOUNTER 400 |
| EQUIPMENT | EQUPCA47 | Casio 4700 |
| EQUIPMENT | EQUPCE65 | Hypercom ICE 6500 |
| EQUIPMENT | EQUPCGTW | PRINCETONCARDCONNECTGTWY |
| EQUIPMENT | EQUPCPAY | PNCPAYEREXPRESSGATEWAY |
| EQUIPMENT | EQUPCROW | EC Services Corporation |
| EQUIPMENT | EQUPCTRC | Vetcentric Gateway |
| EQUIPMENT | EQUPD001 | ONE STEP DATA |
| EQUIPMENT | EQUPDATW | DATAWIRE MICRONODE |
| EQUIPMENT | EQUPDC86 | DataCard 860I Terminal |
| EQUIPMENT | EQUPDIEC | BridgePayGuardISO GTW EC |
| EQUIPMENT | EQUPDIRE | PAYWAY DIRECT GATEWAY  |
| EQUIPMENT | EQUPDXME | INDEX GTWY EC MULTI RC |
| EQUIPMENT | EQUPE400 | ChargeLogicECommv4.00 |
| EQUIPMENT | EQUPFLDH | BANFIELD Pet Hospital |
| EQUIPMENT | EQUPFTP2 | Envoy FTP2 |
| EQUIPMENT | EQUPFTP3 | Envoy FTP3 |
| EQUIPMENT | EQUPGE65 | i6580 PIN PAD |
| EQUIPMENT | EQUPGFCS | CNG Fuel Focus v5.16 |
| EQUIPMENT | EQUPGTEC | TGATE GTWY ECOM |
| EQUIPMENT | EQUPGTWS | Priority Pymts GTW |
| EQUIPMENT | EQUPH4ST | PAYEEZY GATEWAY HOSTEDPAYMENTRTLMOTO |
| EQUIPMENT | EQUPICOR | Epicor ESDM v2.4.1 RC |
| EQUIPMENT | EQUPID01 | IBID INCORPORTATED |
| EQUIPMENT | EQUPIECO | AJB-RC-fipayEcom |
| EQUIPMENT | EQUPIGTE | PSI GATE (G/W) |
| EQUIPMENT | EQUPIN01 | APPLIED INTELLIGENCE GRP |
| EQUIPMENT | EQUPINW1 | USI.net |
| EQUIPMENT | EQUP13EI | Azul Lane 7000 DR |
| EQUIPMENT | EQUP13GW | ATH POS ACE V8R2 RC SRS |
| EQUIPMENT | EQUP13HA | VESTA RC MOTO |
| EQUIPMENT | EQUP13HS | Electronic Pay EC RC GTW |
| EQUIPMENT | EQUP13HV | PayNearMe |
| EQUIPMENT | EQUP13J0 | INGENICO RC OMAHA TSI4.1 |
| EQUIPMENT | EQUP13J9 | aci RCS v5.2 iso GTW ec |
| EQUIPMENT | EQUP13K0 | FINVI GTW RC |
| EQUIPMENT | EQUP13KJ | GTW CoreCommerce |
| EQUIPMENT | EQUP13KO | CardFlight GTW RC V2 |
| EQUIPMENT | EQUP13KU | TRI CardDog 6.x Datawire |
| EQUIPMENT | EQUP13M7 | NCR Aloha EDC v19.6 SRS |
| EQUIPMENT | EQUP13MF | CAD Desk5000 PCI6 RC |
| EQUIPMENT | EQUP13ND | Paywire Gateway 3.2 GTW |
| EQUIPMENT | EQUP13NR | GTW Fortis Payment Syste |
| EQUIPMENT | EQUP13NU | Ingenico USI 5.12.x |
| EQUIPMENT | EQUP13O6 | IPOSPaymt1.0 GTW RC SRS |
| EQUIPMENT | EQUP13Q1 | LOC SMS v4.x ATL105 SRS |
| EQUIPMENT | EQUP13Q2 | IT Retail RC v7rx SRS |
| EQUIPMENT | EQUP20OF | Canadian Vx810 |
| EQUIPMENT | EQUP20OP | GoVolution RC GTW EC |
| EQUIPMENT | EQUP20OU | Multi-Systems Inc |
| EQUIPMENT | EQUP20OZ | Precidia |
| EQUIPMENT | EQUP20QE | AJB Software CAN |
| EQUIPMENT | EQUP20QI | AJB COACH Mx925 |
| EQUIPMENT | EQUP2HUM | PTI-Tellan MAC HUB 2Pk TDC |
| EQUIPMENT | EQUP3010 | NURIT 3010 ON USW |
| EQUIPMENT | EQUP3020 | 3020 |
| EQUIPMENT | EQUP3300 | Omni 3300 |
| EQUIPMENT | EQUP4220 | HYPERCOM T4220 |
| EQUIPMENT | EQUP50TI | FD50Ti |
| EQUIPMENT | EQUP50VO | Omni 3350 Terminal |
| EQUIPMENT | EQUP610C | VX610 CDMA WIRELESS |
| EQUIPMENT | EQUP8018 | Star-Plusv8.0.18 |
| EQUIPMENT | EQUPA421 | ADAK 421 |
| EQUIPMENT | EQUPALBR | Nova Libra Payment GTWY |
| EQUIPMENT | EQUPANAT | Sierra HELIX2000 Ver1.13 |
| EQUIPMENT | EQUPART1 | Online Merchant Center |
| EQUIPMENT | EQUPASC9 | VFI PCCharge 5.9.2 Bpass |
| EQUIPMENT | EQUPASOL | BBA POS Single RC |
| EQUIPMENT | EQUPASSS | EFS v 3.75 |
| EQUIPMENT | EQUPAV40 | XpientCCApplv4.00.96 |
| EQUIPMENT | EQUPAVON | Elavon eN-Concert v2.05 |
| EQUIPMENT | EQUPB001 | AJB |
| EQUIPMENT | EQUPBDM8 | Dejavoo M-8 |
| EQUIPMENT | EQUPBERS | Payment Manager 3.1.9 |
| EQUIPMENT | EQUPBILL | MSBill.com (g/w) |
| EQUIPMENT | EQUPBIV3 | /nsoftwareIBizIntegratV3 |
| EQUIPMENT | EQUPBL01 | SABLE TECHNOLOGIES |
| EQUIPMENT | EQUPBLAR | EDIBLE ARRNGMNTS ISO8583 |
| EQUIPMENT | EQUPBMBG | BLUE BAMBOO GATEWAY |
| EQUIPMENT | EQUPBP22 | Retalix BPIPlinkserver v2.2 |
| EQUIPMENT | EQUPBRA1 | KUBRA |
| EQUIPMENT | EQUPBUPA | VFIBUYPAKv5.04.06 |
| EQUIPMENT | EQUPC590 | Vrfne PCChg 5.9.0 |
| EQUIPMENT | EQUPCBJE | ISO LL Global with Full Tid and Purc/Com |
| EQUIPMENT | EQUPCBJG | DL TransArmor |
| EQUIPMENT | EQUPCBKM | VP Term with Full tid & no Purc/Com card |
| EQUIPMENT | EQUPCDRC | WIRECARD GTWY DW RC |
| EQUIPMENT | EQUPCHAR | PC Charge Internet Dial |
| EQUIPMENT | EQUPCHRD | MI9 Interface for OSH (Orchard supply interface) |
| EQUIPMENT | EQUPCLAT | Escalate1.0 |
| EQUIPMENT | EQUPCR01 | TECHRX |
| EQUIPMENT | EQUPCS01 | ACR SYSTEMS |
| EQUIPMENT | EQUPCSIR | Clear Commerce |
| EQUIPMENT | EQUPCTC1 | Control Transaction Corp./  CTC |
| EQUIPMENT | EQUPCTRW | Micros Tradewind v.10.0 |
| EQUIPMENT | EQUPCXST | Joseph A Bank Micros X-Store V5.5 POS |
| EQUIPMENT | EQUPDA01 | MEDASYST, INC |
| EQUIPMENT | EQUPDCLG | Credit Call Co UK (G/W) |
| EQUIPMENT | EQUPDEV1 | Software Development Inc |
| EQUIPMENT | EQUPDEX8 | Dejavoo X-8 |
| EQUIPMENT | EQUPDH3Q | PassportEDHv8.02.23.03Q |
| EQUIPMENT | EQUPDPRO | BondPRO BPE v8.5 RC |
| EQUIPMENT | EQUPEA13 | Ikea |
| EQUIPMENT | EQUPEBLE | Dream Builders Ecomm |
| EQUIPMENT | EQUPEBU1 | Nortel Networks Ebusiness Applications |
| EQUIPMENT | EQUPECOM | Cybersource Payment Manager v6.4 |
| EQUIPMENT | EQUPENT1 | Domain Point of Sale (Retail & MoTo) |
| EQUIPMENT | EQUPENT2 | Domain Point of Sale (E-comm) |
| EQUIPMENT | EQUPERVE | TOUCHNET T-SERVE |
| EQUIPMENT | EQUPESTP | OneStopEStore |
| EQUIPMENT | EQUPETDI | OMNIMEDIA GATEWAY |
| EQUIPMENT | EQUPF330 | PayfirstPFOSv3.30 |
| EQUIPMENT | EQUPFCM2 | VFI PAYwareTran 3.2.4 EC |
| EQUIPMENT | EQUPFDOM | ASF DM |
| EQUIPMENT | EQUPFTPJ | Envoy FTPJR |
| EQUIPMENT | EQUPGCYE | Paytrace GTW |
| EQUIPMENT | EQUPGENI | Ingenico Elite 510 LAN |
| EQUIPMENT | EQUPGILA | EDGIL ASSOCIATES GTWY |
| EQUIPMENT | EQUPGONL | BigOnline Store |
| EQUIPMENT | EQUPGPTY | ELEC PMNT PG GTWY |
| EQUIPMENT | EQUPGS01 | CSG SYSTEMS |
| EQUIPMENT | EQUPGTE | GTE Terminal |
| EQUIPMENT | EQUPHOST | CCC Hosting Engine (g/w) |
| EQUIPMENT | EQUPHPRA | CashPro Authorize (g/w) |
| EQUIPMENT | EQUPHPRO | ACH ProcWLinc RC EC DW |
| EQUIPMENT | EQUPIBPK | VFI BUYPAK 6.01 |
| EQUIPMENT | EQUPIC01 | v2.60 ICV Win New S-User |
| EQUIPMENT | EQUPIC03 | v2.60 ICV Win New M-User |
| EQUIPMENT | EQUPICE+ | Hypercom ICE 5500+ |
| EQUIPMENT | EQUPIDAS | Store21 4.69.018A |
| EQUIPMENT | EQUPIDSE | Server Add MID License |
| EQUIPMENT | EQUPIF01 | SHIFT 4 CORPORATION |
| EQUIPMENT | EQUPIHLT | EDIHealth GTWY |
| EQUIPMENT | EQUPILNK | CIT-LINK |
| EQUIPMENT | EQUPILYA | OReilly Automotive IPS SW |
| EQUIPMENT | EQUPIMCD | SLIM CD GATGEWAY |
| EQUIPMENT | EQUPIMET | Trimet |
| EQUIPMENT | EQUPINMC | VFI PCC5.10.0NashMultiEC |
| EQUIPMENT | EQUPINMG | VFI PWC NashMultiGtwy |
| EQUIPMENT | EQUPINP2 | PRINCETON ECOMM GATEWAY |
| EQUIPMENT | EQUPIPS2 | Eclipse Pymt. Terminal |
| EQUIPMENT | EQUPITCH | NETPAY PYMNT SWITCH GTWY  |
| EQUIPMENT | EQUPIV01 | TRIVERSITY SOFTWARE |
| EQUIPMENT | EQUPIWRW | ACI RCS V5.0 |
| EQUIPMENT | EQUPJ2CT | PayJunction Gateway ECOM |
| EQUIPMENT | EQUPJRNS | VFI RC Payware trans |
| EQUIPMENT | EQUPJTIP | OMNI 3740 Dual IP/Dial terminal |
| EQUIPMENT | EQUPL3TD | B2B SOFT GTW |
| EQUIPMENT | EQUPLCOD | v2.46 ICV Valcode-Chg Pro |
| EQUIPMENT | EQUP13OF | ACI RCS Presto GTW IP |
| EQUIPMENT | EQUP50BU | HP RP5000 Base Unit |
| EQUIPMENT | EQUPAM32 | Amex 3200 Terminal |
| EQUIPMENT | EQUPARS1 | Bluebird AutoMate |
| EQUIPMENT | EQUPCBIO | ISO Dual without terminal Mgmt |
| EQUIPMENT | EQUPCCMS | ICOMS Pymt Mgmt Svcs |
| EQUIPMENT | EQUPCNSH | LJS KFC NCR Nashville |
| EQUIPMENT | EQUPCRM4 | SPOS32_3.1- T4210, T4205 (Dial Only) |
| EQUIPMENT | EQUPCSYS | Sicom Sys |
| EQUIPMENT | EQUPD485 | Datacard 485ST Terminal |
| EQUIPMENT | EQUPD780 | Datacard 780ST Terminal |
| EQUIPMENT | EQUPDEGY | Eigen Dev Gateway |
| EQUIPMENT | EQUPDTSR | PLCB |
| EQUIPMENT | EQUPFOV8 | Seito FoodnBev v8 |
| EQUIPMENT | EQUPFRNT | UMS StoreFront PC |
| EQUIPMENT | EQUPG712 | Ingenico 712 |
| EQUIPMENT | EQUPGILB | Gilbarco Integrated |
| EQUIPMENT | EQUPGLVF | AVF CON CHRGLGIC GTWY |
| EQUIPMENT | EQUPGNEW | CHARGEANYWHERE GATEWAY |
| EQUIPMENT | EQUPHNET | Auth.net Gateway ECOM |
| EQUIPMENT | EQUPHQWZ | SPOS32_3.3.179 T4230 B |
| EQUIPMENT | EQUPHUB5 | PTI-Tellan PC HUB 5Pk TDC |
| EQUIPMENT | EQUPI001 | RETAIL TECH INTERNAIONAL |
| EQUIPMENT | EQUPISEC | T-Serve Touchnet Information Sys |
| EQUIPMENT | EQUPLBAR | GilbarcoPassport10.00.23 |
| EQUIPMENT | EQUPFWRE | nSoftwareDirPayIntV6.0 |
| EQUIPMENT | EQUPJI01 | FUJITSU TRANS SOLUTION |
| EQUIPMENT | EQUP13A8 | ToshibaACE v8R2 RC SRS |
| EQUIPMENT | EQUP13LH | CenPOS GTW EC |
| EQUIPMENT | EQUP12ZH | HFT PL RC |
| EQUIPMENT | EQUP13G7 | Flutterwave RC EC MO NSH |
| EQUIPMENT | EQUP13JZ | Auruspay 5.x RC DW CNP |
| EQUIPMENT | EQUP13L3 | Jackrabbit V2.0 RC EC MO |
| EQUIPMENT | EQUP13L9 | PAX BroadPos 1.x RC DW |
| EQUIPMENT | EQUP13MV | Justifi GTW RC EC |
| EQUIPMENT | EQUP13OP | 07/20_VAR12_Build_cancellable |
| EQUIPMENT | EQUP1400 | MicroNode 1400 Replacement for 960 |
| EQUIPMENT | EQUP20OO | Canadian Vx-680 3G |
| EQUIPMENT | EQUP41DC | HYPERCOM T4100 |
| EQUIPMENT | EQUPAE4Y | USAePay Gateway ECOM |
| EQUIPMENT | EQUPC0NT | VFI 1000SE with Integrated Contactless Reader |
| EQUIPMENT | EQUPC331 | TenderMerchConv3.3.1 |
| EQUIPMENT | EQUPCH01 | TECHPOINT, INC |
| EQUIPMENT | EQUPCLXT | Celerex Terminal--EDC |
| EQUIPMENT | EQUPCOMS | SICOMS |
| EQUIPMENT | EQUPCSV2 | PDQManufacturing CMS v2 |
| EQUIPMENT | EQUPDE01 | INTERGRATED SYSTEMS DEV |
| EQUIPMENT | EQUPDIVA | GODIVA AJBFIPAY |
| EQUIPMENT | EQUPDYSA | Roundys - AJB RTS v4.0 |
| EQUIPMENT | EQUPHUB2 | PTI-Tellan PC HUB 2 Pk TDC |
| EQUIPMENT | EQUP13H6 | Eigen Vx 820 Duet Pinpad |
| EQUIPMENT | EQUP13ID | TABLESAFE SRS RC |
| EQUIPMENT | EQUP13KR | Forte GTW MS |
| EQUIPMENT | EQUP13M6 | Cardknox 2.0 RC DW CA |
| EQUIPMENT | EQUP13OJ | LInga CP Magensa |
| EQUIPMENT | EQUP13OS | Desk3500 Class B |
| EQUIPMENT | EQUP1I01 | MICROS SYSTEMS |
| EQUIPMENT | EQUP20O1 | AMERICAN KENNEL CLUB |
| EQUIPMENT | EQUP20Q9 | Eigen Development VX820 |
| EQUIPMENT | EQUP20QG | AJB American Eagle Mx915 |
| EQUIPMENT | EQUP20QR | Canadian Vx820 Int PINPad |
| EQUIPMENT | EQUP20QV | Vx680 Int PIN Pad |
| EQUIPMENT | EQUPAMX3 | Amex PC Product |
| EQUIPMENT | EQUPANTL | Sierra National |
| EQUIPMENT | EQUPAU01 | COMPUTER APPLS UNLIMITED |
| EQUIPMENT | EQUPAV75 | DBSTransACTion+v7.5 |
| EQUIPMENT | EQUPB8AN | T8315 CPU/MONITOR BRAIN-Retail |
| EQUIPMENT | EQUPBER5 | BPD DM |
| EQUIPMENT | EQUPBSD1 | AJB RTS V4.1 DW RC |
| EQUIPMENT | EQUPBX01 | NBS |
| EQUIPMENT | EQUPC608 | TickettechRevControl6.08 |
| EQUIPMENT | EQUPCCRD | CitiFinancial T7Plus |
| EQUIPMENT | EQUPCMPI | NCR Compri Etransv90101 |
| EQUIPMENT | EQUPCPAC | ICE-PAC GRAPHICS |
| EQUIPMENT | EQUPCRGE | PTI-GO PC Charge |
| EQUIPMENT | EQUPCVAP | PNC iSites VApp |
| EQUIPMENT | EQUPDS6G | DataSym 6000 GR |
| EQUIPMENT | EQUPDSY1 | Radiant Systems |
| EQUIPMENT | EQUPDY01 | FINANCIAL DYNAMICS INC |
| EQUIPMENT | EQUPEC01 | SPECIALIST DATA SOLUTION |
| EQUIPMENT | EQUPECGW | vSecure Gateway DW |
| EQUIPMENT | EQUPFFUR | EnfaticaFusion RC GTY |
| EQUIPMENT | EQUPFOS1 | Retail  |
| EQUIPMENT | EQUPFTD1 | CCAPI FTD RC |
| EQUIPMENT | EQUPGCOR | LagoonCashier v8.5RCNash |
| EQUIPMENT | EQUPGGE4 | Desc |
| EQUIPMENT | EQUPGLOG | ChargeLogic v4.0 |
| EQUIPMENT | EQUPGTEG | DIGITAL PYMNT TECH CORP |
| EQUIPMENT | EQUPHBPK | PTI-Tellan PC HUB 10 Pk HDC |
| EQUIPMENT | EQUPI791 | i7910 - Wireless |
| EQUIPMENT | EQUPIASX | ALIASWIRE GTWY |
| EQUIPMENT | EQUPIFTH | BIT PointofSale v3.0 RC |
| EQUIPMENT | EQUPIICE | Hypercom ICE 5500 |
| EQUIPMENT | EQUPIJAV | ROI JAVACARD |
| EQUIPMENT | EQUPINML | VFI  PCC5.10.0NashMulti |
| EQUIPMENT | EQUPIO01 | TRIOSOFT, INC |
| EQUIPMENT | EQUPIPJK | Skipjack  |
| EQUIPMENT | EQUPIREE | BRINK POS Rest RC EC |
| EQUIPMENT | EQUPISO1 | xpient Solutions |
| EQUIPMENT | EQUPIWLD | Llewellyn worldwide |
| EQUIPMENT | EQUPJAVO | Dejavoo V-5 |
| EQUIPMENT | EQUPAEPE | USAePAY Ecommerce |
| EQUIPMENT | EQUPCBIC | Cubic GTWY |
| EQUIPMENT | EQUPCH50 | InnsoftCheckinnv5.0 |
| EQUIPMENT | EQUPCUK1 | Credit Call Co UK(Parking Garage) |
| EQUIPMENT | EQUPDLN4 | CREDITLINE V3.00.04 |
| EQUIPMENT | EQUPFD10 | FD-100 TI |
| EQUIPMENT | EQUPGAWR | ChargeAnywhere RC GTWY |
| EQUIPMENT | EQUPGYRC | Tempus Gateway-RC |
| EQUIPMENT | EQUPINV3 | CheckInn v3.0 |
| EQUIPMENT | EQUPJSAW | JIGSAW |
| EQUIPMENT | EQUPL400 | AVF Consulting ChargeLogic v4.00 |
| EQUIPMENT | EQUPBER1 | BPD EC |
| EQUIPMENT | EQUP1T01 | INTEGRIS, INC |
| EQUIPMENT | EQUPAL01 | SMALL BUSINESS COMPUTERS |
| EQUIPMENT | EQUPCBKF | DLHost(LL) with Full Tid Purc/Com card |
| EQUIPMENT | EQUPFO01 | VERIFONE |
| EQUIPMENT | EQUPHDC1 | PTI-Nurit 2080 HDC |
| EQUIPMENT | EQUPICGT | EZIC Inc Gateway |
| EQUIPMENT | EQUPGNST | BRIDGEPAY NEW SOL GTWY |
| EQUIPMENT | EQUPINP1 | PRINCETON GATEWAY (Mo/To) |
| EQUIPMENT | EQUPKTGT | ROCKETGATE GATEWAY |
| EQUIPMENT | EQUP0005 | hfhgf |
| EQUIPMENT | EQUP00GG | FD400GT GPRS |
| EQUIPMENT | EQUP0555 | fdgdgfd |
| EQUIPMENT | EQUP0GTC | FD400GT CDMA |
| EQUIPMENT | EQUP100C | AurusWhizPaySnglStlGTWY |
| EQUIPMENT | EQUP1015 | MILLENNIUM MEEVO DW RC |
| EQUIPMENT | EQUP1016 | Western Register RC |
| EQUIPMENT | EQUP101B | HJRS HLDGS GTWY DW RC |
| EQUIPMENT | EQUP101C | HJRS HLDGS GTWY EC DW RC |
| EQUIPMENT | EQUP101R | IQMS RC DW |
| EQUIPMENT | EQUP1029 | Novaux RC DW |
| EQUIPMENT | EQUP102J | PaxTech BroadPOS RC Sing |
| EQUIPMENT | EQUP102R | 911Soft CreditLine 4.1.3 |
| EQUIPMENT | EQUP102S | Visionworks RC DW |
| EQUIPMENT | EQUP102Y | SyntecBusSysSalonSftwRC |
| EQUIPMENT | EQUP1037 | Adidas NSH Tender Retail |
| EQUIPMENT | EQUP103D | VFI PAYwareConnect RC |
| EQUIPMENT | EQUP103M | Shopko ACI RCS v5.1 |
| EQUIPMENT | EQUP1041 | ARBELSOFT v7.8 RC DW |
| EQUIPMENT | EQUP1045 | FTD CCAS EC RC DW |
| EQUIPMENT | EQUP104P | Darden Dash POS |
| EQUIPMENT | EQUP104V | AJB BestBuy ISO8583 RTL |
| EQUIPMENT | EQUP1057 | Chargelogic DW RC |
| EQUIPMENT | EQUP1058 | TRANSX DW RC |
| EQUIPMENT | EQUP108N | AllMar10 |
| EQUIPMENT | EQUP109G | SigmaPaymentsGTW |
| EQUIPMENT | EQUP100S | EZ Retail v1.53.05 RC DW |
| EQUIPMENT | EQUP1010 | AAA Carolinas RC |
| EQUIPMENT | EQUP1020 | DUN M RT V 2.08 RC TA DW |
| EQUIPMENT | EQUP1021 | EPICOR 6.4 NORTH ISO8583 |
| EQUIPMENT | EQUP1023 | POSLynx220 v2.13 EC DW |
| EQUIPMENT | EQUP1024 | POSLynx220 v2.13 DW |
| EQUIPMENT | EQUP1026 | POSBank Multi RC |
| EQUIPMENT | EQUP1028 | DRAKE SOFTWARE RC DW |
| EQUIPMENT | EQUP102Q | I Love Velvet RC v1.0 |
| EQUIPMENT | EQUP102W | TenderRet MCon v5.0 RC |
| EQUIPMENT | EQUP103L | Ross-AJB V1 |
| EQUIPMENT | EQUP103N | TranzGate RC GWY EC DW |
| EQUIPMENT | EQUP103S | ToysRUs AJB TA |
| EQUIPMENT | EQUP1044 | Epicor RC no VAR Sheet |
| EQUIPMENT | EQUP1049 | BART |
| EQUIPMENT | EQUP104W | AJB BestBuy ISO8583 ECOM |
| EQUIPMENT | EQUP104Y | Costa Cruise RC EC V.1.0 |
| EQUIPMENT | EQUP1059 | Softheon EC GTW |
| EQUIPMENT | EQUP105G | Ingenico ISC250 Pin Pad |
| EQUIPMENT | EQUP105J | Clover Mini |
| EQUIPMENT | EQUP105X | POSLynx220TransNet2.14DW |
| EQUIPMENT | EQUP1061 | AJB Fin Feather Fur |
| EQUIPMENT | EQUP1065 | BuypassFeb28 |
| EQUIPMENT | EQUP106G | TENERUM GTW RT RC EC |
| EQUIPMENT | EQUP107F | The Walt Disney Co |
| EQUIPMENT | EQUP107I | CardKnox PEv1.0 RC |
| EQUIPMENT | EQUP108D | SICOM SLSeries v2.611 DW |
| EQUIPMENT | EQUP108P | Nash01Mar10 |
| EQUIPMENT | EQUP108V | ACI RCS 5.1 |
| EQUIPMENT | EQUP1096 | Vail RC EC POS |
| EQUIPMENT | EQUP1098 | Cabelas RC GTW |
| EQUIPMENT | EQUP10A9 | Deep13mar1556 |
| EQUIPMENT | EQUP10AW | Nash1Mar14 |
| EQUIPMENT | EQUP10C3 | Nash5Mar17 |
| EQUIPMENT | EQUP10E2 | CardnetMar20 |
| EQUIPMENT | EQUP10EK | Nash4Mar21 |
| EQUIPMENT | EQUP10EO | CompassMar21 |
| EQUIPMENT | EQUP10Z3 | HIGH RDS GTWY EC |
| EQUIPMENT | EQUP110F | B2B SOFT GTW RTL DW RC |
| EQUIPMENT | EQUP110O | Guitar Center RC GTW |
| EQUIPMENT | EQUP1111 | Product set up |
| EQUIPMENT | EQUP111E | IBM GATEWAY GTW RC |
| EQUIPMENT | EQUP1124 | Monetra 4.0.0 DW |
| EQUIPMENT | EQUP1125 | Monetra 4.0.0 DW EC |
| EQUIPMENT | EQUP112C | NAB GTWY EC DW RC |
| EQUIPMENT | EQUP114G | GreenLight GTW DW EC RC |
| EQUIPMENT | EQUP114V | ACI RCS GTW RC SS |
| EQUIPMENT | EQUP1198 | Shubert Star RC |
| EQUIPMENT | EQUP102I | Karz v2.0.4 |
| EQUIPMENT | EQUP102Z | Tempus Mobile Card Reader |
| EQUIPMENT | EQUP103Z | EPCORRTLSTR V2.5.11 |
| EQUIPMENT | EQUP1043 | ABC ACI RCS 5.1 |
| EQUIPMENT | EQUP104H | Memorial Herman RC EC |
| EQUIPMENT | EQUP104J | Memorial Herman RC |
| EQUIPMENT | EQUP104U | AJB BestBuy ISO8583 HDC |
| EQUIPMENT | EQUP1051 | PARKMOBILEnashSingGTW DW |
| EQUIPMENT | EQUP1054 | Touchnet Ucomm6.5 RC DW |
| EQUIPMENT | EQUP105E | SMITHCO FBPRTRST1 RCPTDW |
| EQUIPMENT | EQUP105L | SMITHCO FBPRTRST1 RCPTDW |
| EQUIPMENT | EQUP105T | SMITHCO FBPRTRST1 RCPTDW |
| EQUIPMENT | EQUP105Z | Nash3Feb0228 |
| EQUIPMENT | EQUP1078 | Advanced Merchant Grp |
| EQUIPMENT | EQUP107Q | NRT Technologies Kiosk |
| EQUIPMENT | EQUP108M | BuypassMar10 |
| EQUIPMENT | EQUP108W | TrustComm RC |
| EQUIPMENT | EQUP108Z | GOODER DW RC MER |
| EQUIPMENT | EQUP1092 | Tillster v1.0 EC RC |
| EQUIPMENT | EQUP1095 | Vail RC POS |
| EQUIPMENT | EQUP109B | GSI eBay MO RC |
| EQUIPMENT | EQUP109V | Nash4Mar13 |
| EQUIPMENT | EQUP109X | Nash6Mar13 |
| EQUIPMENT | EQUP109Y | CardnetMar13 |
| EQUIPMENT | EQUP10B0 | Nash5Mar14 |
| EQUIPMENT | EQUP10B2 | CardnetMar14 |
| EQUIPMENT | EQUP10B3 | CompassMar14 |
| EQUIPMENT | EQUP10BZ | Nash1Mar17 |
| EQUIPMENT | EQUP10CR | Nash4Mar18 |
| EQUIPMENT | EQUP10CS | Nash5Mar18 |
| EQUIPMENT | EQUP10DD | Nash4Mar19 |
| EQUIPMENT | EQUP10DE | Nash5Mar19 |
| EQUIPMENT | EQUP10DJ | BuypassMar19 |
| EQUIPMENT | EQUP10E3 | CompassMar20 |
| EQUIPMENT | EQUP10E6 | Nash2Mar20 |
| EQUIPMENT | EQUP10E7 | Nash3Mar20 |
| EQUIPMENT | EQUP10EG | Nash2Mar21 |
| EQUIPMENT | EQUP10FA | Nash1Mar24 |
| EQUIPMENT | EQUP10FC | Nash3Mar24 |
| EQUIPMENT | EQUP10FF | Nash6Mar24 |
| EQUIPMENT | EQUP10FJ | AllMar24 |
| EQUIPMENT | EQUP10IG | Nash2Apr21 |
| EQUIPMENT | EQUP10IT | Compass01Apr21 |
| EQUIPMENT | EQUP10OA | CarMar11 |
| EQUIPMENT | EQUP10YV | KeyCorp K23 PCI 2 |
| EQUIPMENT | EQUP10Z1 | PayPros PPI VX820 |
| EQUIPMENT | EQUP10Z2 | DOW Chemicals EC |
| EQUIPMENT | EQUP10Z7 | AJB Express Mx915 |
| EQUIPMENT | EQUP1109 | TelefonicaGW |
| EQUIPMENT | EQUP110A | Dataline GTW |
| EQUIPMENT | EQUP110G | MASTERCARD GTW EC DW RC |
| EQUIPMENT | EQUP110P | Guitar Center RC EC |
| EQUIPMENT | EQUP110S | Cole Haan-AJB-V1 |
| EQUIPMENT | EQUP1115 | Ingenico RC v1.0.0 |
| EQUIPMENT | EQUP1118 | NEXTEP SYSTEMS RTL DW RC |
| EQUIPMENT | EQUP111D | VeriFone SCA4 RC SRS |
| EQUIPMENT | EQUP111H | LOCOMOBI RC DW |
| EQUIPMENT | EQUP111K | CSC-PTC RC |
| EQUIPMENT | EQUP1122 | Monetra 4.1.0 DW |
| EQUIPMENT | EQUP1123 | Monetra 4.1.0 DW EC |
| EQUIPMENT | EQUP1128 | GoVolution RC GTW EC SMS |
| EQUIPMENT | EQUP112M | PAYM01 v1.0 RC DW GTW |
| EQUIPMENT | EQUP1130 | Darden DASH POS EDC Dial |
| EQUIPMENT | EQUP1134 | ExadigmGrapeSecPy13.12DW |
| EQUIPMENT | EQUP113L | ACI RCS 5.1 MS RC EC |
| EQUIPMENT | EQUP113P | GSO Crimson |
| EQUIPMENT | EQUP113R | AJB FIPAY EPS v2.2 MS RC |
| EQUIPMENT | EQUP114E | PAX TECH BROADPOSv1.0 DW |
| EQUIPMENT | EQUP115A | GK TransAction v7.5.1 |
| EQUIPMENT | EQUP115E | iCheckGtwy DW SRS RC |
| EQUIPMENT | EQUP115F | iCheckGtwy DW EC SRS RC |
| EQUIPMENT | EQUP115Z | DTCP NETePay 5.1 DW RC |
| EQUIPMENT | EQUP1169 | GreenLight GTW RC DW EC  |
| EQUIPMENT | EQUP116H | Instamed Direct MOTO |
| EQUIPMENT | EQUP116I | SK REGISTER v1.0 DW RC |
| EQUIPMENT | EQUP116K | MultiService Tech Sol EC |
| EQUIPMENT | EQUP116L | SK REGISTER v1.0 RC DW |
| EQUIPMENT | EQUP1170 | AMDOCSAMSS TAONLYRCDW |
| EQUIPMENT | EQUP117K | PAYON AG GTW EC DW RC |
| EQUIPMENT | EQUP117L | PAYON AG GTW DW RC |
| EQUIPMENT | EQUP119A | TriPayments EC DW SRS RC |
| EQUIPMENT | EQUP119B | ROAM DATA GTW EC RC |
| EQUIPMENT | EQUP11AD | CYBRSRC TK GTW EC RC SRS |
| EQUIPMENT | EQUP11AJ | Overland West RC SRS |
| EQUIPMENT | EQUP11AM | BF PayConexPlus GtwRcEc |
| EQUIPMENT | EQUP11B6 | PAYON PWORKS RC SRS |
| EQUIPMENT | EQUP11B8 | Forever 21 |
| EQUIPMENT | EQUP11BB | VistaPaymentSrvrV4.5DW |
| EQUIPMENT | EQUP11BE | Apriva Pay Plus IOS 4.x |
| EQUIPMENT | EQUP11BK | BTIPOS 9.7 RC SRS |
| EQUIPMENT | EQUP11C6 | MOTIONSOFT GTWY EC SRS |
| EQUIPMENT | EQUP11CG | Paymetric GTW |
| EQUIPMENT | EQUP11CQ | MHC ECOMM V1 RC SRS |
| EQUIPMENT | EQUP11CS | TST DW |
| EQUIPMENT | EQUP11CW | gg_23 |
| EQUIPMENT | EQUP11QE | Mexico ICT220G DW |
| EQUIPMENT | EQUP11SB | Avis Budget |
| EQUIPMENT | EQUP11SR | Ingenico iCT220 Terminal |
| EQUIPMENT | EQUP11ST | CONNECTX GTW RCSRS EC SS |
| EQUIPMENT | EQUP11SW | CONNECTX GTW RCSRS MS |
| EQUIPMENT | EQUP11TL | CURO FIN RC SRS EC |
| EQUIPMENT | EQUP11TZ | Mexico PayPoint GT MOTO |
| EQUIPMENT | EQUP11U7 | Fairytale Brownies |
| EQUIPMENT | EQUP11WC | ECRS Catapult 5.4 RC SRS |
| EQUIPMENT | EQUP11WE | USAePay GTW RC EC MS |
| EQUIPMENT | EQUP11XK | MSTS BBY TOKEN RC SRS EC |
| EQUIPMENT | EQUP11XM | BEST BUY TA GETBIN RC |
| EQUIPMENT | EQUP11ZK | Amadeus APP GTW RC |
| EQUIPMENT | EQUP11ZO | IBM GATEWAY GTW EC |
| EQUIPMENT | EQUP11ZV | TMobile RC |
| EQUIPMENT | EQUP126Y | ConduentOpsBank3.0.0.1EC |
| EQUIPMENT | EQUP126Z | ConduentOpsBank3.0.0.1 |
| EQUIPMENT | EQUP127C | MEXICO LANE5000 DW |
| EQUIPMENT | EQUP127U | WF TSYS |
| EQUIPMENT | EQUP1287 | CBKC RC EC |
| EQUIPMENT | EQUP128I | Point SCA 5.00.x RCSRSSS |
| EQUIPMENT | EQUP1294 | VeriFone V200c Plus Terminal |
| EQUIPMENT | EQUP129L | TranSend RevChip2.5SRSms |
| EQUIPMENT | EQUP129N | PLXIS GTW RC EC MS |
| EQUIPMENT | EQUP12A0 | FIPAY EPS v2.3 EC |
| EQUIPMENT | EQUP12AA | CR-VAR-0204 |
| EQUIPMENT | EQUP12AH | KCX v1.0.18 EC SRS RC SS |
| EQUIPMENT | EQUP12KP | OPW FSC5000 v1 RC SRS |
| EQUIPMENT | EQUP12LD | FTD CCAPI v.3.0.1RCSRSEC |
| EQUIPMENT | EQUP12LF | Billhighway NV RC EC |
| EQUIPMENT | EQUP12NL | EQUINOX 1.0 RC MS |
| EQUIPMENT | EQUP12NN | N5 NEXGO_NVL N08.011.008 |
| EQUIPMENT | EQUP12OI | CMA CGM RC ECOM |
| EQUIPMENT | EQUP12OW | Payrix GW RcSrsMs |
| EQUIPMENT | EQUP12OZ | Blue Parasol DW RC EC |
| EQUIPMENT | EQUP12P4 | AlacriGWOrbipayV8.5RCSRS |
| EQUIPMENT | EQUP12Q7 | AxiaMed GTW RC SRS |
| EQUIPMENT | EQUP12QM | PG GTW RC MOTO DW |
| EQUIPMENT | EQUP12RK | Worldnet GTW TCP IP |
| EQUIPMENT | EQUP12S3 | Monetra RMA014 RC DW GTW |
| EQUIPMENT | EQUP12UA | Viper 8.02.00 RC VPN |
| EQUIPMENT | EQUP12W8 | RESORTCOM RCECOM HDC GTW |
| EQUIPMENT | EQUP12X5 | PRYSYSM Rapid Connect |
| EQUIPMENT | EQUP105U | SMITHCO FBPRTRST RCPTDW |
| EQUIPMENT | EQUP105Y | CYBERSOURCE ICS2 GTW |
| EQUIPMENT | EQUP107W | ProntoServicio DW RC |
| EQUIPMENT | EQUP108T | NCRAlohaEDCV14.1 |
| EQUIPMENT | EQUP109C | PHOENIXMN GTW DW RC |
| EQUIPMENT | EQUP109E | MerchantLinkMPGEMV |
| EQUIPMENT | EQUP109S | Nash1Mar13 |
| EQUIPMENT | EQUP109T | Nash2Mar13 |
| EQUIPMENT | EQUP10B4 | BuypassMar14 |
| EQUIPMENT | EQUP10EL | Nash5Mar21 |
| EQUIPMENT | EQUP10J5 | CompassApr22 |
| EQUIPMENT | EQUP10XY | voltage_VAR1 |
| EQUIPMENT | EQUP10Z0 | Payment Processing ECOM MSR & EMV |
| EQUIPMENT | EQUP110V | APTOS SRS |
| EQUIPMENT | EQUP110W | PayPal |
| EQUIPMENT | EQUP1119 | OmniTkt BUCCS 1.0 RC EC |
| EQUIPMENT | EQUP111F | IBM GATEWAY GTW RC EC |
| EQUIPMENT | EQUP111P | Staples RC |
| EQUIPMENT | EQUP111U | SemnoxParTablet3.0.0dwRC |
| EQUIPMENT | EQUP112B | NAB GTWY DW RC |
| EQUIPMENT | EQUP112Y | Mrch Prtnrs GTW RC EC |
| EQUIPMENT | EQUP1135 | Express |
| EQUIPMENT | EQUP1136 | Express EC |
| EQUIPMENT | EQUP1143 | Scoria 1.25.00 RC |
| EQUIPMENT | EQUP114J | MyCheck GW RC DW EC SS |
| EQUIPMENT | EQUP114P | NCR CP GW RC SS |
| EQUIPMENT | EQUP1154 | Instamed PPS RTL |
| EQUIPMENT | EQUP1155 | Instamed PPS MOTO |
| EQUIPMENT | EQUP115R | PAXBROADPOSPAY1.0SMSDWRC |
| EQUIPMENT | EQUP116G | PhoenixMgNetwk GTW DW EC |
| EQUIPMENT | EQUP116J | MultiService Tech Sol |
| EQUIPMENT | EQUP116Q | Staples Copy Print RC |
| EQUIPMENT | EQUP116X | IT Retail RC DW VX |
| EQUIPMENT | EQUP117B | TenderRet v5.0 RC EC SRS |
| EQUIPMENT | EQUP117N | PAYPLAZA GTW DW RC |
| EQUIPMENT | EQUP117S | Toshiba ACE 7R5 DW RC |
| EQUIPMENT | EQUP117T | Cybersrce GTW RM3 |
| EQUIPMENT | EQUP117U | PelotonTech GTW SMS EC |
| EQUIPMENT | EQUP1197 | MidExSlipstream4.5 SRSrc |
| EQUIPMENT | EQUP11A6 | MSTS MultiSVC GTW EcDW |
| EQUIPMENT | EQUP11A7 | POLARIS v1.0 GTW RC SRS |
| EQUIPMENT | EQUP11AI | ADVAM GTW EC RC SRS |
| EQUIPMENT | EQUP11AO | PaySpan GTW EC RC SRS |
| EQUIPMENT | EQUP11AU | ACI Pos Host SS GTW |
| EQUIPMENT | EQUP11AV | ACI Pos Host MS GTW |
| EQUIPMENT | EQUP11B2 | 3C Payment GTW EC |
| EQUIPMENT | EQUP11B3 | Affinipay GTW SMS DW EC |
| EQUIPMENT | EQUP11BM | Thermeon Cars GTW |
| EQUIPMENT | EQUP11BU | Upfront POS RC SRS |
| EQUIPMENT | EQUP11C1 | SPARROWONEGTW EC RC SRS |
| EQUIPMENT | EQUP11C9 | EsteeTenderRtl Mx915 SRS |
| EQUIPMENT | EQUP11CE | ATMC Milsoft DW |
| EQUIPMENT | EQUP11CF | WFF National Bank EC |
| EQUIPMENT | EQUP11FR | fd pos_var |
| EQUIPMENT | EQUP11FS | FDPOS_0226 |
| EQUIPMENT | EQUP11PR | Canadian IPP320 IntPinPad |
| EQUIPMENT | EQUP11Q5 | BanfieldPetHospital CMPS |
| EQUIPMENT | EQUP11QB | CAC IPG GTW EC |
| EQUIPMENT | EQUP11QO | FD OMAHA RC SRS |
| EQUIPMENT | EQUP11R9 | Trust Commerce GTW RC |
| EQUIPMENT | EQUP11TT | BridgePay GTW RC EC |
| EQUIPMENT | EQUP11U3 | Mexico Vx675 DW |
| EQUIPMENT | EQUP11VJ | DISH AUTH 1.0 RC EC |
| EQUIPMENT | EQUP11VV | Thermeon Cars FDC GTW EC |
| EQUIPMENT | EQUP11XI | CITI GETTKN RETAIL RC |
| EQUIPMENT | EQUP11Y5 | PRISMPAY GTW RC SRS |
| EQUIPMENT | EQUP11YB | VP Term RCSRS |
| EQUIPMENT | EQUP11YM | MenuPad v2.1 RC SRS |
| EQUIPMENT | EQUP11ZG | STPSecureTable US0100 DW |
| EQUIPMENT | EQUP1220 | CR1020046_VAR |
| EQUIPMENT | EQUP122V | USeDIRECT GTW RC SRS EC |
| EQUIPMENT | EQUP122W | Carnival Cruise Lines EC |
| EQUIPMENT | EQUP1232 | CONDUENT GTW |
| EQUIPMENT | EQUP1234 | qwerty |
| EQUIPMENT | EQUP1236 | 123456 |
| EQUIPMENT | EQUP123G | CRDCallReseller EC RC SS |
| EQUIPMENT | EQUP123R | Wells Fargo Bank SDK |
| EQUIPMENT | EQUP123T | Hertz GTW |
| EQUIPMENT | EQUP1273 | LANSHLD GTW RC SRS EC |
| EQUIPMENT | EQUP127H | WF MPLS RC EC |
| EQUIPMENT | EQUP127Q | WF ISO8583 MPLS |
| EQUIPMENT | EQUP127S | WF ISO8583 DW |
| EQUIPMENT | EQUP127V | WF Compass |
| EQUIPMENT | EQUP128E | OnePay GTW SRS CP RC |
| EQUIPMENT | EQUP128N | Bill 1st GTWY DS |
| EQUIPMENT | EQUP128Q | WFPG Retail CP GTWY |
| EQUIPMENT | EQUP129J | PAX Prolin 1.0 RC |
| EQUIPMENT | EQUP129K | TranSend RevChip2.5SRSss |
| EQUIPMENT | EQUP129M | PLXIS GTW RC EC SS |
| EQUIPMENT | EQUP129R | Seamless GTW HdcSrsMsEc |
| EQUIPMENT | EQUP129Y | SETECS GTW RC SRS EC |
| EQUIPMENT | EQUP12A2 | FIPAY EPS v2.3 DW EC |
| EQUIPMENT | EQUP12A6 | 4DPayments v16 RcSrsSsEc |
| EQUIPMENT | EQUP12AC | VerisoftPOSv1 ss RC SRS |
| EQUIPMENT | EQUP12AF | AMT v1.4 GTW SRS RC MS |
| EQUIPMENT | EQUP12AO | AptosGTWESDM3RCSRS |
| EQUIPMENT | EQUP12BF | VeriFone SCA Engage FDRC |
| EQUIPMENT | EQUP12BL | TRANSACTIS GTW SRS RC SS |
| EQUIPMENT | EQUP12BP | FAC PowerTranz CP GTW |
| EQUIPMENT | EQUP12CE | Flight Center DM SS |
| EQUIPMENT | EQUP12CO | SINOWEST EON v1.1 RC SRS |
| EQUIPMENT | EQUP12CU | NCR EPS v2.8 ATL105 SRS |
| EQUIPMENT | EQUP12K1 | Mexico Engage V240M WiFi |
| EQUIPMENT | EQUP12K6 | Arts People RC |
| EQUIPMENT | EQUP12KK | Fluid Pay GW SRS SS RET |
| EQUIPMENT | EQUP12KL | GK TransAction+7.6RC MS |
| EQUIPMENT | EQUP12KX | FORTE GTW ISO EC SS |
| EQUIPMENT | EQUP12KY | FORTE GTW ISO SS |
| EQUIPMENT | EQUP12LB | Phillips Med MoTo RM3 |
| EQUIPMENT | EQUP12M2 | CR1158407 0812 |
| EQUIPMENT | EQUP12MA | Khamu Sapphire6.1 SRS TC |
| EQUIPMENT | EQUP12MB | CRQ000000015067_Var |
| EQUIPMENT | EQUP12MH | WU APOLLO RC GW EC |
| EQUIPMENT | EQUP12O0 | FATZEBRA GTW RC SRS |
| EQUIPMENT | EQUP12OB | 4D Payments v16 SRS SS |
| EQUIPMENT | EQUP12OM | ChargeLogic4.0 RcSrsMs |
| EQUIPMENT | EQUP12OP | ECRS Catapult 5.5 RC SRS |
| EQUIPMENT | EQUP12OR | RC PSN GTW CC 1.2.0 ECOM |
| EQUIPMENT | EQUP12P1 | Point SCA 4.0 DWRCSRS |
| EQUIPMENT | EQUP12PD | Trovato v8 RC DW SRS |
| EQUIPMENT | EQUP12PP | ADVMOBILEPYMT SRS EC RC |
| EQUIPMENT | EQUP12PS | FD BAMS Canada |
| EQUIPMENT | EQUP12PV | M400 IntegratedPinpad CA |
| EQUIPMENT | EQUP12PX | TEMPUSCANECGTW |
| EQUIPMENT | EQUP12QL | PecanSolutionsV2.0 RC EC |
| EQUIPMENT | EQUP12QN | PAYMENTWALL SRS EC RC |
| EQUIPMENT | EQUP12QR | ACI RCS v5.2 GTW IP MS |
| EQUIPMENT | EQUP12R8 | SIRPA048SOUNDPMTPAXCOMON |
| EQUIPMENT | EQUP12R9 | THD Ingenico ISC250 CTLS |
| EQUIPMENT | EQUP12RE | Auth.net Reseller/EPP EC |
| EQUIPMENT | EQUP12RL | Worldnet GTW TCP IP EC |
| EQUIPMENT | EQUP12RX | Aptos Pymt 2017.3 RC SRS |
| EQUIPMENT | EQUP12RZ | Dataline GTW Compass |
| EQUIPMENT | EQUP12S1 | EHI IBM MX915 RC CR GTW |
| EQUIPMENT | EQUP12SA | AURUS GTW RC VPN SS |
| EQUIPMENT | EQUP12SU | YahooAAbaco RCSRS EC GTW |
| EQUIPMENT | EQUP12SV | AlaGWOrbipV8.5SSRCSRSEC |
| EQUIPMENT | EQUP12SW | AlaGWOrbipayV8.5SSRCSRS |
| EQUIPMENT | EQUP12T2 | IDTech Trio-CAGE-RCDWSRS |
| EQUIPMENT | EQUP12TE | BroadPOS v1.02.02E GTW |
| EQUIPMENT | EQUP12TT | EIGEN MiraServ PTS MOTO |
| EQUIPMENT | EQUP12U8 | Acculynk GTW RC EC MPLS |
| EQUIPMENT | EQUP12UK | crq11171 |
| EQUIPMENT | EQUP12UQ | SecureTrading RC Omaha |
| EQUIPMENT | EQUP12UR | OLO GTW EC RC SRS |
| EQUIPMENT | EQUP12UY | Apriva BroadPOS GTW |
| EQUIPMENT | EQUP12WA | One Inc COMPASS EC |
| EQUIPMENT | EQUP12WR | SchFCSV12 RC SRS |
| EQUIPMENT | EQUP12WV | Paypoint GTW RC |
| EQUIPMENT | EQUP12XJ | 0517_VAR |
| EQUIPMENT | EQUP12XQ | Eigen MiraServ 6.17+ Ret |
| EQUIPMENT | EQUP12XZ | EpicPay vs 1.0 RC PFAC GTW |
| EQUIPMENT | EQUP10J1 | CardnetApr22 |
| EQUIPMENT | EQUP115L | PAXBROADPOSPAY1.0DWRCSMS |
| EQUIPMENT | EQUP116Z | EHG DENTXCHANGE DW RC |
| EQUIPMENT | EQUP11BG | Novadine v9.0 DW |
| EQUIPMENT | EQUP11YV | PSIGate2.5GW EC RCSRS SS |
| EQUIPMENT | EQUP11YY | Yapstone RC SRS |
| EQUIPMENT | EQUP123D | ACCULYNK GTWV2.0 RCSRSEC |
| EQUIPMENT | EQUP1274 | Mexico Engage V240M DW |
| EQUIPMENT | EQUP127E | WF VPN RC |
| EQUIPMENT | EQUP127O | WF ISO8583 VPN |
| EQUIPMENT | EQUP128C | ADVAM GTW SRS RC |
| EQUIPMENT | EQUP12B7 | Breadcrumbv1GTWssRCSRSEC |
| EQUIPMENT | EQUP12BE | TDS Telecom |
| EQUIPMENT | EQUP12KC | aiCorp RC GW DW MS |
| EQUIPMENT | EQUP12KG | CR1144521_Var |
| EQUIPMENT | EQUP12KJ | Fluid Pay GW SRS SS EC |
| EQUIPMENT | EQUP12LU | MasterCard RC GTW |
| EQUIPMENT | EQUP12M6 | PrismPay GTW TermCapt RC |
| EQUIPMENT | EQUP12M8 | ViaTouch GTW RC SRS EC |
| EQUIPMENT | EQUP12N4 | Freedom Pay Canada |
| EQUIPMENT | EQUP12NB | 4DPayments v16 SrsMs |
| EQUIPMENT | EQUP12NC | 4DPayments v16 SrsMsEc |
| EQUIPMENT | EQUP12NM | Gilbarco ATL105v1.04 IP |
| EQUIPMENT | EQUP12PH | CUBIC GTW RC |
| EQUIPMENT | EQUP12Q2 | DOVER v2.4 ATL105 VPN |
| EQUIPMENT | EQUP12QK | MEXICO LINK2500 3G |
| EQUIPMENT | EQUP12RC | MiuraM010 PremiumPal 2.1 |
| EQUIPMENT | EQUP12SZ | FreedomPay GTW SS |
| EQUIPMENT | EQUP12T3 | IDTech Duo-CAGE-RCDWSRS |
| EQUIPMENT | EQUP12TR | Pay O Matic RC |
| EQUIPMENT | EQUP12UE | Pineapple GTW RC MS |
| EQUIPMENT | EQUP12W5 | Blue Parasol SRS RC EC |
| EQUIPMENT | EQUP12X1 | Ingenico MOVE2500 |
| EQUIPMENT | EQUP12X2 | Ingenico Move5000 pp  |
| EQUIPMENT | EQUP12XE | CYBRSRC TK GW RC |
| EQUIPMENT | EQUP12XN | Gravity Direct GTW RC |
| EQUIPMENT | EQUP11CB | Mexico IPG GTW EC |
| EQUIPMENT | EQUP12A4 | Pay Manager |
| EQUIPMENT | EQUP12NZ | FATZEBRA GTW RC SRS EC |
| EQUIPMENT | EQUP1047 | JPMC Virtual EC RC DW |
| EQUIPMENT | EQUP106Q | FreedomPay GTW multi |
| EQUIPMENT | EQUP10C5 | cardnetMar17 |
| EQUIPMENT | EQUP10EH | Nash3Mar21 |
| EQUIPMENT | EQUP116T | CRDCallCdEase GTW SMS |
| EQUIPMENT | EQUP11A1 | FEXCO OpenConnect GwDwMs |
| EQUIPMENT | EQUP11WD | USAePay GTW RC MS |
| EQUIPMENT | EQUP126H | DISH AUTH 1.0 RCSRS MOTO |
| EQUIPMENT | EQUP12KZ | FORTE GTW ISO EC MS |
| EQUIPMENT | EQUP113C | CastleTechPrjMerv1.0RCDW |
| EQUIPMENT | EQUP11Q9 | Delego V2.5.4 RC SRS |
| EQUIPMENT | EQUP123O | E PROC NET GTW OTC RC EC |
| EQUIPMENT | EQUP128V | ILToll ATS RC PTS EC |
| EQUIPMENT | EQUP12AG | BNYMELLON GTW SRS RC |
| EQUIPMENT | EQUP12AK | BISGLOBAL GTWECSRSRCMS |
| EQUIPMENT | EQUP12AL | Cayman GTW |
| EQUIPMENT | EQUP12BU | CSIBIP1.1 GTW RC SRS EC |
| EQUIPMENT | EQUP12GH | SamplePC_9762 |
| EQUIPMENT | EQUP12LL | SI DCAP Chargelogic |
| EQUIPMENT | EQUP12LP | CR1098308_Var |
| EQUIPMENT | EQUP12NQ | CARDCONNECTGTWY MSTRSES |
| EQUIPMENT | EQUP12P8 | NAVTRE GTW SWOOP RC USD |
| EQUIPMENT | EQUP12Q5 | BluePay CA RC EC GTW |
| EQUIPMENT | EQUP12Q6 | AxiaMed GTW RC SRS EC |
| EQUIPMENT | EQUP12QE | Paycertify GTW MS |
| EQUIPMENT | EQUP12T4 | HOLLAND NASH ISO8583 EC  |
| EQUIPMENT | EQUP12TQ | SIRBL006AlacritiPAX |
| EQUIPMENT | EQUP12WX | One Inc RC GetPan |
| EQUIPMENT | EQUP119E | JIFFYLUBE DW SRS RC |
| EQUIPMENT | EQUP11FY | Var_Regression_QA |
| EQUIPMENT | EQUP12PY | Var_CRQ000000133358&CRQ000000133833 |
| EQUIPMENT | EQUP12TY | Currencypay GTW RC EC |
| EQUIPMENT | EQUP12X4 | CellfiePayment SRS EC RC |
| EQUIPMENT | EQUP12XY | Monetra RMA017 RC DW GTW |
| EQUIPMENT | EQUP10C4 | Nash6Mar17 |
| EQUIPMENT | EQUPTNDS | CAPTAIN D'S |
| EQUIPMENT | EQUPVB63 | -VSO001 |
| EQUIPMENT | EQUPVB58 | -VSN001 |
| EQUIPMENT | EQUPVERL | Verifone P250 Printer |
| EQUIPMENT | EQUPS8 | Hypercom S8 Secure Pin Pad |
| EQUIPMENT | EQUPISDS | Integrated Systems Development (ISD) Software |
| EQUIPMENT | EQUPSTDB | PC Batch DOS Software |
| EQUIPMENT | EQUP490N | 490N |
| EQUIPMENT | EQUPCP4 | CP4 Printer |
| EQUIPMENT | EQUPP700 | Verifone P700 Printer |
| EQUIPMENT | EQUPC200 | Citizen 200 Printer |
| EQUIPMENT | EQUPHNDB | Verifone Handset |
| EQUIPMENT | EQUPWDGM | WDGM |
| EQUIPMENT | EQUP5991 | NCR5991 Signature Capture |
| EQUIPMENT | EQUPSSFB | Stand Flat Bottom |
| EQUIPMENT | EQUPHOLD | HOLD (Unknown equip. type) |
| EQUIPMENT | EQUPAMEX | UNKNOWN - AMEX |
| EQUIPMENT | EQUPIBMC | UNKNOWN - IBMC |
| EQUIPMENT | EQUPOMNI | UNKNOWN - OMNI |
| EQUIPMENT | EQUPWDGE | UNKNOWN - WDGE |
| EQUIPMENT | EQUPZON | UNKNOWN - ZON |
| EQUIPMENT | EQUPOMRP | Omron Printer |
| EQUIPMENT | EQUPP102 | Verifone 102 Pin Pad |
| EQUIPMENT | EQUP3535 | Citizen 3535 Printer |
| EQUIPMENT | EQUPPPC7 | Power Packs CT7 |
| EQUIPMENT | EQUPPPP7 | Power Packs CP7 |
| EQUIPMENT | EQUPCB15 | Cable P150 |
| EQUIPMENT | EQUPCB10 | Cable P101 |
| EQUIPMENT | EQUPPMAR | Arms T7P (T1E) |
| EQUIPMENT | EQUPCVPV | Paper Cover Verl |
| EQUIPMENT | EQUPP350 | Verifone PrintPack 350 |
| EQUIPMENT | EQUPSGST | Guest*Plus Software |
| EQUIPMENT | EQUPOMOD | Omni 100 Modem |
| EQUIPMENT | EQUPPP47 | Power Pack Omni 470 |
| EQUIPMENT | EQUPPP49 | Power Pack Omni 490 |
| EQUIPMENT | EQUPPP35 | Power Pack PrintPack 350 |
| EQUIPMENT | EQUPCBPP | Cable PrintPack 300/350 |
| EQUIPMENT | EQUPCB1M | Cable Tranz 460 Pin Pad 1 Meter |
| EQUIPMENT | EQUPPP46 | Power Pack Tranz 460 |
| EQUIPMENT | EQUPCB39 | Cable Tranz 395 Pin Pad |
| EQUIPMENT | EQUPWPTC | FDC PC Windows Software |
| EQUIPMENT | EQUPUPTC | FDC PC DOS-Win Software Upgrade |
| EQUIPMENT | EQUPSPCA | Stand Verifone Check Arm |
| EQUIPMENT | EQUPGRDE | 64K RAM Upgrade to StoreFront |
| EQUIPMENT | EQUPFEIT | COUNTERFEIT COP. |
| EQUIPMENT | EQUPLFEE | Loaner Fee Pre-charge |
| EQUIPMENT | EQUPDISP | Paymate 1000 Display |
| EQUIPMENT | EQUPS295 | Epson TM 295 Slip Prntr |
| EQUIPMENT | EQUPRIMT | Imprinter Model 900 |
| EQUIPMENT | EQUPS7CR | Hypercom S7CR Pin Pad |
| EQUIPMENT | EQUPIV6M | IVI 6M Cashier Pad |
| EQUIPMENT | EQUPICTL | ICTL (Unknown equip. type) |
| EQUIPMENT | EQUPHYPE | UNKNOWN - HYPE |
| EQUIPMENT | EQUP1000 | Verifone 1000 Pin Pad |
| EQUIPMENT | EQUPPNPS | Pen Plus Printer |
| EQUIPMENT | EQUPPP7E | Power Packs T7E |
| EQUIPMENT | EQUPPP70 | Power Packs P700 |
| EQUIPMENT | EQUPCBPS | Tranzport 232 Printer Port Splitter |
| EQUIPMENT | EQUPP300 | Verifone PrintPack 300 |
| EQUIPMENT | EQUPFOC1 | Folio Charger (Single) |
| EQUIPMENT | EQUPLINK | CES Link |
| EQUIPMENT | EQUPVER | VER (Unknown Printer) |
| EQUIPMENT | EQUP2000 | Test_0331 |
| EQUIPMENT | EQUPPP1E | Power Packs T7P (T1E) |
| EQUIPMENT | EQUPSPPS | Verifone Privacy Shield |
| EQUIPMENT | EQUPSTBK | Dial Batch Kermit Software |
| EQUIPMENT | EQUPNETA | Moneta PC/Internet Software |
| EQUIPMENT | EQUPCBS7 | Cable S7CR Pin Pad |
| EQUIPMENT | EQUPCBAC | Cable Accelera |
| EQUIPMENT | EQUPCBCR | Cable Check Reader |
| EQUIPMENT | EQUPPPCP | Power Pack Citizen Printer |
| EQUIPMENT | EQUPDRAW | Cash Drawer 5 Bills / 5 Coins |
| EQUIPMENT | EQUPPRN1 | PrintPoint 1000 (Friction) |
| EQUIPMENT | EQUPWERS | Pymt.1000/Power Supply |
| EQUIPMENT | EQUPOVER | Pymt.1000/Keyboard Overlay |
| EQUIPMENT | EQUPCARD | Pymt.1000/Quick Ref. Card |
| EQUIPMENT | EQUPMANU | Pymt.1000/User Manual |
| EQUIPMENT | EQUPCABL | Pymt.1000/PIN Pad Cable |
| EQUIPMENT | EQUPEQUP | Unknown Terminal - PTI Only |
| EQUIPMENT | EQUPPSSP | Unknown Terminal - PTI Only |
| EQUIPMENT | EQUPPRIN | PrintPoint 3000 - Long Base Plate |
| EQUIPMENT | EQUPODUL | PAYMATE MEMORY MODULE |
| EQUIPMENT | EQUPTENA | ANTENNA 2090 |
| EQUIPMENT | EQUPTREX | ANTENNA CELL TREK EXPLR |
| EQUIPMENT | EQUPRRYN | CASE FOR CELLTREK EXPLR |
| EQUIPMENT | EQUPHRGR | CAR ADAPTOR FOR NURIT |
| EQUIPMENT | EQUPARGR | CHARGR BASE UNIT |
| EQUIPMENT | EQUPCOVR | PRINTER COVER NURIT 2090 |
| EQUIPMENT | EQUPVERE | PRINTER COVER 3010 |
| EQUIPMENT | EQUPCP7 | CP7 Printer |
| EQUIPMENT | EQUPP201 | Verifone 201 PinPad |
| EQUIPMENT | EQUPWEDG | WEDG Wedge Swiper |
| EQUIPMENT | EQUPS101 | S101 Verifone SPCL 101 Cashier Pad |
| EQUIPMENT | EQUPDM80 | DM80 80 Column Dot Matrix Printer |
| EQUIPMENT | EQUPDEBT | DEBT |
| EQUIPMENT | EQUPC562 | Citizen 562 Printer |
| EQUIPMENT | EQUPMAG | Mag Tek Pinpad |
| EQUIPMENT | EQUPV776 | Verifact 7.76 Pinpad |
| EQUIPMENT | EQUP3530 | Citizen 3530 Printer |
| EQUIPMENT | EQUPFOC4 | Folio Charger (Quad) |
| EQUIPMENT | EQUPFODO | Folio Docker |
| EQUIPMENT | EQUPFOPP | Folio Pin Pad |
| EQUIPMENT | EQUPSSFM | Stand Flush Mount |
| EQUIPMENT | EQUPSSUB | Stand U Bottom |
| EQUIPMENT | EQUPPRTR | Alliance Printer (Unknown) |
| EQUIPMENT | EQUPBLSS | Buttonless Hand Set |
| EQUIPMENT | EQUPICOT | ICOT (Unknown equip. type) |
| EQUIPMENT | EQUPMD24 | PC Modem (MD24) |
| EQUIPMENT | EQUPP3D | P3D (Unknown Equip. Type) |
| EQUIPMENT | EQUPVCHR | VCHR (Unknown Equip. Type) |
| EQUIPMENT | EQUP380 | UNKNOWN - 380 |
| EQUIPMENT | EQUPFOLO | UNKNOWN - FOLO |
| EQUIPMENT | EQUPNAC | UNKNOWN - NAC |
| EQUIPMENT | EQUPXT7 | UNKNOWN - XT7 |
| EQUIPMENT | EQUPCRDD | Direct Data Cheq'r - Check Reader |
| EQUIPMENT | EQUPCRSM | Soricon MR1000 Check Reader |
| EQUIPMENT | EQUPCZRP | Citizen Roll Printer |
| EQUIPMENT | EQUPSDBC | Soft Deposit/Batch Catcher PC--EDC |
| EQUIPMENT | EQUPSMAC | MacAuthorize PC Software--EDC |
| EQUIPMENT | EQUPSMCI | MCI Trans PC Software--EDC |
| EQUIPMENT | EQUPSMCW | MCI Wizard PC Software--EDC |
| EQUIPMENT | EQUPSPLG | Prologue PC Software --EDC |
| EQUIPMENT | EQUPSQPS | QPS PC Software-EDC |
| EQUIPMENT | EQUPSSDP | Soft Deposit PC software --EDC |
| EQUIPMENT | EQUPSSQR | Squirrel ECR Software--EDC |
| EQUIPMENT | EQUPT8US | UNKNOWN TRANZ 380 - T380 |
| EQUIPMENT | EQUPDCUS | UNKNOWN DATACARD - DCUS |
| EQUIPMENT | EQUPP301 | Verifone 301 Pin Pad |
| EQUIPMENT | EQUPP950 | Verifone 950 HS Sprocket Printer |
| EQUIPMENT | EQUPPPTZ | Power Packs Trnz |
| EQUIPMENT | EQUPPPZX | Power Packs Zon XL |
| EQUIPMENT | EQUPPPO3 | Power Packs Omni380 |
| EQUIPMENT | EQUPPPSC | Power Packs Signature Capture |
| EQUIPMENT | EQUPPP15 | Power Packs P150 |
| EQUIPMENT | EQUPPP25 | Power Packs P250 |
| EQUIPMENT | EQUPPP90 | Power Packs P900 |
| EQUIPMENT | EQUPCB90 | Cable P900 |
| EQUIPMENT | EQUPCB20 | Cable P201 |
| EQUIPMENT | EQUPCBSC | Signature Capture Cable |
| EQUIPMENT | EQUPPMSP | Spindles |
| EQUIPMENT | EQUPCV1E | Cover T7P (T1E) |
| EQUIPMENT | EQUPPET1 | Printer Module T7P (T1E) |
| EQUIPMENT | EQUPCVRV | Ribbon Cover Verl |
| EQUIPMENT | EQUPPOCT | Call Tag |
| EQUIPMENT | EQUPPOMN | Manuals |
| EQUIPMENT | EQUPPOFP | FacePlate |
| EQUIPMENT | EQUPPESC | Signature Capture Coverter Box |
| EQUIPMENT | EQUPCBP4 | Phone Cord 4 Prong |
| EQUIPMENT | EQUPPESP | Signature Capture Pen |
| EQUIPMENT | EQUPP8F | Hypercom P8F ROLL PRINTER |
| EQUIPMENT | EQUPP8S | Hypercom P8S SPROCKET PRINTER |
| EQUIPMENT | EQUPCBHV | Cable Hypercom to Verifone Printer |
| EQUIPMENT | EQUPPMAC | Citizen Printer Arms |
| EQUIPMENT | EQUPT381 | T381 |
| EQUIPMENT | EQUPPODS | Decals/Stickers |
| EQUIPMENT | EQUP**** | Alliance Unknown Pin Pad |
| EQUIPMENT | EQUPPMP7 | Paper Holder CP7 |
| EQUIPMENT | EQUPS7 | Hypercom S7 Pin Pad No Reader |
| EQUIPMENT | EQUPPE10 | Hypercom Splitter Pin Pad Port FIP10 |
| EQUIPMENT | EQUPP101 | P101 |
| EQUIPMENT | EQUPWAYN | Wayne Nucleus Petro |
| EQUIPMENT | EQUPGILG | Gilbarco G Site Petro |
| EQUIPMENT | EQUPRUSY | Ruby System Petro |
| EQUIPMENT | EQUP15MO | HP 15" TCH SCRN MONITOR |
| EQUIPMENT | EQUPTRPR | HP THERMAL RECEIPT PRNTR |
| EQUIPMENT | EQUPBCSC | HP BARCODE SCANNER -USB |
| EQUIPMENT | EQUPKBWM | HP KEYBRD W/MOUSE -USB |
| EQUIPMENT | EQUPMSRD | HP MAG STRIPE RDR -USB |
| EQUIPMENT | EQUPDISB | LOGIC POLE DISPLAY BLACK |
| EQUIPMENT | EQUPCATX | HP CASH TRAY EXTRA |
| EQUIPMENT | EQUPARCP | ZEBRA BARCODE PRINTR |
| EQUIPMENT | EQUPRTWS | MERTOLOGIC WIRELESS SCNR |
| EQUIPMENT | EQUPGCRI | TPG CHECK RDR W/IMAGING |
| EQUIPMENT | EQUPC560 | Citizen 560 Printer |
| EQUIPMENT | EQUPPPAC | Power Pack Accelera |
| EQUIPMENT | EQUPP355 | Verifone P355 Thermal Printer |
| EQUIPMENT | EQUPSVPP | Unknown Terminal - PTI Only |
| EQUIPMENT | EQUPNTR3 | Stand Alone PP 3000 - Small Base Plate |
| EQUIPMENT | EQUPPINP | Verifone 101 PinPad |
| EQUIPMENT | EQUPRIVA | Apriva Wireless Mobile Terminal |
| EQUIPMENT | EQUPV80 | Verifact 8.0 Pinpad |
| EQUIPMENT | EQUPS7CD | Hypercom S7C DUKPT Pin Pad |
| EQUIPMENT | EQUPEPPP | VERIFONE EVEREST PLUS PP |
| EQUIPMENT | EQUPNACC | IPN Access for PC POS |
| EQUIPMENT | EQUPCONT | HYPERCOM NAC CONTROLLER |
| EQUIPMENT | EQUPRTT4 | FDR TOUCHTONE ETC TYPE 4 |
| EQUIPMENT | EQUPPAPY | YOURPAY API MOTO |
| EQUIPMENT | EQUPV3AU | Ver 3.10 ICVERIFY Additional User |
| EQUIPMENT | EQUPPPSE | Verifone 1000SE Pin Pad |
| EQUIPMENT | EQUPZZZZ | test |
| EQUIPMENT | EQUPPS9C | HYPE PPAD S9C 15FT CABLE |
| EQUIPMENT | EQUPPPS9 | HYPE PPAD S9 15FT CABLE |
| EQUIPMENT | EQUP9C15 | HYPE PPAD S9C 6FT CABLE |
| EQUIPMENT | EQUPS915 | HYPE PPAD S9 6FT CABLE |
| EQUIPMENT | EQUPPPST | Everest Plus Stand |
| EQUIPMENT | EQUPWKIT | Welcome Kit |
| EQUIPMENT | EQUPQRG1 | Quick Reference Guide |
| EQUIPMENT | EQUPPWPK | PowerPack |
| EQUIPMENT | EQUPOLAY | Overlay |
| EQUIPMENT | EQUPGENC | INGENICO EN-CRYPT 100 PIN PAD |
| EQUIPMENT | EQUPBPII | FD-10 |
| EQUIPMENT | EQUP8DOC | NURIT 8000 DOCKING STATION |
| EQUIPMENT | EQUPCASW | MagTek Card Swipe |
| EQUIPMENT | EQUPTIVC | CITIZEN VEHICLE CHARGER |
| EQUIPMENT | EQUPT RB | CITIZEN REPLACE BAT 9.7V |
| EQUIPMENT | EQUPT CC | CITIZEN CARRYING CASE |
| EQUIPMENT | EQUPTPMR | CITIZEN BT PRINTER/MAG R |
| EQUIPMENT | EQUP12VC | EXTECH 12V VEHICLE CHRGR |
| EQUIPMENT | EQUPSHST | EXTECH SHOULDER STRAP |
| EQUIPMENT | EQUPBLSY | EXTECH BELT LOOP SYSTEM |
| EQUIPMENT | EQUPBATP | EXTECH BATTERY PACK |
| EQUIPMENT | EQUPBPMR | EXTECH BT PRINTER/MAG RD |
| EQUIPMENT | EQUPVERS | Verifone P150 Printer |
| EQUIPMENT | EQUPODEM | ODEM MODEM |
| EQUIPMENT | EQUPV744 | Verifact 7.44 Pinpad |
| EQUIPMENT | EQUPSSLB | Stand L Bottom |
| EQUIPMENT | EQUPOMRO | UNKNOWN - OMRO |
| EQUIPMENT | EQUPVMMF | Verifone MoblMrch--Telephone |
| EQUIPMENT | EQUPCRUK | UNKNOWN CHECK READER - CRUK |
| EQUIPMENT | EQUPV150 | Verifact 15.01 Pin Pad |
| EQUIPMENT | EQUPCB25 | Cable P250 |
| EQUIPMENT | EQUPCBP6 | Phone Cord 6 Prong |
| EQUIPMENT | EQUPEH33 | EH33 |
| EQUIPMENT | EQUPDSPP | DataCard Silent Partner Printer |
| EQUIPMENT | EQUPSTBR | Dial Batch RJE Software |
| EQUIPMENT | EQUPSTAC | Stacker |
| EQUIPMENT | EQUPDCPP | Datacard SPPII PinPad |
| EQUIPMENT | EQUPCB70 | Cable P700 |
| EQUIPMENT | EQUPSPRP | Verifone Printer/Pin Pad Stand |
| EQUIPMENT | EQUPCB9M | Cable Tranz 460 Pin Pad 9 Meter |
| EQUIPMENT | EQUPCBCP | Cable Citizen Printer |
| EQUIPMENT | EQUPKEYS | Pymt.1000/Register Key Set |
| EQUIPMENT | EQUPADAP | AC/DC ADAPTOR FOR NURIT |
| EQUIPMENT | EQUPTERY | BATTERY 3010 + 2090 |
| EQUIPMENT | EQUPOMNT | Paycom.net (G/W) |
| EQUIPMENT | EQUPMPRT | Imprinter Model 916 |
| EQUIPMENT | EQUPOCHK | Omni Check Reader |
| EQUIPMENT | EQUPP7E | UNKNOWN - P7E |
| EQUIPMENT | EQUPCBP7 | Cable CP7 |
| EQUIPMENT | EQUPS8D | Hypercom S8 DUKPT Pin Pad |
| EQUIPMENT | EQUPACTO | Exact |
| EQUIPMENT | EQUPOBIX | Globix |
| EQUIPMENT | EQUPCAUT | MacAuthorizer |
| EQUIPMENT | EQUPTCOM | Network Commerce |
| EQUIPMENT | EQUPTTEK | Payteck |
| EQUIPMENT | EQUPUGNP | Plug n Pay |
| EQUIPMENT | EQUPDIAN | Radient |
| EQUIPMENT | EQUPEEDP | Speedpay |
| EQUIPMENT | EQUP374M | Omni 3740-4M |
| EQUIPMENT | EQUP37DM | Omni 3740DM-4M |
| EQUIPMENT | EQUPALS9 | Vital-S9 |
| EQUIPMENT | EQUPS916 | Vital-S9-16 |
| EQUIPMENT | EQUPAS9C | Vital-S9C |
| EQUIPMENT | EQUPTDAT | Thales Pinpad |
| EQUIPMENT | EQUPT292 | Lipman 292 |
| EQUIPMENT | EQUPTPEN | IVI en-Crypt 100 |
| EQUIPMENT | EQUP800M | Lipman 8000-S Motient |
| EQUIPMENT | EQUPCRIM | Magtek Micr Imager |
| EQUIPMENT | EQUP4KAM | VIVOPAY 4000 PROXIMITY READER - WINDOW MOUNT |
| EQUIPMENT | EQUP13PP | Equinox P1300-6FT cbl |
| EQUIPMENT | EQUPSCBT | APRIVA SC30BT BATTERY |
| EQUIPMENT | EQUPSCCC | APRIVA SC30BT CAR CHRGR |
| EQUIPMENT | EQUPPWCS | APRIVE PRINTER W/CASE |
| EQUIPMENT | EQUP0CPP | FD-10C |
| EQUIPMENT | EQUPWMIN | MAG TEK USB WEDGE |
| EQUIPMENT | EQUPVDTF | VIVOPAY DTF |
| EQUIPMENT | EQUPVDTM | VIVOPAY DTM |
| EQUIPMENT | EQUPS232 | MAGTEK Check Reader 22533003 |
| EQUIPMENT | EQUPGT03 | MAGTEK Check Reader 22533003 |
| EQUIPMENT | EQUPMAGT | MAGTEK Check Reader 22522043 |
| EQUIPMENT | EQUPS607 | PTI-IVI Scribe 607 |
| EQUIPMENT | EQUPS602 | PTI-IVI Scribe 602 |
| EQUIPMENT | EQUP0PCI | FD-10 PCI PINPAD |
| EQUIPMENT | EQUPLBPP | Gilbarco Passport |
| EQUIPMENT | EQUPP906 | Equinox S9 PCI-6FT cbl |
| EQUIPMENT | EQUP9C06 | HYPE PPAD S9C PCI 6FT CABLE |
| EQUIPMENT | EQUPSPCI | HYPE PPAD S9C PCI 15FT CABLE |
| EQUIPMENT | EQUP9PCI | Equinox S9 PCI-16FT cbl |
| EQUIPMENT | EQUP1PCI | Verifone 1000SE PCI Pin Pad |
| EQUIPMENT | EQUPCFPP | Mx830 PIN Pad |
| EQUIPMENT | EQUPSPCO | RST SOL RECPT PWR CNDTNR |
| EQUIPMENT | EQUPTPCN | RST SOL KTCHN PWR CNDTNR |
| EQUIPMENT | EQUPBORD | FD Solution Keyboard |
| EQUIPMENT | EQUPPOLE | FD SOLUTION POLE DISPLAY |
| EQUIPMENT | EQUPREPR | FD SOL RECEIPT PRINTER |
| EQUIPMENT | EQUPROUT | POS Value Exchange 4 Port Router |
| EQUIPMENT | EQUPDRWR | FD SOLUTION CASH DRAWER |
| EQUIPMENT | EQUPRESO | REST SOLUTION SOFTWARE |
| EQUIPMENT | EQUP1316 | Equinox P1300-16FT cbl |
| EQUIPMENT | EQUPPONS | BAMS TSYS equiptype - PPAK350 |
| EQUIPMENT | EQUPPORE | BAMS TSYS equiptype - EC6014 |
| EQUIPMENT | EQUPPORG | BAMS TSYS equiptype - EC6014NOCR |
| EQUIPMENT | EQUPPORI | BAMS TSYS equiptype - EN2600I |
| EQUIPMENT | EQUPPORK | BAMS TSYS equiptype - EN2600IP |
| EQUIPMENT | EQUPPOS1 | BAMS TSYS equiptype - CR600BG |
| EQUIPMENT | EQUPPOS3 | BAMS TSYS equiptype - PP1000SE |
| EQUIPMENT | EQUPSLV2 | VeriFone PAYware Mobile IPhone Encryption Sleeve |
| EQUIPMENT | EQUPCSDK | PC CHARGE SDK |
| EQUIPMENT | EQUPMPUS | MAG30050400 MPUS |
| EQUIPMENT | EQUPCP2A | PC wevchamp |
| EQUIPMENT | EQUPSTRE | FD SOL MAG STRIPE RDR |
| EQUIPMENT | EQUPROTE | FD SOLUTN 8 PORT ROUTER |
| EQUIPMENT | EQUPRT8R | 8 Port Router |
| EQUIPMENT | EQUPGRDR | TP8315 MagStripe Reader |
| EQUIPMENT | EQUPRLAN | Apriva Wireless LAN Vending |
| EQUIPMENT | EQUPRVAV | Apriva Wireless Vending |
| EQUIPMENT | EQUPIRDR | IVI MR2300 CHECKREADER |
| EQUIPMENT | EQUPMMOB | COMSTAR MOBILEPRO PRINTER |
| EQUIPMENT | EQUPNPRI | GENERIC PRINTER |
| EQUIPMENT | EQUPESCA | E-SEEK SCANNER WITH OUT P |
| EQUIPMENT | EQUPSWPC | GO SOFTWARE/PC CHARGE EXP |
| EQUIPMENT | EQUPTIPP | TALENTO T-IPP CREDIT/DEBI |
| EQUIPMENT | EQUPF8S8 | PETRO HYPERCOM S-8 PIN PAD |
| EQUIPMENT | EQUPS612 | PTI-IVI Scribe 612 |
| EQUIPMENT | EQUPISCR | IVI Scribe Printer |
| EQUIPMENT | EQUPD562 | Citizen IPS 562 Printer |
| EQUIPMENT | EQUPI301 | i3010 External PIN Pad |
| EQUIPMENT | EQUPYPOS | Insert Poster for Loyalty |
| EQUIPMENT | EQUPGPRS | FD400 GPRS |
| EQUIPMENT | EQUPCDMA | FD-400 CDMA |
| EQUIPMENT | EQUPPCHR | Ret Sol Chk Rdr / Prntr |
| EQUIPMENT | EQUPTKMI | MagtekUSBWedgeReaderVPOS |
| EQUIPMENT | EQUPSBAR | Retail Sol Barcode Prntr |
| EQUIPMENT | EQUPSBOF | Ret Sol Bckoffice sftwre |
| EQUIPMENT | EQUPLSOF | Ret Solution Softwre pcA |
| EQUIPMENT | EQUPSCAN | Ret Sol Barcode Scanner |
| EQUIPMENT | EQUPPTC | FDC PTC PC Software |
| EQUIPMENT | EQUPSTBL | Dial Batch LS-Line Software |
| EQUIPMENT | EQUPPPRO | Payment Pro PC Software |
| EQUIPMENT | EQUPOGRD | PCChrg Upgrd Latestversion |
| EQUIPMENT | EQUPCBNU | BAMS TSYS equiptype - 8320U |
| EQUIPMENT | EQUPCBNV | BAMS TSYS equiptype - VERIFONE PC CHARGE |
| EQUIPMENT | EQUPCBNW | BAMS TSYS equiptype - HCSTAGE |
| EQUIPMENT | EQUPCBNX | BAMS TSYS equiptype - AUTH |
| EQUIPMENT | EQUPCBNY | BAMS TSYS equiptype - VX510 |
| EQUIPMENT | EQUPCBNZ | BAMS TSYS equiptype - T-IPP |
| EQUIPMENT | EQUPCBO1 | BAMS TSYS equiptype - IC VERIFY |
| EQUIPMENT | EQUPCBO2 | BAMS TSYS equiptype - 3020-22 |
| EQUIPMENT | EQUPCBO3 | BAMS TSYS equiptype - ICE 5500VISA OR 5700VISA |
| EQUIPMENT | EQUPCBO4 | BAMS TSYS equiptype - 3020 |
| EQUIPMENT | EQUPCBO5 | BAMS TSYS equiptype - ELITE 712 |
| EQUIPMENT | EQUPCBO6 | BAMS TSYS equiptype - JIGSAW |
| EQUIPMENT | EQUPCBO7 | BAMS TSYS equiptype - RMS |
| EQUIPMENT | EQUPCBO8 | BAMS TSYS equiptype - PRO |
| EQUIPMENT | EQUPCBO9 | BAMS TSYS equiptype - T-ONE |
| EQUIPMENT | EQUPCBOA | BAMS TSYS equiptype - V-NET |
| EQUIPMENT | EQUPCBOB | BAMS TSYS equiptype - 8320E |
| EQUIPMENT | EQUPCBOC | BAMS TSYS equiptype - 3730 |
| EQUIPMENT | EQUPCBOD | BAMS TSYS equiptype - POS |
| EQUIPMENT | EQUPCBOE | BAMS TSYS equiptype - 8320SC |
| EQUIPMENT | EQUPCBOF | BAMS TSYS equiptype - P7E |
| EQUIPMENT | EQUPCBOG | BAMS TSYS equiptype - 3000 |
| EQUIPMENT | EQUPCBOH | BAMS TSYS equiptype - T-IPPS |
| EQUIPMENT | EQUPCBOI | BAMS TSYS equiptype - SC5000 |
| EQUIPMENT | EQUPCBOJ | BAMS TSYS equiptype - PV1310 |
| EQUIPMENT | EQUPCBOK | BAMS TSYS equiptype - POSPORT |
| EQUIPMENT | EQUPCBOL | BAMS TSYS equiptype - XL |
| EQUIPMENT | EQUPCBOM | BAMS TSYS equiptype - LINK |
| EQUIPMENT | EQUPTIGS | FD400Ti GPRS |
| EQUIPMENT | EQUPCBON | BAMS TSYS equiptype - 2085+ |
| EQUIPMENT | EQUPCBOO | BAMS TSYS equiptype - 3730LE |
| EQUIPMENT | EQUPCBOQ | BAMS TSYS equiptype - Everest |
| EQUIPMENT | EQUPCBNI | BAMS TSYS equiptype - R-IMAGER 2600 |
| EQUIPMENT | EQUPCBNJ | BAMS TSYS equiptype - R-RDM 6014I |
| EQUIPMENT | EQUPCBNK | BAMS TSYS equiptype - N-RDM 6004I |
| EQUIPMENT | EQUPCBNL | BAMS TSYS equiptype - RDM 6004I |
| EQUIPMENT | EQUPCBNM | BAMS TSYS equiptype - N-RDM 6014I |
| EQUIPMENT | EQUPCBNN | BAMS TSYS equiptype - N-CR600 |
| EQUIPMENT | EQUPCBNO | BAMS TSYS equiptype - N-MGTK COMBO CRD/CHK |
| EQUIPMENT | EQUPCBNP | BAMS TSYS equiptype - CR1000I |
| EQUIPMENT | EQUPCBNQ | BAMS TSYS equiptype - N-INGENICO 2500 |
| EQUIPMENT | EQUPCBNR | BAMS TSYS equiptype - RDM 5004I |
| EQUIPMENT | EQUPCBNS | BAMS TSYS equiptype - R-CR600 |
| EQUIPMENT | EQUPCBNT | BAMS TSYS equiptype - R-INGENICO 2500 |
| EQUIPMENT | EQUPPMQ6 | TSYS equiptype - UNKNOWN Equipment |
| EQUIPMENT | EQUPTASQ | Pin Pad 1000SEUSB |
| EQUIPMENT | EQUPP8SR | S8000 Receipt Printer |
| EQUIPMENT | EQUPPRJ6 | FD300Ti |
| EQUIPMENT | EQUPJ719 | FD300Ti WiFi |
| EQUIPMENT | EQUPXMDX | Mag 22360001_Excella MDX |
| EQUIPMENT | EQUPIPAD | Mag30050200 IPAD |
| EQUIPMENT | EQUPGUSB | Magtek 21040145 Mini USB |
| EQUIPMENT | EQUPNET1 | $$$ ON THE NET Internet Gateway |
| EQUIPMENT | EQUPPH02 | APRIVA SG5 CELL PHONE |
| EQUIPMENT | EQUPANBC | BDA Web Commerce |
| EQUIPMENT | EQUPONCO | BLACKBOARD (CampusWide On-Line (g/w)) |
| EQUIPMENT | EQUPCGWE | ELAVON ProtoBase LL Car Rental/Lodging |
| EQUIPMENT | EQUPWRKS | HP/Verifone Payworks |
| EQUIPMENT | EQUPALLR | iMall/Site.RegisterCom (g/w) |
| EQUIPMENT | EQUPLOBG | iMall/The Globe (g/w) |
| EQUIPMENT | EQUPCPIP | Sun Coast Las Vegas Leased Line |
| EQUIPMENT | EQUPWAVE | Wave III |
| EQUIPMENT | EQUPYPAY | Yourpay |
| EQUIPMENT | EQUPPURE | YOURPAY SP CONVERT |
| EQUIPMENT | EQUP35ST | FD35 PP Stand |
| EQUIPMENT | EQUPABLE | Cable |
| EQUIPMENT | EQUPISTN | Swivel Stand - Hypercom ICE 5500 |
| EQUIPMENT | EQUPKIPR | REST SOL KITCHEN PRNTER |
| EQUIPMENT | EQUPCBIE | TEST EDC MESSAGE VENDOR/MERC |
| EQUIPMENT | EQUPCBKH | TEST EDC MESSAGE VENDOR/MERC |
| EQUIPMENT | EQUPCB64 | LEASED LINE FMT-7 TEST SETUP |
| EQUIPMENT | EQUPCBKQ | BATCH TEST SETUP |
| EQUIPMENT | EQUPCB2U | LEASED LINE FMT-15 TEST SETUP |
| EQUIPMENT | EQUPCB5V | VP TERM DIAL TEST SETUP |
| EQUIPMENT | EQUP35HW | FD35 HW PIN Pad w NFC-EMV |
| EQUIPMENT | EQUPBLR2 | Pogo MSR |
| EQUIPMENT | EQUPBL2B | BAMS Mobile Pay MSR |
| EQUIPMENT | EQUPILPF | FD Mobile Pay MSR |
| EQUIPMENT | EQUPLPXQ | FD MOBILE PAY MOBILE MSR |
| EQUIPMENT | EQUPXCVB | Test Test test 1 |
| EQUIPMENT | EQUPNFD6 | FD60 |
| EQUIPMENT | EQUP2573 | Pina Dave Test |
| EQUIPMENT | EQUP107L | Test 05March 1608 |
| EQUIPMENT | EQUP124 | Test |
| EQUIPMENT | EQUPBEMS | BAMS BENTO MSR |
| EQUIPMENT | EQUPC123 | testequip4 |
| EQUIPMENT | EQUPB123 | testequip2 |
| EQUIPMENT | EQUPMNNA | HYPERCOM P8 FRICTION PRIN - G3 BAM COV/EOL |
| EQUIPMENT | EQUPMNNB | HYPERCOM S7 PIN PAD - G3 BAM COV/EOL |
| EQUIPMENT | EQUP4587 | Testing1 |
| EQUIPMENT | EQUP9658 | Testing2 |
| EQUIPMENT | EQUP4894 | Test3 |
| EQUIPMENT | EQUPIVEL | FD130 Swivel Stand |
| EQUIPMENT | EQUPPE4S | TRANZ 380 X 2 64k |
| EQUIPMENT | EQUPPE4T | HYPERCOM T7E |
| EQUIPMENT | EQUPPE4U | PayPal  (Verisign) Payflow Link Reseller |
| EQUIPMENT | EQUPPE4V | Innovations |
| EQUIPMENT | EQUPPE4W | Atomic Software |
| EQUIPMENT | EQUPPE4X | HYPERCOM T7E |
| EQUIPMENT | EQUPPE4Y | HYPERCOM T7E - 512K |
| EQUIPMENT | EQUPPE4Z | Hypercom T7 Plus |
| EQUIPMENT | EQUPPE51 | Hypercom T7 Plus - 512K |
| EQUIPMENT | EQUPTBCD | Cash Drawer |
| EQUIPMENT | EQUPAOAN | Clover Station |
| EQUIPMENT | EQUPVCDR | Clover Cash Drawer  |
| EQUIPMENT | EQUPVSCL | Clover Scale |
| EQUIPMENT | EQUPJRDA | PAYware Mobile e100 Audio Jack Card Reader |
| EQUIPMENT | EQUPKTPR | Kitchen Receipt Printer |
| EQUIPMENT | EQUPLFBX | Clover Hub |
| EQUIPMENT | EQUPATRF | Tablet Point of Sale System |
| EQUIPMENT | EQUPTHPR | FT Store Receipt Printer |
| EQUIPMENT | EQUP1DSR | Clover 1D Scanner |
| EQUIPMENT | EQUP2DSR | 2D Scanner |
| EQUIPMENT | EQUPA126 | test |
| EQUIPMENT | EQUP1067 | FD130 Test Case 13 |
| EQUIPMENT | EQUPE123 | testequip6 |
| EQUIPMENT | EQUP1PP2 | VF PP1000SE PCI-2 |
| EQUIPMENT | EQUP1052 | test equip 123 |
| EQUIPMENT | EQUP106Z | Test4March2014 1321 |
| EQUIPMENT | EQUP1070 | Test4March2014 1453 |
| EQUIPMENT | EQUP1072 | Test04March2014 1611 |
| EQUIPMENT | EQUP107D | Test 05March1044 |
| EQUIPMENT | EQUP104I | Test 20 Feb 3 |
| EQUIPMENT | EQUP107N | test cardnet |
| EQUIPMENT | EQUP107M | Test 05March 1610 |
| EQUIPMENT | EQUP1094 | test 11March 1047 |
| EQUIPMENT | EQUP10A8 | Test13 mar 1527 |
| EQUIPMENT | EQUP10CM | test 17 march 16141 |
| EQUIPMENT | EQUP10DZ | Test 19 March Buypass 2 |
| EQUIPMENT | EQUP10DY | Test  19 March Buypass 1 - |
| EQUIPMENT | EQUP10DX | Test 19 March Compass |
| EQUIPMENT | EQUP10DV | Test 19 March Cardnet 2 |
| EQUIPMENT | EQUP10DR | Test 19 March Nashville 3 |
| EQUIPMENT | EQUPST40 | test equip 89 |
| EQUIPMENT | EQUPST41 | test equip 89 |
| EQUIPMENT | EQUP10F8 | Test 21 March 1527 /7711 |
| EQUIPMENT | EQUP10FP | test 24 march 6 |
| EQUIPMENT | EQUP10FO | test 24 march 5 |
| EQUIPMENT | EQUP10FL | test 24 march 2 |
| EQUIPMENT | EQUPST96 | test equip 83 |
| EQUIPMENT | EQUPST99 | test equip 83 |
| EQUIPMENT | EQUP10J9 | FD130 Test Case 23 |
| EQUIPMENT | EQUP10KQ | FD130 Test Case 27 |
| EQUIPMENT | EQUP10KY | testing |
| EQUIPMENT | EQUP1077 | fgdfg |
| EQUIPMENT | EQUP101W | Pina Test Pinpad |
| EQUIPMENT | EQUP10M3 | FD130 Test Case 38 |
| EQUIPMENT | EQUPNSHV | VFI PCCharge 5.10.1 Nash |
| EQUIPMENT | EQUP107K | testing213389137 |
| EQUIPMENT | EQUP108F | test 07March 1209 |
| EQUIPMENT | EQUP109Q | Test 12March 1014 |
| EQUIPMENT | EQUP10BA | Test 14 March 1011 |
| EQUIPMENT | EQUPST24 | test equip 89 |
| EQUIPMENT | EQUPST25 | test equip 89 |
| EQUIPMENT | EQUPST26 | test equip 89 |
| EQUIPMENT | EQUP10ER | Test 21 March 09491 |
| EQUIPMENT | EQUP10EZ | Test 21 March 1507 Nashville 1 |
| EQUIPMENT | EQUP10ET | test 21 march 01 |
| EQUIPMENT | EQUPST44 | test equip 89 |
| EQUIPMENT | EQUP10FN | test 24 march 4 |
| EQUIPMENT | EQUP10FM | test 24 march 3 |
| EQUIPMENT | EQUP10FK | test 24 march 1 |
| EQUIPMENT | EQUPST51 | test equip 89 |
| EQUIPMENT | EQUPST71 | test equip 89 |
| EQUIPMENT | EQUPST02 | test equip 83 |
| EQUIPMENT | EQUPST03 | test equip 83 |
| EQUIPMENT | EQUPST04 | test equip 83 |
| EQUIPMENT | EQUPST05 | test equip 83 |
| EQUIPMENT | EQUPST92 | test equip 92 |
| EQUIPMENT | EQUPS016 | test equip 83 |
| EQUIPMENT | EQUPS017 | test equip 83 |
| EQUIPMENT | EQUPS026 | test equip 83 |
| EQUIPMENT | EQUPS028 | test equip 83 |
| EQUIPMENT | EQUP10IB | Test 18 April 1442 |
| EQUIPMENT | EQUP10IE | Test 18 April 1500 |
| EQUIPMENT | EQUP10LK | Pina Var Test2 |
| EQUIPMENT | EQUP10LJ | Pina Var Test1 |
| EQUIPMENT | EQUP108S | test 10March 1524 |
| EQUIPMENT | EQUPST42 | test equip 89 |
| EQUIPMENT | EQUP10F2 | Test 21 March 1527 /77 |
| EQUIPMENT | EQUP10F1 | Test 21 March 1525 -21 |
| EQUIPMENT | EQUP10F6 | test cardnet petro 2 |
| EQUIPMENT | EQUP10F7 | test 21 march 55sjjjd2w |
| EQUIPMENT | EQUP10F9 | test issueslklk |
| EQUIPMENT | EQUPST95 | test equip 83 |
| EQUIPMENT | EQUP10HZ | Test 18 April 1014 |
| EQUIPMENT | EQUP10I3 | test 18 april 1038 |
| EQUIPMENT | EQUP10I5 | test 18 April 1051 |
| EQUIPMENT | EQUP10I6 | test 18 April 1103 |
| EQUIPMENT | EQUP10HX | FD130 Test Case 21 |
| EQUIPMENT | EQUP10I9 | test 1330 18 april |
| EQUIPMENT | EQUP10JW | Test 28 April 1143 |
| EQUIPMENT | EQUP10LQ | FD130 Test Case 37 |
| EQUIPMENT | EQUP102K | HUNTINGTN EPAID MSR |
| EQUIPMENT | EQUP10LZ | Pina Dave Weigh Scale |
| EQUIPMENT | EQUPST15 | test equip 89 |
| EQUIPMENT | EQUP109R | Test 12March 1624 |
| EQUIPMENT | EQUP10D7 | Test 18 March 11152 R |
| EQUIPMENT | EQUP10D5 | test 18 march 11122 |
| EQUIPMENT | EQUP10D2 | Test 18 March 11051 |
| EQUIPMENT | EQUP10D0 | test 18 march 10571 |
| EQUIPMENT | EQUPST28 | test equip 89 |
| EQUIPMENT | EQUPST29 | test equip 89 |
| EQUIPMENT | EQUP10E0 | Test 19 March Buypass 3 / |
| EQUIPMENT | EQUP10DW | Test 19 march Compass 1 |
| EQUIPMENT | EQUP10DU | Test 19 March Cardnet 1 |
| EQUIPMENT | EQUP10DT | Test 19 March 5 Nashville |
| EQUIPMENT | EQUP10DS | Test 19 March Nashville 4 |
| EQUIPMENT | EQUP10DQ | Test 19 March Nashville 2 |
| EQUIPMENT | EQUP10EV | Test 21 March 1352 N 1 |
| EQUIPMENT | EQUP10F4 | Test 21 March 1559 |
| EQUIPMENT | EQUP10F5 | test cardnet petro |
| EQUIPMENT | EQUP10DL | Test 19 March 09.49 |
| EQUIPMENT | EQUPST20 | test equip 89 |
| EQUIPMENT | EQUPST36 | test equip 89 |
| EQUIPMENT | EQUPST46 | test equip 89 |
| EQUIPMENT | EQUPST56 | test equip 89 |
| EQUIPMENT | EQUPST63 | test equip 89 |
| EQUIPMENT | EQUPST66 | test equip 89 |
| EQUIPMENT | EQUPST67 | test equip 89 |
| EQUIPMENT | EQUPST68 | test equip 89 |
| EQUIPMENT | EQUPST79 | test equip 89 |
| EQUIPMENT | EQUPST87 | test equip 83 |
| EQUIPMENT | EQUPST98 | test equip 83 |
| EQUIPMENT | EQUPS021 | test equip 83 |
| EQUIPMENT | EQUPS022 | test equip 83 |
| EQUIPMENT | EQUPS050 | test equip 83 |
| EQUIPMENT | EQUPS051 | test equip 83 |
| EQUIPMENT | EQUPS052 | test equip 83 |
| EQUIPMENT | EQUPS055 | test equip 83 |
| EQUIPMENT | EQUP10IA | Test 18 April 1424 |
| EQUIPMENT | EQUP10IC | Test 18 April 1444 |
| EQUIPMENT | EQUP10ID | tEST 18 aPRIL 1457 |
| EQUIPMENT | EQUP10JA | FD130 Test Case 24 |
| EQUIPMENT | EQUP10JB | test 22 april 1539 |
| EQUIPMENT | EQUP10JQ | Test 23 April 1632 |
| EQUIPMENT | EQUP10JV | XXXXXXXXXXX |
| EQUIPMENT | EQUP10KJ | MX915 BAMS Pinpad Test |
| EQUIPMENT | EQUP10KO | FD130 TC 23 Redo |
| EQUIPMENT | EQUP10KX | Multicurrancy TEST2 |
| EQUIPMENT | EQUP1088 | dfgdfg |
| EQUIPMENT | EQUP10LM | FD20 |
| EQUIPMENT | EQUP10AD | test equip 89 |
| EQUIPMENT | EQUPST16 | test equip 89 |
| EQUIPMENT | EQUP106U | FD130 Test Case 15 |
| EQUIPMENT | EQUPST23 | test equip 89 |
| EQUIPMENT | EQUPST50 | test equip 89 |
| EQUIPMENT | EQUPST52 | test equip 89 |
| EQUIPMENT | EQUPST53 | test equip 89 |
| EQUIPMENT | EQUPST54 | test equip 89 |
| EQUIPMENT | EQUPS030 | test equip 83 |
| EQUIPMENT | EQUPS045 | test equip 83 |
| EQUIPMENT | EQUP10L2 | Check Reader Test 2 |
| EQUIPMENT | EQUP10H8 | test equip intersilo |
| EQUIPMENT | EQUP10LO | FD21 |
| EQUIPMENT | EQUP10LV | Pina Weigh Scale |
| EQUIPMENT | EQUP102L | Pina Card Reader |
| EQUIPMENT | EQUPPINA | Pina Dave POS TEST VAR |
| EQUIPMENT | EQUP10MF | Pina TEST SRS RC VAR3 |
| EQUIPMENT | EQUP10MG | Pina Card Reader NS |
| EQUIPMENT | EQUP1068 | Clover Mobile Dock |
| EQUIPMENT | EQUP1069 | Clover Mobile Printer |
| EQUIPMENT | EQUP106A | Clover Mobile Wi-Fi Only |
| EQUIPMENT | EQUP106B | Clover Mobile 3G & Wi-Fi |
| EQUIPMENT | EQUP10CZ | test 18 march 10041 |
| EQUIPMENT | EQUP10DI | test equip 0319 |
| EQUIPMENT | EQUPST58 | test equip 89 |
| EQUIPMENT | EQUPST59 | test equip 89 |
| EQUIPMENT | EQUPST60 | test equip 89 |
| EQUIPMENT | EQUPS056 | test equip 83 |
| EQUIPMENT | EQUP10LC | Test 3 June 1414 |
| EQUIPMENT | EQUP10KI | Mx915 BAMS Pinpad Test |
| EQUIPMENT | EQUP10L0 | Check Reader Test 1 |
| EQUIPMENT | EQUP10KW | EDC Checkdigit Test |
| EQUIPMENT | EQUP102T | this is a test 09 July |
| EQUIPMENT | EQUP103A | RAM3 EC MobilePay |
| EQUIPMENT | EQUP103B | RAM3 EC Wells Fargo |
| EQUIPMENT | EQUP103C | RAM3 EC POGO |
| EQUIPMENT | EQUP1017 | CLOVER FD40 US Silver |
| EQUIPMENT | EQUP1018 | CLOVER WEIGHT SCALE |
| EQUIPMENT | EQUP1019 | KITCHEN PRTR-ASIAN CHR |
| EQUIPMENT | EQUP10MI | Pina Card Reader-NS2  |
| EQUIPMENT | EQUPHWR1 | TEST HW REFRESH 1 |
| EQUIPMENT | EQUP105N | FD40 Non-Contactless PP |
| EQUIPMENT | EQUP10ND | Siong HW Refresh Test 12 |
| EQUIPMENT | EQUP10OB | Siong HW Refresh Test 25 |
| EQUIPMENT | EQUP107S | ROAM MSR Mobile Reader |
| EQUIPMENT | EQUP107U | FD130 + FD35 Pin Pad |
| EQUIPMENT | EQUP107Y | Wells ROAM EMV Mobl Rdr |
| EQUIPMENT | EQUP1080 | BAMS ROAM MSR Mobl Rdr |
| EQUIPMENT | EQUP10OG | Pina Test EMV Reader3 |
| EQUIPMENT | EQUP10N2 | Siong HW Refresh Test 5 |
| EQUIPMENT | EQUP10N4 | Siong HW Refresh Test 6 |
| EQUIPMENT | EQUP105B | CYBERSOURCE ICS2 GTW |
| EQUIPMENT | EQUP10O0 | test 1510 2 march |
| EQUIPMENT | EQUP10O7 | Siong HW Refresh Test 24 |
| EQUIPMENT | EQUP10P9 | Siong HW Refresh Test 34 |
| EQUIPMENT | EQUP10PE | Test 1234 1105 |
| EQUIPMENT | EQUP115I | Siong Var Test 28 |
| EQUIPMENT | EQUP10O6 | test 6 march |
| EQUIPMENT | EQUP107H | FD40 Non-CTLS PP |
| EQUIPMENT | EQUP109H | VX805 Pin Pad |
| EQUIPMENT | EQUP10OY | Test Nash Sept 14 |
| EQUIPMENT | EQUP1150 | Siong Var Test 26 |
| EQUIPMENT | EQUP115T | Siong Var Test 35 |
| EQUIPMENT | EQUP10PV | Test-1218 |
| EQUIPMENT | EQUP10QD | Siong HW Refresh Test 42 |
| EQUIPMENT | EQUP10QB | Siong HW Refresh Test 40 |
| EQUIPMENT | EQUP10QE | Siong HW Refresh Test 43 |
| EQUIPMENT | EQUP10QF | Siong HW Refresh Test 44 |
| EQUIPMENT | EQUP10QH | Siong HW Refresh Test 46 |
| EQUIPMENT | EQUP10QI | Siong HW Refresh Test 47 |
| EQUIPMENT | EQUP117M | VPOS Walker C2X |
| EQUIPMENT | EQUP107C | FD410 GPRS UK |
| EQUIPMENT | EQUP106V | FD40 Pin Pad Swivel Stand |
| EQUIPMENT | EQUP107X | Wells ROAM MSR Mobl Rdr |
| EQUIPMENT | EQUP107Z | BAMS ROAM EMV Mobl Rdr |
| EQUIPMENT | EQUP110N | FD410 DW |
| EQUIPMENT | EQUP112U | VX680 WiFi Pin Pad |
| EQUIPMENT | EQUP113X | Siong Var Test 6 |
| EQUIPMENT | EQUP113Z | Siong Var Test 8 |
| EQUIPMENT | EQUP114M | Siong Var Test 18 |
| EQUIPMENT | EQUP114O | Siong Var Test 19 |
| EQUIPMENT | EQUP114R | Siong Var Test 20 |
| EQUIPMENT | EQUP114X | Siong Var Test 24 |
| EQUIPMENT | EQUP10PY | Test-1221 |
| EQUIPMENT | EQUP10PZ | TEST-1223 |
| EQUIPMENT | EQUP10NJ | Siong HW Refresh Test 18 |
| EQUIPMENT | EQUP1086 | Mobile To Go |
| EQUIPMENT | EQUP10OJ | Siong HW Refresh Test 28 |
| EQUIPMENT | EQUP10P6 | Siong HW Refresh Test 31 |
| EQUIPMENT | EQUP115K | Siong Var Test 30 |
| EQUIPMENT | EQUP115M | Siong Var Test 31 |
| EQUIPMENT | EQUP10Q1 | test -9876 |
| EQUIPMENT | EQUP10QG | Siong HW Refresh Test 45 |
| EQUIPMENT | EQUP105H | Ingenico I6550 Pin Pad |
| EQUIPMENT | EQUP105C | FD40 PP Swivel Stand |
| EQUIPMENT | EQUP107T | ROAM EMV Mobile Reader |
| EQUIPMENT | EQUP10OZ | Test Cardnet Sept 14 |
| EQUIPMENT | EQUP10P0 | Test Compass Sept 14 |
| EQUIPMENT | EQUP10P7 | Siong HW Refresh Test 32 |
| EQUIPMENT | EQUP10P8 | Siong HW Refresh Test 33 |
| EQUIPMENT | EQUP10PA | Siong HW Refresh Test 35 |
| EQUIPMENT | EQUP10PB | Siong HW Refresh Test 36 |
| EQUIPMENT | EQUP114C | Siong Var Test 17 |
| EQUIPMENT | EQUP1163 | Siong Var Test 36 |
| EQUIPMENT | EQUP10Q0 | Test-2312 |
| EQUIPMENT | EQUP10Q2 | TEST 1020 |
| EQUIPMENT | EQUP10Q7 | TEST 1001 |
| EQUIPMENT | EQUP10Q8 | TEST 0011 |
| EQUIPMENT | EQUP10OD | test 24 March 1401 |
| EQUIPMENT | EQUP110B | Clover Merchant Keypad |
| EQUIPMENT | EQUP110L | VX805 PP w/USB Cable |
| EQUIPMENT | EQUP114S | Siong Var Test 21 |
| EQUIPMENT | EQUP1152 | Siong Var Test 27 |
| EQUIPMENT | EQUP1165 | Siong Var Test 37 |
| EQUIPMENT | EQUP10PW | Testing-123456 |
| EQUIPMENT | EQUP10PX | TEST-1218 |
| EQUIPMENT | EQUP10QA | Siong HW Refresh Test 39 |
| EQUIPMENT | EQUP10QC | Siong HW Refresh Test 41 |
| EQUIPMENT | EQUP1175 | Siong Var Test 35 |
| EQUIPMENT | EQUP1079 | FD130 UK |
| EQUIPMENT | EQUP107B | FD35 Pin Pad UK |
| EQUIPMENT | EQUP107E | FD410 WiFi UK |
| EQUIPMENT | EQUP10P5 | Siong HW Refresh Test 30 |
| EQUIPMENT | EQUP10PC | Siong HW Refresh Test 37 |
| EQUIPMENT | EQUP10PD | Siong HW Refresh Test 38 |
| EQUIPMENT | EQUP113S | Test var 1029 |
| EQUIPMENT | EQUP113T | Testing var 1029 |
| EQUIPMENT | EQUP1140 | Siong Var Test 9 |
| EQUIPMENT | EQUP1157 | Wells INSTMD Dynapro SC |
| EQUIPMENT | EQUP1158 | Wells INSTMD Dynapro6013 |
| EQUIPMENT | EQUP1159 | Wells INSTMD Dynapro6028 |
| EQUIPMENT | EQUP10R2 | Siong HW Refresh Test 83 |
| EQUIPMENT | EQUP11CU | BENSERONLINGA V1.0 RCSRS |
| EQUIPMENT | EQUP11CT | MidniteExSlipstream4.5DW |
| EQUIPMENT | EQUP11P3 | Canadian VX 820 SI |
| EQUIPMENT | EQUP11P4 | Sams Club Retail Package |
| EQUIPMENT | EQUP119F | Siong Test Var 50 |
| EQUIPMENT | EQUP119T | Siong Test Var 55 |
| EQUIPMENT | EQUP11P9 | Pay Sentry 19.3 RC GTW |
| EQUIPMENT | EQUP11Q6 | SemnxParafait2.10.0RCSRS |
| EQUIPMENT | EQUP11PW | OLUZeamsterv2.0GTW SRS |
| EQUIPMENT | EQUP11QR | HAMER ENT RC SRS EC |
| EQUIPMENT | EQUP11QS | Wm Walthers |
| EQUIPMENT | EQUP11QT | Vision 2 Systems DW |
| EQUIPMENT | EQUP11QV | TPS001 v1.0 Nash RC SRS |
| EQUIPMENT | EQUP11AZ | CLOVER FD40 US |
| EQUIPMENT | EQUP11B0 | Clover Go NFC Stand |
| EQUIPMENT | EQUP11BN | CDEARTH RC SRS |
| EQUIPMENT | EQUP11BP | S300 PinPad |
| EQUIPMENT | EQUP11BW | VX 820 SEMI INT PINPAD |
| EQUIPMENT | EQUP1270 | CR1063792_test var |
| EQUIPMENT | EQUP11P7 | Brown Shoe Level10 VX820 |
| EQUIPMENT | EQUP10XH | jboss Test 10 |
| EQUIPMENT | EQUP11PC | Comdata SmrtSls4.02RCSRS |
| EQUIPMENT | EQUP11PH | Comdata SmrtSls4.02SRSRC |
| EQUIPMENT | EQUP11CN | Mexico ICT220 DW |
| EQUIPMENT | EQUP11CO | Mexico ICT220 Int PinPad |
| EQUIPMENT | EQUP11PS | FIS ClearComm GTWRCSRS |
| EQUIPMENT | EQUP11Q8 | Verifone Mx 915 Pin Pad |
| EQUIPMENT | EQUP11QG | Westgate Resorts EC SRS |
| EQUIPMENT | EQUP11QZ | Clover Flex Countertop Kit |
| EQUIPMENT | EQUP11R0 | Bypass Clover ISV |
| EQUIPMENT | EQUP11R7 | TR MCM IAB |
| EQUIPMENT | EQUP11R8 | Trust Commerce GTW RC EC |
| EQUIPMENT | EQUP11RB | SiteOne Landscape Supply |
| EQUIPMENT | EQUP11RC | CLOVER ISV CARECLOUD |
| EQUIPMENT | EQUP11AQ | FD ClovrGo EMV NFC RDR |
| EQUIPMENT | EQUP11AS | MagTek MICRSafe USB |
| EQUIPMENT | EQUP11CR | TranSafe EDC GTW SRS EC |
| EQUIPMENT | EQUP11B9 | FD CLOVER GTW EMV |
| EQUIPMENT | EQUP11CV | Prosperity ERP Clover |
| EQUIPMENT | EQUP119R | Siong Test Var 52 |
| EQUIPMENT | EQUP11AP | BAMS ClovrGo EMV NFC RDR |
| EQUIPMENT | EQUP11AR | WELLS EMV NFC Mobl RDR |
| EQUIPMENT | EQUPAA87 | Test |
| EQUIPMENT | EQUP11PA | HELCIM GTWY MS EC RC SRS |
| EQUIPMENT | EQUP11PB | HELCIM GTWY MS RC SRS |
| EQUIPMENT | EQUP11PG | Siong Test Var 62 |
| EQUIPMENT | EQUPTIZI | Test |
| EQUIPMENT | EQUP11PI | VALUEPYMTSYSGTWECRCSRS |
| EQUIPMENT | EQUP11PF | WU Apollo ISO DW |
| EQUIPMENT | EQUP11PT | FIS ISTRTLHCS GTWRCSRSEC |
| EQUIPMENT | EQUP11PU | FIS ISTRTLHCS GTWRCSRS |
| EQUIPMENT | EQUP11PY | LEXNEX PF GTW RC SRS |
| EQUIPMENT | EQUP11Q0 | Mexico IWL220 DW |
| EQUIPMENT | EQUP119G | Siong Test Var 51 |
| EQUIPMENT | EQUP11AT | MagTek IMAGESafe USB |
| EQUIPMENT | EQUP11B5 | Siong Test Var 56 |
| EQUIPMENT | EQUP10R0 | Siong HW Refresh Test 82 |
| EQUIPMENT | EQUP11P5 | Pay Sentry 19.3 GTW RC |
| EQUIPMENT | EQUP11P6 | VALUEPYMTSYSGTWRCSRS |
| EQUIPMENT | EQUPT | a |
| EQUIPMENT | EQUP11PM | Canadian MX 915 SI |
| EQUIPMENT | EQUP11PN | Canadian MX 925 SI |
| EQUIPMENT | EQUP11PK | PSIGate 2.5 GW EC RC SRS |
| EQUIPMENT | EQUP11PL | GHSPA v120010 RC SRS |
| EQUIPMENT | EQUP11PP | TPS001 v1.0 RC SRS |
| EQUIPMENT | EQUP11PQ | MONEY MOVERS GTWY |
| EQUIPMENT | EQUP11PX | SIMPLEPAY GTW RC SRS |
| EQUIPMENT | EQUP11PZ | LEXNEX PF GTW EC RC SRS |
| EQUIPMENT | EQUP11Q2 | CASHIER LIVE GTWY RC SRS |
| EQUIPMENT | EQUP11PV | OLUZeamsterv2.0GTW SRSEC |
| EQUIPMENT | EQUP11QC | ClearCommerce GTWY |
| EQUIPMENT | EQUP11QD | ClearCommerce GTWY ECOMM |
| EQUIPMENT | EQUP11QI | PAYIX GTW EC RC SRS |
| EQUIPMENT | EQUP11QJ | FTB GTWY EC RC SRS |
| EQUIPMENT | EQUP11QK | HAMER ENT EC RC SRS |
| EQUIPMENT | EQUP11QQ | Siong Test 101 |
| EQUIPMENT | EQUP11QL | AURUSPAY5.1.5.30 ECRCSRS |
| EQUIPMENT | EQUP11QU | FD OMAHA RC NOVARSHEET |
| EQUIPMENT | EQUP11QX | Clover Flex 3G |
| EQUIPMENT | EQUP11QY | Clover Flex Cable Kit |
| EQUIPMENT | EQUP11R3 | CR969132 Test VAR |
| EQUIPMENT | EQUP11R5 | CR969132 Test VAR |
| EQUIPMENT | EQUP10S6 | Check Digit Test 9 |
| EQUIPMENT | EQUP10SC | Check Digit Test 10 |
| EQUIPMENT | EQUP10SM | Check Digit Test 20 |
| EQUIPMENT | EQUP10SN | Check Digit Test 21 |
| EQUIPMENT | EQUP10SO | Check Digit Test 22 |
| EQUIPMENT | EQUP11T6 | HW Refresh Test 1 |
| EQUIPMENT | EQUP10XM | Wildfly Test 12 |
| EQUIPMENT | EQUP11T9 | HW Refresh Test 4 |
| EQUIPMENT | EQUP11TF | TEST COMPASS_CR0226 |
| EQUIPMENT | EQUP127W | iCorePayPNCISV |
| EQUIPMENT | EQUP11UG | CR996763_Test1 |
| EQUIPMENT | EQUP10TN | ETC Test Var 17 |
| EQUIPMENT | EQUP11UY | CR1002592_TEST_1 |
| EQUIPMENT | EQUP12C4 | CR1110749_testterminal |
| EQUIPMENT | EQUP12C5 | CR1110749_testvar1 |
| EQUIPMENT | EQUP12CL | CR1132476_Terminal |
| EQUIPMENT | EQUP115N | TEST_0419 |
| EQUIPMENT | EQUP116V | Test_2004_nash_2 |
| EQUIPMENT | EQUP1171 | Test_2004_nash_3 |
| EQUIPMENT | EQUP1189 | Test_2304_Comp1 |
| EQUIPMENT | EQUP118B | Test_2304_Comp2 |
| EQUIPMENT | EQUP118C | Test_2304_Comp3 |
| EQUIPMENT | EQUP10RM | AAABCD |
| EQUIPMENT | EQUP10S0 | Check Digit Test 4 |
| EQUIPMENT | EQUP10S3 | Check Digit Test 7 |
| EQUIPMENT | EQUP10S4 | Check Digit Test 8 |
| EQUIPMENT | EQUP10S7 | TEST_SHAWN |
| EQUIPMENT | EQUPABCD | ABCD |
| EQUIPMENT | EQUPABC1 | ABCD |
| EQUIPMENT | EQUP10SG | Check Digit Test 14 |
| EQUIPMENT | EQUP10SJ | Check Digit Test 17 |
| EQUIPMENT | EQUP10SK | Check Digit Test 18 |
| EQUIPMENT | EQUP10SL | Check Digit Test 19 |
| EQUIPMENT | EQUP11T7 | HW Refresh Test 2 |
| EQUIPMENT | EQUP1271 | CR1063792_test terminal |
| EQUIPMENT | EQUP10XR | WF Test 17 |
| EQUIPMENT | EQUP11TG | LAC Vx-820 PinPad |
| EQUIPMENT | EQUP10XG | TEST1 |
| EQUIPMENT | EQUP10XS | test1 |
| EQUIPMENT | EQUP1281 | TEST-CR1078130 |
| EQUIPMENT | EQUP129E | CR1088824-terminal |
| EQUIPMENT | EQUP11U2 | Mexico Vx520 Int PinPad |
| EQUIPMENT | EQUP11U4 | Mexico Vx675 Int PinPad |
| EQUIPMENT | EQUP11RI | NTS |
| EQUIPMENT | EQUP11RJ | NOVODIA Group GTW RC SRS |
| EQUIPMENT | EQUP11RE | VP Term RC SRS |
| EQUIPMENT | EQUP11RF | EDC RC SRS |
| EQUIPMENT | EQUP11RG | DL Host RC SRS |
| EQUIPMENT | EQUP11RR | 3Delta GTWY RC |
| EQUIPMENT | EQUP11SZ | Mexico PayPoint GTW MOTO |
| EQUIPMENT | EQUP11RW | Excentus 7.1 Petro RC |
| EQUIPMENT | EQUP11RA | ISO Global RC SRS |
| EQUIPMENT | EQUP11T1 | Princess Cruise RCSRS |
| EQUIPMENT | EQUP11SD | Monetra 8.x RC SRS EC |
| EQUIPMENT | EQUP11SK | Passport 11.02 |
| EQUIPMENT | EQUP11S8 | Vanco Services LLC |
| EQUIPMENT | EQUP11RD | MRL POSNET GTW SRS |
| EQUIPMENT | EQUP11SM | YMCA |
| EQUIPMENT | EQUP11T0 | Mexico PayPoint GTW EC |
| EQUIPMENT | EQUP11T2 | Princess Cruise RCSRS EC |
| EQUIPMENT | EQUP10TL | ETC Test Var 16 |
| EQUIPMENT | EQUP10XK | jboss test 12 |
| EQUIPMENT | EQUP10XQ | WF Test 16 |
| EQUIPMENT | EQUP11XT | CR1015656_terminal |
| EQUIPMENT | EQUP11ZZ | CR1020046_Terminal |
| EQUIPMENT | EQUP1291 | CR1093731-terminal |
| EQUIPMENT | EQUP1238 | D Link DGS 1008P Switch |
| EQUIPMENT | EQUP10VV | BTS Test 3 |
| EQUIPMENT | EQUP10WK | Test Equipment DW 6 |
| EQUIPMENT | EQUP126M | Apple ClvrGo NFC RDR V2 |
| EQUIPMENT | EQUP126O | Bypass MasterKey |
| EQUIPMENT | EQUP126P | Bypass MasterKey CD |
| EQUIPMENT | EQUP126T | Bypass PreActivated |
| EQUIPMENT | EQUP126U | Booker ISV Clover |
| EQUIPMENT | EQUP1298 | P500 Printer |
| EQUIPMENT | EQUP12A9 | CR-terminal-0204 |
| EQUIPMENT | EQUP10YG | test_test |
| EQUIPMENT | EQUP10YK | pos_test |
| EQUIPMENT | EQUP12BV | CR18.02_ Terminal |
| EQUIPMENT | EQUP12CG | CR1100729_terminal |
| EQUIPMENT | EQUP12C3 | CR1110749_testvar |
| EQUIPMENT | EQUP12CF | CR1100729_test |
| EQUIPMENT | EQUP115S | Test_1904 |
| EQUIPMENT | EQUP116P | Test_2004_nash_1 |
| EQUIPMENT | EQUP1176 | Test_2004_nash_4 |
| EQUIPMENT | EQUP1179 | Test_2004_nash_5 |
| EQUIPMENT | EQUP118D | Test_2304_Comp4 |
| EQUIPMENT | EQUP11X3 | CR1013481_Terminal |
| EQUIPMENT | EQUP10Y2 | Test-Chiranjib |
| EQUIPMENT | EQUP10V0 | TEST_Wildfly |
| EQUIPMENT | EQUP1296 | PAX S300 Swival Stand |
| EQUIPMENT | EQUP10VT | BTS Test 2 |
| EQUIPMENT | EQUP10VZ | BTS Test 5 |
| EQUIPMENT | EQUP10XP | wf test 15 |
| EQUIPMENT | EQUP12C9 | VeriFone Carbon 10 |
| EQUIPMENT | EQUP1121 | Test_0418_ETC |
| EQUIPMENT | EQUP118R | Test_2304_Card3 |
| EQUIPMENT | EQUP118S | Test_2304_Card4 |
| EQUIPMENT | EQUP118T | Test_2304_Card5 |
| EQUIPMENT | EQUP118V | Test_2304_Card6 |
| EQUIPMENT | EQUP118W | Test_2304_ETC1 |
| EQUIPMENT | EQUP118X | Test_2304_ETC2 |
| EQUIPMENT | EQUP118Y | Test_2304_ETC3 |
| EQUIPMENT | EQUP118Z | Test_2304_ETC4 |
| EQUIPMENT | EQUP1190 | Test_2304_ETC6 |
| EQUIPMENT | EQUP119L | Test_2304_ETC5 |
| EQUIPMENT | EQUP119N | Test_2304_1 |
| EQUIPMENT | EQUP119V | Test_2304_2 |
| EQUIPMENT | EQUP11BQ | Test_2304_3 |
| EQUIPMENT | EQUP11BR | Test_2304_4 |
| EQUIPMENT | EQUP11BS | Test_2304_5 |
| EQUIPMENT | EQUP11C0 | Test_2304_6 |
| EQUIPMENT | EQUP12K9 | TEST18.05_Terminal |
| EQUIPMENT | EQUP12AS | CR_Test1 |
| EQUIPMENT | EQUP12AU | CR1114035_Test1 |
| EQUIPMENT | EQUP12B3 | test monday 123 |
| EQUIPMENT | EQUP11WH | CR1008744_0412_terminal |
| EQUIPMENT | EQUP10YJ | tes_te |
| EQUIPMENT | EQUP10ZM | test IR_0418 |
| EQUIPMENT | EQUP10TW | TEST_Voltage |
| EQUIPMENT | EQUP10V1 | TEST Compass-Wildfly |
| EQUIPMENT | EQUP11Z6 | Clover FlexSiliconeSleev |
| EQUIPMENT | EQUP11Z7 | Clover EmployeeLoginCard |
| EQUIPMENT | EQUP10V6 | Wildfly Test 5 |
| EQUIPMENT | EQUP10V7 | Wildfly Test 6 |
| EQUIPMENT | EQUP11Z8 | BREADCRUMBPOS |
| EQUIPMENT | EQUP10VS | BTS Test 1 |
| EQUIPMENT | EQUP10VY | BTS Test 4 |
| EQUIPMENT | EQUP123V | WFPG C2X Reader |
| EQUIPMENT | EQUP1261 | CC ISV Ingenico iCT250 |
| EQUIPMENT | EQUP1262 | CC ISV Ingenico iPP320 |
| EQUIPMENT | EQUP111R | test_0418_1 |
| EQUIPMENT | EQUP1264 | CC ISV Ingenico iUN |
| EQUIPMENT | EQUP1266 | CC ISV Ingenico iWL220 |
| EQUIPMENT | EQUP1267 | CC ISV Ingenico iWL250 |
| EQUIPMENT | EQUP126J | test1 |
| EQUIPMENT | EQUP111S | Test_0418_BP |
| EQUIPMENT | EQUP1120 | Test_0418_CD |
| EQUIPMENT | EQUP12CW | test_2018 |
| EQUIPMENT | EQUP1167 | Test_2004_Nash |
| EQUIPMENT | EQUP11CY | 18.05_test |
| EQUIPMENT | EQUP12KH | Clover Flex |
| EQUIPMENT | EQUP11D0 | test_0517 |
| EQUIPMENT | EQUP12KR | CR1146132_Terminal |
| EQUIPMENT | EQUP12KV | Clover Flex Travel Kit |
| EQUIPMENT | EQUP1277 | Test1 |
| EQUIPMENT | EQUP11X8 | CR1010425_Test 1 |
| EQUIPMENT | EQUP11Y3 | CR1019197 |
| EQUIPMENT | EQUP11YZ | CR1029878_Terminal |
| EQUIPMENT | EQUP11Z2 | Voltage_Terminal |
| EQUIPMENT | EQUP10V8 | Wildfly Test 7 |
| EQUIPMENT | EQUP128S | FollettPNCISV |
| EQUIPMENT | EQUP10VW | Test_Terminal 1 |
| EQUIPMENT | EQUP10VX | VAR_Test 2 |
| EQUIPMENT | EQUP123M | MiCamp ISV Clover |
| EQUIPMENT | EQUP10W0 | compliance_test |
| EQUIPMENT | EQUP10WF | Test Equipment DW 2 |
| EQUIPMENT | EQUP10WJ | Test Equipment DW 5 |
| EQUIPMENT | EQUP123W | PINA TEST BTS |
| EQUIPMENT | EQUP10WQ | hajaratest |
| EQUIPMENT | EQUP1269 | CC ISV Ingenico iWL280 |
| EQUIPMENT | EQUP126A | CC ISV Miura M007 |
| EQUIPMENT | EQUP126D | Verifone MX 925 |
| EQUIPMENT | EQUP126K | TEST2 |
| EQUIPMENT | EQUP126L | test3 |
| EQUIPMENT | EQUP126S | TEST CR |
| EQUIPMENT | EQUP129H | FD ClvrGo NFC RDR V2 |
| EQUIPMENT | EQUP129I | BAMS ClvrGo NFC RDR V2 |
| EQUIPMENT | EQUP129U | CR1102105-terminal |
| EQUIPMENT | EQUP12B0 | test 1x1 |
| EQUIPMENT | EQUP127Y | CR1078130 - terminal |
| EQUIPMENT | EQUP11XW | CR1018432_Terminal |
| EQUIPMENT | EQUP127Z | CR1078130 - TEST VAR |
| EQUIPMENT | EQUP1280 | CR1078130-TEST VAR |
| EQUIPMENT | EQUP11YO | PGW Ingenico IPP320 |
| EQUIPMENT | EQUP10V4 | Wildfly Test 3 |
| EQUIPMENT | EQUP10V5 | Wildfly Test 4 |
| EQUIPMENT | EQUP10W6 | BTS Test 5 |
| EQUIPMENT | EQUP123X | PINA TEST BTS1 |
| EQUIPMENT | EQUP123Y | CC ISV Ingenico iCT220 |
| EQUIPMENT | EQUP126F | test kt part 11 |
| EQUIPMENT | EQUP10YN | test_2018 |
| EQUIPMENT | EQUP12KA | TEST18.05_Var |
| EQUIPMENT | EQUP12KF | CR1144521_Terminal |
| EQUIPMENT | EQUP12L4 | CR1100294_terminal |
| EQUIPMENT | EQUP12L5 | CR1157770_terminal |
| EQUIPMENT | EQUP10TV | test 12 |
| EQUIPMENT | EQUP129C | P550 Printer NFC Display |
| EQUIPMENT | EQUP10V3 | Wildfly Test 2 |
| EQUIPMENT | EQUP1239 | Meraki MR33 Access Point |
| EQUIPMENT | EQUP123C | Meraki MX64 Router |
| EQUIPMENT | EQUP122J | CR1035028_Test 10 |
| EQUIPMENT | EQUP10WX | Manish Test DW9 |
| EQUIPMENT | EQUP1268 | CC ISV Ingenico iWL255 |
| EQUIPMENT | EQUP126B | CC ISV Miura M010 |
| EQUIPMENT | EQUP12AN | ClvrGo Dock V2 |
| EQUIPMENT | EQUP12AR | CR_Test |
| EQUIPMENT | EQUP10YL | reg_test |
| EQUIPMENT | EQUP12C8 | VeriFone Carbon 8 |
| EQUIPMENT | EQUP12CB | VeriFone P400 Plus PINPad |
| EQUIPMENT | EQUP10ZR | t2_test |
| EQUIPMENT | EQUP128O | test var |
| EQUIPMENT | EQUP128P | test.var |
| EQUIPMENT | EQUP11XG | CR1014986_Terminal |
| EQUIPMENT | EQUP11XH | CR1014986_Test Terminal |
| EQUIPMENT | EQUP10TX | Wildfly_Terminal |
| EQUIPMENT | EQUP10V2 | Wildfly Test 1 |
| EQUIPMENT | EQUP10V9 | Wildfly Test 8 |
| EQUIPMENT | EQUP10VB | Wildfly Test 9 |
| EQUIPMENT | EQUP10VC | Wildfly Test 10 |
| EQUIPMENT | EQUP1225 | CR1038731_Terminal |
| EQUIPMENT | EQUP1228 | CR1035028_Test 2 |
| EQUIPMENT | EQUP129G | Station 2018 Kit |
| EQUIPMENT | EQUP123N | Shopkeep ISV Clover |
| EQUIPMENT | EQUP10W7 | PINA TEST GO |
| EQUIPMENT | EQUP10W8 | PINA TEST GO 2 |
| EQUIPMENT | EQUP10WM | PINA TEST GO 3 |
| EQUIPMENT | EQUP123Z | CC ISV ID Tech Augusta |
| EQUIPMENT | EQUP1260 | CC ISV Globalcom BV1000 |
| EQUIPMENT | EQUP10VJ | Test_Manish_3 |
| EQUIPMENT | EQUP10XT | voltage terminal |
| EQUIPMENT | EQUP10ZW | 33_test |
| EQUIPMENT | EQUP112J | teee_134 |
| EQUIPMENT | EQUP118F | Test_2304_Comp5 |
| EQUIPMENT | EQUP118G | Test_2304_Comp6 |
| EQUIPMENT | EQUP118H | Test_2304_Buyp1 |
| EQUIPMENT | EQUP118J | Test_2304_Buyp2 |
| EQUIPMENT | EQUP118K | Test_2304_Buyp3 |
| EQUIPMENT | EQUP118L | Test_2304_Buyp4 |
| EQUIPMENT | EQUP118M | Test_2304_Buyp5 |
| EQUIPMENT | EQUP118N | Test_2304_Buyp6 |
| EQUIPMENT | EQUP118P | Test_2304_Card1 |
| EQUIPMENT | EQUP118Q | Test_2304_Card2 |
| EQUIPMENT | EQUP12CZ | test buypass 23April2018 |
| EQUIPMENT | EQUP11W8 | Error Test 123 |
| EQUIPMENT | EQUP11WR | CR1008751_Terminal |
| EQUIPMENT | EQUP1297 | Clover Station 2018 |
| EQUIPMENT | EQUP11Z5 | 2D Hands Free BC Scanner |
| EQUIPMENT | EQUP11EP | TEST12345 |
| EQUIPMENT | EQUP10WP | PINA TEST TEST |
| EQUIPMENT | EQUP10WR | Test DW Terminal |
| EQUIPMENT | EQUP12AQ | CloverGo UniClip |
| EQUIPMENT | EQUP12AY | Shopkeep2 ISV Clover |
| EQUIPMENT | EQUPTEST | TEST |
| EQUIPMENT | EQUPMN4P | Swivel Stand for Clover Mini |
| EQUIPMENT | EQUP12N9 | Clover Mini 2 PIN Shield |
| EQUIPMENT | EQUP12NP | FD GO MEXICO |
| EQUIPMENT | EQUP12SG | CRQ000000172585_Test 1 |
| EQUIPMENT | EQUP11HQ | test_0620 |
| EQUIPMENT | EQUP11HS | Test123 |
| EQUIPMENT | EQUP11HX | Test123 |
| EQUIPMENT | EQUP11HY | Test123 |
| EQUIPMENT | EQUP11HZ | Test123 |
| EQUIPMENT | EQUP11J0 | Test123 |
| EQUIPMENT | EQUP11J1 | Test123 |
| EQUIPMENT | EQUP12SL | CareStack Pay ISV Clover |
| EQUIPMENT | EQUP11J3 | test_0704 |
| EQUIPMENT | EQUP12TB | Clover Flex 2GStarterKit |
| EQUIPMENT | EQUP12TK | RP10 PinPad Stand |
| EQUIPMENT | EQUP11JL | Test123 |
| EQUIPMENT | EQUP12TO | Clover P501StationPrintr |
| EQUIPMENT | EQUP12UJ | CRQ1117 |
| EQUIPMENT | EQUP12LS | CR1169822_Terminal |
| EQUIPMENT | EQUP12LX | CR1176958_Terminal_TEST |
| EQUIPMENT | EQUP12LY | CR1176958_Ter_TEST |
| EQUIPMENT | EQUP12NF | CRQ000000049450_Terminal |
| EQUIPMENT | EQUP12Q1 | Terminal_CR |
| EQUIPMENT | EQUP12QU | 04_21_Terminal |
| EQUIPMENT | EQUP11HW | test_0626 |
| EQUIPMENT | EQUP12SP | DR TEST 3 |
| EQUIPMENT | EQUP12TP | Clover Cash Drawer CA |
| EQUIPMENT | EQUP12UG | Test 1110 |
| EQUIPMENT | EQUP12UX | Equinox Luxe 6200M |
| EQUIPMENT | EQUP12X6 | 0419_Terminal |
| EQUIPMENT | EQUP12XR | Verfione P400 Eigen Reta |
| EQUIPMENT | EQUP12XU | 06_21_Terminal |
| EQUIPMENT | EQUP12XW | Verione E280PP |
| EQUIPMENT | EQUP12XX | Verifone E285 |
| EQUIPMENT | EQUP12Y3 | Verifone E280PP |
| EQUIPMENT | EQUP12MC | CRQ000000015067_Terminal |
| EQUIPMENT | EQUP12MD | CR_Terminal |
| EQUIPMENT | EQUP12NR | PROD TEST |
| EQUIPMENT | EQUP11FT | test_var 0227 |
| EQUIPMENT | EQUP11FV | fdpos_test var |
| EQUIPMENT | EQUP7890 | test_0315 |
| EQUIPMENT | EQUP12PW | WisePad 2 |
| EQUIPMENT | EQUP12Q9 | March Rel_Test |
| EQUIPMENT | EQUP11J2 | Test123 |
| EQUIPMENT | EQUP11J4 | Test123 |
| EQUIPMENT | EQUP11J6 | Test123 |
| EQUIPMENT | EQUP12T6 | RP10 PIN Pad Stand |
| EQUIPMENT | EQUP11KQ | test 0903 |
| EQUIPMENT | EQUP12UT | Test_1216 |
| EQUIPMENT | EQUP12WT | Epson Label Printer |
| EQUIPMENT | EQUP12X0 | Ingenico Desk5000 pp |
| EQUIPMENT | EQUP12XG | 0517_Terminal |
| EQUIPMENT | EQUP12LO | CR1098308_Terminal |
| EQUIPMENT | EQUP1882 | Test 1 |
| EQUIPMENT | EQUP12LR | CR1169822_Test |
| EQUIPMENT | EQUP12LV | CR1176958_Terminal |
| EQUIPMENT | EQUP12LW | CR1176958 var_Test |
| EQUIPMENT | EQUP12LZ | CR1176958_Test |
| EQUIPMENT | EQUP12M3 | CR1152338_Test_Var |
| EQUIPMENT | EQUP12M4 | CR1152338_Test_Terminal |
| EQUIPMENT | EQUP12M5 | test omaha 0821 |
| EQUIPMENT | EQUP12PR | VeriFone V INT PRINTER |
| EQUIPMENT | EQUP12PN | VeriFone V INT PIN PAD |
| EQUIPMENT | EQUP12N5 | Canadian IPP350 PinPad |
| EQUIPMENT | EQUP12NH | MPOS FD GO |
| EQUIPMENT | EQUP12NT | TEST PROD |
| EQUIPMENT | EQUP12OJ | MerchantLink IPP320 CAN |
| EQUIPMENT | EQUP11G2 | test_0423 |
| EQUIPMENT | EQUP12R3 | CRQ000000152961_Test1 |
| EQUIPMENT | EQUP12R4 | CRQ000000152961_Test2 |
| EQUIPMENT | EQUP12R7 | THD ISC250 CTLS |
| EQUIPMENT | EQUP1441 | TestPos |
| EQUIPMENT | EQUP1442 | test2Pos |
| EQUIPMENT | EQUP12MN | CRQ000000020591_terminal |
| EQUIPMENT | EQUP12N1 | USB EMV Card reader |
| EQUIPMENT | EQUP12PI | CR TEST 21719 |
| EQUIPMENT | EQUP12QC | Test 3-24 Install |
| EQUIPMENT | EQUP11H7 | test_0516 |
| EQUIPMENT | EQUP11HC | Test123 |
| EQUIPMENT | EQUP12RG | test var fdpos 111 |
| EQUIPMENT | EQUP12RH | test var fdpos 112 |
| EQUIPMENT | EQUP12T7 | Clover DUO Terminal |
| EQUIPMENT | EQUP12T8 | Clover DUO Display |
| EQUIPMENT | EQUP12T9 | Clover DUO Starter Kit |
| EQUIPMENT | EQUP12TA | Clover Flex 2nd Gen |
| EQUIPMENT | EQUP12TC | Clover Mini 2 Tether Cbl |
| EQUIPMENT | EQUP11KV | test 10281 |
| EQUIPMENT | EQUP12UH | Test 11101 |
| EQUIPMENT | EQUPZAQA | test test test |
| EQUIPMENT | EQUP12WS | Hands Free BC Scanner 2 |
| EQUIPMENT | EQUP12WU | Star Thermal Kit Printer |
| EQUIPMENT | EQUP12XD | Eigen Verifone Vx690 |
| EQUIPMENT | EQUP12XH | 0517_Terminal |
| EQUIPMENT | EQUP12XI | 0517_Term |
| EQUIPMENT | EQUP12XK | 05_17_Terminalsam |
| EQUIPMENT | EQUP12LI | CR_test |
| EQUIPMENT | EQUP12LJ | CR_test2 |
| EQUIPMENT | EQUP12M1 | CR1176958_Test1 |
| EQUIPMENT | EQUP12MX | test 0916 1 |
| EQUIPMENT | EQUP12N6 | Clover Mini 2 LTE & WiFi |
| EQUIPMENT | EQUP12N7 | Clover Mini 2 StarterKit |
| EQUIPMENT | EQUP12OA | Augusta USB Chip Reader |
| EQUIPMENT | EQUP12O9 | Verifone M400 |
| EQUIPMENT | EQUP11FG | new test |
| EQUIPMENT | EQUP11HB | test_0517 |
| EQUIPMENT | EQUP12SH | WellsSPTest RC EC |
| EQUIPMENT | EQUP12ST | PAX D210 |
| EQUIPMENT | EQUP12U3 | CRQ000000207963_Class A1 |
| EQUIPMENT | EQUP12U2 | CRQ000000207963_Class A |
| EQUIPMENT | EQUP12U6 | CRQ207963_A |
| EQUIPMENT | EQUPFSPP | Test Equip Type |
| EQUIPMENT | EQUP12O7 | CRQ000000072822_Terminal |
| EQUIPMENT | EQUP12OE | Epicor RC IPP320 Canada |
| EQUIPMENT | EQUPTFGR | Test_1023 |
| EQUIPMENT | EQUP12QY | RP10 |
| EQUIPMENT | EQUP12SM | V400M Charging Base |
| EQUIPMENT | EQUP12SN | DR Test |
| EQUIPMENT | EQUP11J9 | test_terminal_0722 |
| EQUIPMENT | EQUP11JC | Test123 |
| EQUIPMENT | EQUP11JD | Test123 |
| EQUIPMENT | EQUP12TD | Clover Account |
| EQUIPMENT | EQUPCCCC | test amit |
| EQUIPMENT | EQUP12WI | 0216_Terminal |
| EQUIPMENT | EQUP12WP | CRQ000000244659_Terminal |
| EQUIPMENT | EQUP12YS | 28/8_Terminal1 |
| EQUIPMENT | EQUP12YT | 28/8_Terminal3 |
| EQUIPMENT | EQUP12ZC | 20/9_Terminal7 |
| EQUIPMENT | EQUP13BC | 17/1_Terminal19 |
| EQUIPMENT | EQUP13BI | Presto A3 |
| EQUIPMENT | EQUP13FN | 18/7_Terminal28 |
| EQUIPMENT | EQUP13G2 | 19/8_Terminal76 |
| EQUIPMENT | EQUP13GN | 19/9_Terminal12 |
| EQUIPMENT | EQUP13H1 | Ingenico Link 2500 CA |
| EQUIPMENT | EQUP13HC | Clover Station Solo CA |
| EQUIPMENT | EQUP13HE | P400 PINPAD VERIFONE CAN |
| EQUIPMENT | EQUP13HL | Verifone MX915 PCI V4 |
| EQUIPMENT | EQUP13HP | Ingenico Lane 7000 CA |
| EQUIPMENT | EQUP13HQ | Ingenico Lane 5000 CA |
| EQUIPMENT | EQUP13IO | Canadian VFI P400 RC |
| EQUIPMENT | EQUP13JQ | 19/5_Terminal46 |
| EQUIPMENT | EQUP13AA | 11/08_TERMINAL_01 |
| EQUIPMENT | EQUP13AF | 12/11_Terminal4 |
| EQUIPMENT | EQUP13BG | Clover Solo Starter Kit |
| EQUIPMENT | EQUP13BM | Equinox Luxe 6200M WLESS |
| EQUIPMENT | EQUP13CS | Clover Go 3rd Gen |
| EQUIPMENT | EQUP13D0 | 18/3_Terminal40 |
| EQUIPMENT | EQUP13E1 | 29/4_Terminal30 |
| EQUIPMENT | EQUP13E7 | 16/5_Terminal48 |
| EQUIPMENT | EQUP13F9 | 17/6_Terminal20 |
| EQUIPMENT | EQUP13GU | MOVE 5000 BLUETOOTH CHAR |
| EQUIPMENT | EQUP11Z4 | 2D Handheld BC Scanner |
| EQUIPMENT | EQUP13I8 | Clover Mini 3 |
| EQUIPMENT | EQUP13JS | 19/5_Terminal17 |
| EQUIPMENT | EQUPOPAY | OPAY |
| EQUIPMENT | EQUPTERN | TERN |
| EQUIPMENT | EQUPBNKD | BNKD |
| EQUIPMENT | EQUP12Y6 | 07_19_Terminal |
| EQUIPMENT | EQUP12YI | Clover Flex 2 Verizon |
| EQUIPMENT | EQUP12YM | 08_16_Terminal_01 |
| EQUIPMENT | EQUP12Z2 | 10/9_Terminal7 |
| EQUIPMENT | EQUP12Z4 | 10/9_Terminal9 |
| EQUIPMENT | EQUP13AH | 15/11_Terminal6 |
| EQUIPMENT | EQUP12D8 | Test02082021 |
| EQUIPMENT | EQUP13C7 | 18/2_Terminal46 |
| EQUIPMENT | EQUP13DF | Clover Mini 2 WiFi |
| EQUIPMENT | EQUP13EL | ING IUP250 PINPAD |
| EQUIPMENT | EQUP13EV | PAX PX7 Pin Pad CA |
| EQUIPMENT | EQUP13F7 | Vx680 Bluetooth Base |
| EQUIPMENT | EQUP13HN | 18/11_Terminal43 |
| EQUIPMENT | EQUP13HW | MX915 PCI 4 |
| EQUIPMENT | EQUP13I9 | Clover Mini 3 StarterKit |
| EQUIPMENT | EQUP12ZP | 18/10_Terminal4 |
| EQUIPMENT | EQUP12ZR | 18/10_Terminal4 |
| EQUIPMENT | EQUP13A9 | 11/08_TERMINAL |
| EQUIPMENT | EQUP13B9 | 16/1_Terminal6 |
| EQUIPMENT | EQUP13C4 | sample |
| EQUIPMENT | EQUP13C9 | TestEquip |
| EQUIPMENT | EQUP13CB | TestEquip2 |
| EQUIPMENT | EQUP13D2 | 21/3_Terminal75 |
| EQUIPMENT | EQUP13DH | Clover Flex 2 WiFi |
| EQUIPMENT | EQUP13DG | Clover Duo Terminal WiFi |
| EQUIPMENT | EQUP13EC | 20/5_Terminal12 |
| EQUIPMENT | EQUP13ES | 13/6_Terminal55 |
| EQUIPMENT | EQUP13EM | IUR250 CARD READER |
| EQUIPMENT | EQUP13FD | 20/6_Terminal30 |
| EQUIPMENT | EQUP13GK | 16/9_Terminal69 |
| EQUIPMENT | EQUP13GL | 16/9_Terminal50 |
| EQUIPMENT | EQUP13GT | VAil Resort Tetra Family |
| EQUIPMENT | EQUP13HK | CLOVER WEIGHT SCALE CA |
| EQUIPMENT | EQUP13J1 | Unattended device |
| EQUIPMENT | EQUP12YR | Test123 |
| EQUIPMENT | EQUP12ZV | 20/10_Terminal3 |
| EQUIPMENT | EQUP12ZX | 20/10_Terminal8 |
| EQUIPMENT | EQUP13EN | Ingenico Lane 7000 PP CA |
| EQUIPMENT | EQUP13EP | Verifone MX925 PCI V 4 |
| EQUIPMENT | EQUP13EQ | Verifone MX925 Coach |
| EQUIPMENT | EQUP13FA | IWL Bluetooth base |
| EQUIPMENT | EQUP13I4 | VF M440  Engage |
| EQUIPMENT | EQUP13JO | 17/5_Terminal54 |
| EQUIPMENT | EQUP13JV | Clover Duo 2 Terminal |
| EQUIPMENT | EQUP13JW | Clover Duo 2 Display |
| EQUIPMENT | EQUP13JX | Clover Duo 2 StarterKit |
| EQUIPMENT | EQUP13K9 | Ingenico Lane 3000 |
| EQUIPMENT | EQUP13KB | Ingenico Lane7000 |
| EQUIPMENT | EQUP13KC | Ingenico Lane8000 |
| EQUIPMENT | EQUPANAK | Test3 |
| EQUIPMENT | EQUPADAD | Test5 |
| EQUIPMENT | EQUP12YA | 07_23_Terminal |
| EQUIPMENT | EQUP12YK | 08_16_Terminal |
| EQUIPMENT | EQUP13AD | Terminal_11/08_02 |
| EQUIPMENT | EQUP13AI | 15/11_Terminal9 |
| EQUIPMENT | EQUP13B5 | TR VER ENG P400 CXPI  |
| EQUIPMENT | EQUP13CK | 21/2_Terminal66 |
| EQUIPMENT | EQUP13D5 | Bypass MasterKey CD CA |
| EQUIPMENT | EQUP13DL | 15/4_Terminal10 |
| EQUIPMENT | EQUP13DM | 15/4_Terminal65 |
| EQUIPMENT | EQUP13DR | 18/4_Terminal85 |
| EQUIPMENT | EQUP13DS | 18/4_Terminal85 |
| EQUIPMENT | EQUP13DT | 18/4_Terminal47 |
| EQUIPMENT | EQUP13FH | Nikki test |
| EQUIPMENT | EQUP13IB | Clover Flex 3 StarterKit |
| EQUIPMENT | EQUP13JH | 417testing2 |
| EQUIPMENT | EQUP13L8 | PAX A77 RC DW |
| EQUIPMENT | EQUP13LB | patchingtest1016 |
| EQUIPMENT | EQUP13CE | TestCC |
| EQUIPMENT | EQUP13DO | 17/4_Terminal54 |
| EQUIPMENT | EQUP13DQ | 18/4_Terminal98 |
| EQUIPMENT | EQUP13EO | Verifone MX915 PCI V 4 |
| EQUIPMENT | EQUP13EU |  IWL CHARGING BASE |
| EQUIPMENT | EQUP13EX | Move 5000 Charging Base |
| EQUIPMENT | EQUP13F2 | IUC150B CLESS READER |
| EQUIPMENT | EQUP13F6 | PAX SP30 PINPad |
| EQUIPMENT | EQUP13FJ | 15/7_Terminal67 |
| EQUIPMENT | EQUP13GB | 29/8_Terminal16 |
| EQUIPMENT | EQUP13IA | Clover Flex 3 |
| EQUIPMENT | EQUP13JT | Equinox 6200 L6200-250E |
| EQUIPMENT | EQUP13K4 | 16/6_Terminal22 |
| EQUIPMENT | EQUP13KA | Ingenico Lane3600 |
| EQUIPMENT | EQUP13LF | Ingenico Lane 5000 |
| EQUIPMENT | EQUP13LK | PAX A80 CA |
| EQUIPMENT | EQUP13LJ | PAX A920 CA |
| EQUIPMENT | EQUP13LI | PAX A35 CA |
| EQUIPMENT | EQUP12ZJ | 6/10_Terminal2 |
| EQUIPMENT | EQUP13BF | Clover Station Solo |
| EQUIPMENT | EQUP13CA | TestEquip1 |
| EQUIPMENT | EQUP13CF | TestCreditCard |
| EQUIPMENT | EQUP13E9 | 16/5_Terminal53 |
| EQUIPMENT | EQUP13EY | VX 680 Charging base |
| EQUIPMENT | EQUP13EZ | VX680 Full Feature Base |
| EQUIPMENT | EQUP13FL | Ingenico V400 Eigen |
| EQUIPMENT | EQUP13FO | 18/7_Terminal57 |
| EQUIPMENT | EQUP11RS | 3Delta GTWY EC RC |
| EQUIPMENT | EQUP13IP | Test31322a |
| EQUIPMENT | EQUP13J3 | Clover Solo starterKitCA |
| EQUIPMENT | EQUP13JP | 18/5_Terminal21 |
| EQUIPMENT | EQUP13M2 | Integrated Desk 5000 CA |
| EQUIPMENT | EQUP13MI | Intregrared VF M400 CA |
| EQUIPMENT | EQUP13QN | Toshiba ACE V8R3 RC SRS |
| EQUIPMENT | EQUP13QO | TGate GTW RC DW SRS SS |
| EQUIPMENT | EQUP13QP | Populus RC GTW |
| EQUIPMENT | EQUP13QS | Interated E280S CA |
| EQUIPMENT | EQUP13NX | Move 5000 Integrated CA |
| EQUIPMENT | EQUP13NW | Lane 3600 Integrated CA |
| EQUIPMENT | EQUP13OK | 07/06_VAR12_UI_REgression |
| EQUIPMENT | EQUP13OV | Castles Saturn 1000 |
| EQUIPMENT | EQUP13OZ | Samsung CA Kiosk Base |
| EQUIPMENT | EQUP13QG | Clover Kiosk Mini Termnl |
| EQUIPMENT | EQUP13M1 | Integrated Move5000 CA |
| EQUIPMENT | EQUP13LP | SAMSUNG 24 INCH KIOSK |
| EQUIPMENT | EQUP13LQ | SAMSUNG KIOSK BASE |
| EQUIPMENT | EQUP13MY | 16/2_Terminal97 |
| EQUIPMENT | EQUP13QA | Integrated PAX A77 CA |
| EQUIPMENT | EQUP13QH | Clover Kiosk Printer |
| EQUIPMENT | EQUP13QI | Clover Kiosk Frame |
| EQUIPMENT | EQUP13QU | FeitianSmartPAYv1SrsMs |
| EQUIPMENT | EQUP13QV | BF PayConex GW RcMs |
| EQUIPMENT | EQUP13QW | ZUMRAILS RC DWSRS EC |
| EQUIPMENT | EQUP13QY | Populus RC GTWY |
| EQUIPMENT | EQUP13NB | 16/4_VAR23 |
| EQUIPMENT | EQUP13O1 | Replaces Micronode1400 |
| EQUIPMENT | EQUP13OU | Samsung CA Kiosk 24 Inch |
| EQUIPMENT | EQUP13QD | Clover KitchenDisplay 24 |
| EQUIPMENT | EQUP13QE | Bump Bar KB9000 USB |
| EQUIPMENT | EQUP13QF | Clover Kiosk Display |
| EQUIPMENT | EQUP13QQ | RCG RC SRS SouthPTS EC |
| EQUIPMENT | EQUP13QR | Exxon |
| EQUIPMENT | EQUP13LY | STAR MICRONICS TSP650II |
| EQUIPMENT | EQUP13N6 | Integrated E285 CA |
| EQUIPMENT | EQUP13NZ | MN2800 Replacement for |
| EQUIPMENT | EQUP13QT | Integrated P400 Plus CA |
| EQUIPMENT | EQUP13QX | ZumRails Funds RC DWSRS |
| EQUIPMENT | EQUP13M9 | Clover Kitchen Display |
| EQUIPMENT | EQUP13R2 | Toshiba ACE V8R3 RC_SRS |
| EQUIPMENT | EQUP13R3 | ZumRails Funds RCDWSRS |
| EQUIPMENT | EQUP13R4 | ELOTouch Buypass RC |
| EQUIPMENT | EQUP13R5 | Tenerum TouchFree GTW RC |
| EQUIPMENT | EQUP13R6 | CenPOS GW RcDwSrsSs |
| EQUIPMENT | EQUP13R8 | E280-604-34 IntegratedCA |
| EQUIPMENT | EQUP13R7 | E285-500-14 IntegratedCA |
| EQUIPMENT | EQUP13R9 | Ingenico Desk 2600 |
| EQUIPMENT | EQUP13RI | 12/4_VAR12_Build_cancellable |
| EQUIPMENT | EQUP13RN | 12/4_Var_BC1_testing |
| EQUIPMENT | EQUP13RD | Clover Flex 4 Pocket |
| EQUIPMENT | EQUP13RE | Clover Compact |
| EQUIPMENT | EQUP13RG | Star Thermal Kit Printr4 |
| EQUIPMENT | EQUP13RA | Ingenico Move 5000 V6 |
| EQUIPMENT | EQUP13RK | 12/4_var12_bUILD_CANCEL |
| EQUIPMENT | EQUP13RF | Clover Companion |
| EQUIPMENT | EQUP13RB | Clover Flex 4 |
| EQUIPMENT | EQUP13RC | Clover Flex 4 StarterKit |
| EQUIPMENT | EQUP13RP | 12/5_VAR5_BC2_testing |
| EQUIPMENT | EQUP13RQ | VALORPAY BP GTW RC SRS |
| EQUIPMENT | EQUP13RR | Tenerum Hostclose GTW RC |
| EQUIPMENT | EQUP13RS | Guestypay RC EC |
| EQUIPMENT | EQUP13RT | Samsung Kiosk Bento |
| EQUIPMENT | EQUP13RU | Equipment code test |
| EQUIPMENT | EQUP13RV | PATCH1-21-24 |
| EQUIPMENT | EQUP13S0 | uCom RC Gateway SS |
| EQUIPMENT | EQUP13S6 | uCom RC GTW SS |
| EQUIPMENT | EQUP13S1 | CodepayRegister GwSrsSs |
| EQUIPMENT | EQUP13S2 | Tempus GTW ISO VPN |
| EQUIPMENT | EQUP13S3 | SELF4000-IntegratedCA |
| EQUIPMENT | EQUP13S4 | Marketpay23.10 GW RC |
| EQUIPMENT | EQUP13S5 | E235-4G-1 IntegratedCA |
| EQUIPMENT | EQUP13SA | Epicor Eagle GTW RC EC |
| EQUIPMENT | EQUP13S9 | Peloton EPP1.X GTW RC DW |
| EQUIPMENT | EQUP13S8 | Cardknox2.X GTW RC DW CA |
| EQUIPMENT | EQUP13S7 | TGate GW RC DW EC SRS SS |
| EQUIPMENT | EQUP13SB | Ingenico Desk 1600 PP |
| EQUIPMENT | EQUP13SC | Bump Bar KB9000 USB CA |
| EQUIPMENT | EQUP13SE | Test - Adm Portal |
| EQUIPMENT | EQUP13SF | KeyGTW KAAS Anet |
| EQUIPMENT | EQUPBCEG | test656 |
| EQUIPMENT | EQUPBCEI | test666I |
| EQUIPMENT | EQUPBCEM | testtest32 |
| EQUIPMENT | EQUPCOPY | COPYTOTEST |
| EQUIPMENT | EQUP11L0 | TEST for ANirban |
| EQUIPMENT | EQUPBCEN | testdemo1 |
| EQUIPMENT | EQUP13SH | Patch3-22-24 |
| EQUIPMENT | EQUP13SJ | Lane3000 Integrated CA |
| EQUIPMENT | EQUP13SK | is8583 |
| EQUIPMENT | EQUP13SL | Datecs RC GW DW SRS MS |
| EQUIPMENT | EQUP13SM | Viscus RC GW DW SRS SS |
| EQUIPMENT | EQUP13SN | TPro RC GW DW SRS EC MS |
| EQUIPMENT | EQUP13SO | MerchTrendFrPy RcGwSrsSs |
| EQUIPMENT | EQUP13SP | Patch4-4-24 |
| EQUIPMENT | EQUP13SQ | MEX Clover FLX4 |
| EQUIPMENT | EQUP13SR | MEX Clover MINI3 |
| EQUIPMENT | EQUP13SS | MEX Clover FLX3 |
| EQUIPMENT | EQUP13ST | TestPatch4-17-24 |
| EQUIPMENT | EQUPZZY8 | Testing_PassBuypass |
| EQUIPMENT | EQUP13SU | Equip_04_18 |
| EQUIPMENT | EQUP13SV | Equip_04_21 |
| EQUIPMENT | EQUP13SW | Everlink GTW ISO VPN |
| EQUIPMENT | EQUP13SX | Jackrabbit V2.1 RC GTW |
| EQUIPMENT | EQUP13SY | EP-DW-GTWY-RT-SURCH-RC |
| EQUIPMENT | EQUP13SZ | Ingenico ARCSIv1 CH GTW |
| EQUIPMENT | EQUP13T0 | P200 Integrated CA |
| EQUIPMENT | EQUP13T1 | Patch 5-2-24 |
| EQUIPMENT | EQUP20S4 | Charge Anywhere VX820 |
| EQUIPMENT | EQUP20S8 | INVENSTAR |
| EQUIPMENT | EQUP20SA | Sicom Systems VX820 |
| EQUIPMENT | EQUP20S7 | NB Dot |
| EQUIPMENT | EQUP20S9 | Brown Shoe Canadian |
| EQUIPMENT | EQUP20S5 | Sears/KMART |
| EQUIPMENT | EQUP20S6 | CR Dot |
| EQUIPMENT | EQUP20S3 | IMS GoPayment |
| EQUIPMENT | EQUP20SB | Charge Anywhere - Blackberry 8703, 8830 |
| EQUIPMENT | EQUPZZY3 | Test Sample_low |
| EQUIPMENT | EQUPZZY2 | Test Pinpad Next |
| EQUIPMENT | EQUPZZY1 | Test Card Reader Next |
| EQUIPMENT | EQUP13T2 | Patch 05_16_24 |
| EQUIPMENT | EQUPZZZY | TechTrex Integrated CA |
| EQUIPMENT | EQUPZZXN | testingnashville54 |
| EQUIPMENT | EQUPZZXM | Nashville Test 3 |
| EQUIPMENT | EQUPZZXH | Test061124 |
| EQUIPMENT | EQUPZZXD | testingN56 |
| EQUIPMENT | EQUP13T8 | Nikki Test |
| EQUIPMENT | EQUP13T9 | CBS RC DW SRS MLTIFE |
| EQUIPMENT | EQUP13TA | Mexico Sim Card |
| EQUIPMENT | EQUP13TC | Patch_06_28 |
| EQUIPMENT | EQUPZZX7 | Test Eq 5 |
| EQUIPMENT | EQUPZZX6 | Equip Test 55 |
| EQUIPMENT | EQUPZZX5 | Equip Tool Test 1 |
| EQUIPMENT | EQUPZZX4 | Equip Tool 2 |
| EQUIPMENT | EQUP13TD | Cardknox 2.X GTW RC DW |
| EQUIPMENT | EQUP13TF | PAYROC EC GTW RC SRS |
| EQUIPMENT | EQUP13TG | PAYROC CP GWY RC SRS |
| EQUIPMENT | EQUP13TH | EquinoxVoyager1.X GTW RC |
| EQUIPMENT | EQUP13TE | Datawire RC EC GTW |
| EQUIPMENT | EQUP13TI | Monet Switch ISO VPN GTW |
| EQUIPMENT | EQUP13TJ | M3T ContPmt GW RcSrsSs |
| EQUIPMENT | EQUP13TK | EquinoxVoyager1.X GTW RC |
| EQUIPMENT | EQUP13TL | Point SCA 5.X.X DWRCSRS |
| EQUIPMENT | EQUPZZZX | Test071924 |
| EQUIPMENT | EQUPZZXG | testingN58 |
| EQUIPMENT | EQUPZZXK | Testing 1234 |
| EQUIPMENT | EQUPZZWZ | Testingnash |
| EQUIPMENT | EQUPZZWY | Testing 55 |
| EQUIPMENT | EQUPZZWX | TestNash5 |
| EQUIPMENT | EQUPZZWW | TestingNash6 |
| EQUIPMENT | EQUP13TM | EC PayPal |
| EQUIPMENT | EQUP13TN | Verifone SCA 4.x RC DW |
| EQUIPMENT | EQUPZZWV | TeatingNash7 |
| EQUIPMENT | EQUPZZVY | TeatingNash8 |
| EQUIPMENT | EQUPZZWT | TestANIrban12 |
| EQUIPMENT | EQUPZZWS | TestNonNash |
| EQUIPMENT | EQUPZZWR | PinpadTest |
| EQUIPMENT | EQUPZZWQ | CardREaderTEST |
| EQUIPMENT | EQUPZZWP | TestBuypass |
| EQUIPMENT | EQUPZZWN | Equip Test 8 |
| EQUIPMENT | EQUPZZWM | testingR56 |
| EQUIPMENT | EQUPZZWK | Test Equip 88 |
| EQUIPMENT | EQUPZZWJ | testebus |
| EQUIPMENT | EQUPZZWH | Test Equip 55 |
| EQUIPMENT | EQUP13TP | Vail GTW RC US DW |
| EQUIPMENT | EQUP13TO | Vail GTW RC CA DW |
| EQUIPMENT | EQUPZZWG | Equip Type New 11 |
| EQUIPMENT | EQUPZZWF | testingtab |
| EQUIPMENT | EQUPZZWD | Equip 88 |
| EQUIPMENT | EQUPZZWC | Equip 55 |
| EQUIPMENT | EQUPZZWB | testingvNash |

<!-- type: tab-end -->
---

### STATUS

* Description: This field indicates whether the product is active or not.
* API field: `isActive`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Required     | Allowed |    NA        |

**Valid Values**:
|         Value        |                    Description                 |
|:----------------------|:------------------------------------------------|
| N | Flag to indicate that product is inactive |
| Y | Flag to indicate that product is active |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Enum   | NA        |    NA        |    Available     | Required     | Allowed |    NA        |

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| Boolean  |    4     |    5    |    Available     |   Required     |  Allowed |     NA        |

**Valid Values**:
|              Value   |                    Description                 |
|:----------------------|:------------------------------------------------|
| N | Flag to indicate that product is inactive |
| Y | Flag to indicate that product is active |

<!-- type: tab-end -->
---

### UNIQUE_IDENTIFIER

* Description: This field serves as a unique identifier for a particular product
* API field: Not Available
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    3        |    Available     | NA     |      NA       |    NA         |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    3        |    Available     | NA     |      NA       |    NA         |

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    3        |    Available     | NA     |      NA       |    NA         |

<!-- type: tab-end -->
---

### FEE_TABLE_ID

* Description: TBD
* API field: `feeTableId`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    16        |    Available     | Optional  |  Allowed   |    NA        |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    16        |    Available     | Optional  |  Allowed   |    NA        |

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 1        |    16        |    Available     | Optional  |  Allowed   |    NA        |

<!-- type: tab-end -->
---

### WHOLESALE_CHARGE

* Description: TBD
* API field: `wholesaleAmountOrPercent`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| BigDecimal  | NA       |    NA        |    Available   | Optional  |  Allowed   |    NA      |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 4        |    11    |    Available     | Optional  |  Allowed   |        NA        |

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String |        4       |    11    |    Available    |      NA      |       NA     |  NA     |

<!-- type: tab-end -->
---

### RETAIL_CHARGE

* Description: TBD
* API field: `retailAmountOrPercent`
* Field Specification:

<!-- type: tab 
titles: UMM, North, GMA 
-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| BigDecimal  | NA       |    NA        |    Available   | Optional  |  Allowed   |    NA      |

<!-- type: tab -->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 4        |    11    |    Available     | Optional  |  Allowed   |    NA        |

<!-- type: tab -->

<!--##### South Specification -->

<!--| Type   | Inquiry  |  Create  |    Update    |    Delete    |-->
<!--|--------|:--------:|:--------:|:------------:|:------------:|-->
<!--| String |     -    |          |              |       NA     |-->

| Type   | Minimum Length | Max Length | Inquiry  |    Create    |    Update    |    Delete    |
|--------|:--------------:|:----------:|:--------:|:------------:|:------------:|:------------:|
| String  | 4        |    11    |    Available     | NA  |  NA   |    NA        |

<!-- type: tab-end -->