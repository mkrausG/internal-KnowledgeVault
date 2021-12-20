ASP Net Features

Mittwoch, 1. April 2015

20:06

 

# Übersicht über die Features von ASP Net

 

[ASP Web Form Features](onenote:ASP%20Net.one#ASP%20Web%20Form%20Features&section-id={767D70D3-DF51-45D0-BA12-83F1E57FD03C}&page-id={16D16168-C8A9-40BE-A4E5-FE780C70D232}&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/Schulung)

[Code Seperation and the Page Class](onenote:ASP%20Net.one#Code%20Seperation%20and%20the%20Page%20Class&section-id={767D70D3-DF51-45D0-BA12-83F1E57FD03C}&page-id={AA4B58F0-4B61-4997-9051-2935C576F81C}&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/Schulung)

[Page Directive and Attributes](onenote:ASP%20Net.one#Page%20Directive%20and%20Attributes&section-id={767D70D3-DF51-45D0-BA12-83F1E57FD03C}&page-id={7B13CD7B-C8C1-42D3-87D2-CC4CB729FB0C}&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/Schulung)

[Web Controls](onenote:ASP%20Net.one#Web%20Controls&section-id={767D70D3-DF51-45D0-BA12-83F1E57FD03C}&page-id={E3F81B98-2C5E-452C-BDBB-B8F73693BB1B}&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/Schulung)

[Validating User Input](onenote:ASP%20Net.one#Validating%20User%20Input&section-id={767D70D3-DF51-45D0-BA12-83F1E57FD03C}&page-id={93AB5C16-CE78-4159-8885-403DFD5DE004}&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/Schulung)

[Setting Defaults](onenote:ASP%20Net.one#Setting%20Defaults&section-id={767D70D3-DF51-45D0-BA12-83F1E57FD03C}&page-id={E8B94C4F-D4D6-452A-9EBA-75E6B7A8FEB7}&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/Schulung)

[Creating User Controls (WebUserControl)](onenote:#Creating%20User%20Controls%20(WebUserControl)&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={BA48B1B2-6E1F-485E-B5AD-4E0134CA33FD}&object-id={424493CF-E81F-4249-A3E3-8CF01150BF28}&11&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet%20Schule/ASP%20Net.one)

[Creating Custom Server Controls](onenote:#Creating%20Custom%20Server%20Controls&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={E3BA5C2D-5224-4AD3-9472-35E0B970DEFC}&object-id={32600B67-9BF3-0770-3686-FAFED73F0ED4}&12&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet%20Schule/ASP%20Net.one)

[Request Validation](onenote:#Request%20Validation&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={D57C4AB5-6DCD-4384-A12B-43435AF71668}&object-id={57E6CF26-2FC4-01EF-3316-C99291693A06}&12&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet%20Schule/ASP%20Net.one)

[Client-Side Development](onenote:#Client-Side%20Development&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={BE44AD00-6F5E-4B19-A7E8-AB729F8104EB}&object-id={3233F32E-630B-0A60-0E93-1EB52566B396}&12&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet%20Schule/ASP%20Net.one)

[Web API](onenote:#Web%20API&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={5911A536-2DD1-44F3-89DF-EAFC45835F83}&object-id={F5248965-EA92-0F11-2ECB-526896DA5C1E}&12&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet%20Schule/ASP%20Net.one)

 

 

Master Forms

User Control

Web Parts

Css

JavaScript

Navigation / Routing

Authorization / Authentication see [Security](onenote:#Security&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={FF464C7C-4BA7-41CD-85E2-988B098CE605}&end&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet%20Schule/ASP%20Net.one)

## code nugget

 

  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  \<%@    Directive = perform an action that affects the entire Web Form. Siehe Page Header in WEbForms
  ------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  \<%     Code Block bzw. Server side scripting delimiter.(Steht inline in Html Seite) Standart Code Nugget that contains code Statements that are evaluated by the Framework. You must use Response.Write method in th code nugget if you want to include html in the response to the browser

  \<%=    Aufruf Code in CodeBehind bzw Methode

  \<%:    Entspricht \<%= but the response is HTML encoded.

  \<%#    Datarepeater == use current bound object .(Databinding) d.h. bezug auf Item \<%# Item%>

  \<%#:   Datarepeater=> net 4... entspricht \<%# (Databinding) but with html encoding

  \<%\$   Property Code Nugget. Used to refer to configuration Value .. e.g. in Web.config
  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

!! Es sollte immer das encoded Nugget gewählt werden wenn man nicht weiß woher die Daten kommen.. z.B. unsichere Lieferant !! Dadurch kein Injection möglich

> Sicherstellen das WebComfofrm String
>
>  
>
> Server.HtmlEncode ...

 

> WEbForms Application needs a global.asax => Initial Configuration => events. Siehe: [Global Lifecycle](onenote:#Lifecycles%20and%20Context&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={19F97947-C062-4E5A-BEC4-F794353F172E}&object-id={E9BFF393-93B3-0A76-015D-5A1FC819A397}&C&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet%20Schule/ASP%20Net.one)

WebForms are compiled into c# classes before they are used to process requests.

 

ASP Web Form Features

Mittwoch, 1. April 2015

20:36

 

:

  ------------------------------------------------------------------------
  ASP Net Control Categories                                        
  ---------------------------- --------- ------------ ------------ -------
  Security                     Data      Navigation   Web Parts    Ajax

  ------------------------------------------------------------------------

 

  ------------------------------------------------------------------------
  Key Features                                              
  ------------------ ------------------- ----------------- ---------------
  Master Pages       Themes/Skins        Localization      Adaptive UI

  ------------------------------------------------------------------------

 

  -----------------------------------------------------------------------
  Application Services APIs                            
  ------------------------------- ------------------- -------------------
  Membership                      Role Manager        Personalization

  Site Navigation                 Caching             Management
  -----------------------------------------------------------------------

Categories

-   Security

-   Data (EF6)

-   Navigation ( WebSiteMap.xml)

-   Web Parts

-   Ajax

Key Features

-   Master Pages (Template)

-   Themes/Skins (themes and css)

-   Localization (MultiLanguage)

-   Adaptive UI (WebControls)

 

Application Service APIs

-   Membership (Security - DB)

-   Role Manager (Security -\> DB)

-   Personalization (Personal Settings -\> DB)

-   Site Navigation ( ggf auch in DB )

-   Caching (Pages , Parts of pages, Data objects )

-   Management

What's in a Web Form

-   Directives ( \<%@ )\
    \<%@ Page Language="C#" AutoEventWireup="True"%>

-   Code Blocks = .html inline scripts ( \<script )\
    \<script language="C#" runat="Server">...\</script>

-   Render Blocks = Write Inhalt von Property / Method ( \<%= )\
    \<%=UserDetails&>

-   Server Controls ( \<asp: )\
    \<aps:Label id="lblHelloWorld" runat="server />

-   User Controls ( \<acme )\
    \<acme: Header id="ucHeader" runat="server" />

-   ASP.Net Expressions (Hole daten aus Web.config) (\<%\$ )\
    \<%\$ ConnectionStrings: NorthWindConnString %>

-   Data Binding Expressions ( \<%# )\
    \<%# Eval("DBFieldName") %>

 

Code Seperation and the Page Class

Mittwoch, 1. April 2015

20:36

 

Aufteilung HTML und Code Files in separate Files.

 

In VS xx kann man auch alles in einer Datei schreiben, das sollte aber nicht der Standard sein.

 

![](./assets/media/image1.png){width="3.839583333333333in" height="2.4430555555555555in"}

 

Wenn das als Single File funktionieren soll und man script braucht dann muss das mit \<script type=\"text/C#\" runat=\"server\" \>

* *

 

 

Page Directive and Attributes

Mittwoch, 1. April 2015

20:37

 

## Page Directive

> How to compile !
>
> ***\<%@ Page Language=\"C#\" %>***
>
>  

## Key Page directive features:

-   Specify Page language

-   Maintain scrollbar positions

-   Identify code file paths

-   Turn on or off tracint ( logging)

-   Identify themes or master pages uses by the page

-   Identify an error page

 

## Übersicht einiger Attribute

+----------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| Attribute                        | Description                                                                                                                     |
+==================================+=================================================================================================================================+
| Async                            | When true the generated page class derives from IHttpAsyncHandler which adds asynchronous capabilities.                         |
+----------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| CodeFile                         | Specifies the name of the refeneced Code-Seperation file to use for the page                                                    |
+----------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| EnableTheming                    | Indicates whether themes can be applied to the page                                                                             |
+----------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| Language                         | Target language used ( C# or VB )                                                                                               |
+----------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| Trace                            | Turns tracing funtionality on or off                                                                                            |
+----------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| MaintainScrollPositionOnPostBack | JavaSCript will be inserted into your rendered page tghat maintains the scroll position in the browser window for all postbacks |
+----------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| Theme                            | Specifies the name off the theme to use                                                                                         |
+----------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| AutoEventWireUp                  | When true, the ASP.NET Framework will automatically call methods in the codebehind                                              |
|                                  |                                                                                                                                 |
|                                  | class in response to page events.                                                                                               |
+----------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| CodeBehind                       | Used to specify the file that contains the code-behind class.                                                                   |
+----------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| EnableEventValidation            | When true, the ASP.NET Framework will validate POST requests to try and prevent                                                 |
|                                  |                                                                                                                                 |
|                                  | maliciously created requests being processed. We explain the events in Chapter 16                                               |
|                                  |                                                                                                                                 |
|                                  | and validation in Part 3. The default value is true and we recommend that you do                                                |
|                                  |                                                                                                                                 |
|                                  | not disable this feature.                                                                                                       |
+----------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| EnableSessionState               | Determines if the ASP.NET Framework supports session state for the Web Form.                                                    |
|                                  |                                                                                                                                 |
|                                  | The default value is true, but this attribute can also be set to false (which disables                                          |
|                                  |                                                                                                                                 |
|                                  | session state) or ReadOnly, which means that no state modifications can be made.                                                |
|                                  |                                                                                                                                 |
|                                  | Session state can have a significant impact on performance                                                                      |
+----------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| EnableViewState                  | Determines if the ASP.NET Framework will use view state to preserve the state of                                                |
|                                  |                                                                                                                                 |
|                                  | controls. The default value is true                                                                                             |
+----------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| EnableViewStateMac               | Determines if ASP.NET will use a message authentication code (MAC) to validate                                                  |
|                                  |                                                                                                                                 |
|                                  | the integrity of view state data                                                                                                |
+----------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| ErrorPage                        | Specifies a page that should be shown to the user when an error occurs processing                                               |
|                                  |                                                                                                                                 |
|                                  | the Web Form.                                                                                                                   |
+----------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| ValidateRequest                  | When set to true, the ASP.NET Framework checks data posted to the application                                                   |
|                                  |                                                                                                                                 |
|                                  | for potentially dangerous content. The default is true and you should not disable                                               |
|                                  |                                                                                                                                 |
|                                  | this feature.                                                                                                                   |
+----------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| ViewStateMode                    | Used to enable or disable the view state feature                                                                                |
+----------------------------------+---------------------------------------------------------------------------------------------------------------------------------+
| ViewStateEncryptionMode          | Used to enable or disable view state encryption                                                                                 |
+----------------------------------+---------------------------------------------------------------------------------------------------------------------------------+

 

Web Controls

Mittwoch, 1. April 2015

20:37

 

# Definition

-   ASP.Net relies on Web Server Controls to collect, display and validate Data

-   Server Controls are classes with properties, methods and events.

-   Server Controls dynamically generate xhtml compliant code.

>  

# Basic Types

-   Web Server Controls\
    Strongly typed programmable Objects ( Classes ) \[z.b. Calender, Checkboxlist, DataSource u.a. )\
    \<asp:Textbox

-   Html Server Controls\
    Rare, Similar to regular HTML elements but you control them on the server-side.\
    z.b. \<input

-   Validation Controls\
    Used to validate Web Form submissions\
    \<asp:RequiredFieldValidator

-   User Controls\
    Custom controls such as headers, footers and menus\
    \<acme:Header

>  
>
>  
>
> Alle Controls MÜSSEN runat=\"server\" haben.
>
>  
>
> Server Control properties can be set declaratively using attributes.\
> z.b.: \<asp:GridView BorderColor=\"black\"
>
>  

 

Validating User Input

Mittwoch, 1. April 2015

20:37

  ------------------------------------------------------------------------
                        ASP                  JSf
  --------------------- -------------------- -----------------------------
  Application var       .Application\[\"     \@Application Attribute

  Session var           .Session\[\"         \@Session Attribute
  ------------------------------------------------------------------------

Validation kann

a.  Client seitig mit Javascript -\> jQuery Validation, nuget oder

> Microsoft jQuery Unobtrusive Validation

b.  Serverside mit Logik \[Attribute an class \[Required(ErrorMessage = \"Please enter your name\")\]

 

Implementiert werden.

 

To Check for Validation errors, use **ModelState.IsValid** in Backend Clas**s**

 

Unter Validierung fallen:

+-----------------------------------------------------+-----------------------------------+
| -   Required entry                                  | \<asp:RequiredFieldValidator>     |
+=====================================================+===================================+
| -   Validating specific criteria (value range, etc) | \<asp:ValidationSummary>          |
+-----------------------------------------------------+-----------------------------------+
| -   Comparing control values (does text1 = text2 ?) | \<asp:CompareValidator>           |
+-----------------------------------------------------+-----------------------------------+
| -   Range Checking                                  | \<asp:RangeValidator>             |
+-----------------------------------------------------+-----------------------------------+
| -   Pattern Matching (Regular Expressions)          | \<aps:RegularExpressionValidator> |
+-----------------------------------------------------+-----------------------------------+
| -   Custom Validation                               | \<asp:CustomValudator>            |
+-----------------------------------------------------+-----------------------------------+

>  

Man kann das Model bzw die Properties eines Models mit dem Attribut

Required versehen :-) Die Methode TryUpdateModel führt dann eine Validierung durch.

![](./assets/media/image2.png){width="1.6791666666666667in" height="1.7833333333333334in"}

 

> Es muss das Property \"ControlToValidate\" gesetzt sein. Es wird dazu auch clientScript gesetzt ( JavaScript) => Property \"EnableClientScript\"
>
>  
>
> Standart wird die Message im Validator gezeigt. Es kann aber auch ein ValidationSummary genutzt werden um alle Fehler anzuzeigen , in einer Stelle in der Form. Dazu im Validator Text zu \"\*\" setzen. (Kennzeichung Feld)
>
>  
>
> Code, Page.Validate() triggerd Validation und mit if(Page.isValid) kann es geprüft werden d.h. das am Server aufrufen und niemand kann im Client das HTML Verändern und schicken, da der Server die Validations auch noch mal durchführt.

 

Setting Defaults

Mittwoch, 1. April 2015

20:37

 

defaultButton = Wenn Enter gedrückt wird.

 

Asp Panel control kann defaultButton überschreiben

 

-   defaultButton

-   defaultFocus ( oder Page.SetFocus, txtName.Focus())

 

Creating User Controls (WebUserControl)

Mittwoch, 1. April 2015

20:37

# CHOOSING USER OR SERVER CONTROLS

User and server controls both allow you to create custom controls and can be used to create the same kind of functionality. User controls are easier to create; it is easy to write HTML in ASCX files and you can use other controls and code nuggets. User controls are not perfect---they are hard to package up for use in multiple projects, and they work best when you always want to generate the same HTML fragment with a small portion of dynamic content.

 

 

Server controls are harder to write because you have to generate the output using C# statements---but this means you can generate non-HTML content (like XML or JSON data) and makes it easy to package controls in an assembly that can be used in different projects. Server controls are also better suited when you want to generate a range of completely different content fragments---you can do this with user controls, but it becomes pretty

complicated. We show you more complex examples of both user and server controls in the chapters that follow

 

> User controls allow us to create reusable blocks of functionality so that we can generate the same fragments of HTML
>
> at different places within our project, in multiple Web Forms or even multiple places in the same Web Form. User
>
> controls are similar to Web Forms in that there is a file that contains markup and code nuggets from which a partial
>
> class is generated and compiled with a code-behind class
>
>  
>
>  
>
> Shared on Websites...
>
>  
>
> z.B. Login Pages, Headers, Footers, Repeating Menus
>
>  
>
> Tag \<%@ Control Language=\"C#\"%>
>
> File Extension must be = .ascx
>
>  
>
> Schritte:

1.  WebUserControl erstellen. ( nun wie webform )

2.  Reference / Register Control in WebForm\
    entweder Source DragDrop oder von Hand\
    Hand würde -\> \<%\@Register src=\"xx\\dd.\" tagname=\"Header\" tagprefix\"uc1\" %> und im Code dann \<uc1:Header runat=\"server\"\>

3.  Alternativ Register die UserControls in web.config\
     

> \<pages>
>
> \<controls>
>
> \<add tagPrefix=\"SS\" tagName=\"CatLinks\" src=\"\~/Controls/CategoryList.ascx\"/>
>
> \<add tagPrefix=\"SS\" tagName=\"CartSummary\" src=\"\~/Controls/CartSummary.ascx\"/>
>
> \</controls>
>
> \</pages>\
>  
>
> **Tip** You can't use the Web.config file to declare user controls that are in the same directory as the Web Form or
>
> master page in which they are used---this is why we use a separate Controls folder.
>
>  
>
> Man kann das user control auch dynamisch einbauen
>
> Dazu muss eigentlich nur der Pfad bekannt sein. Dazu wir ein PlaceHolder genutzt
>
> z.B.
>
> \<div>
>
> \<asp:PlaceHolder ID=\"HeaderPlaceHolder\" runat=\"server\"/>
>
> \</div>
>
>  
>
> Dann im PageLoad
>
> Var ctl = Page.LoadControl(\~/cc/yy.ascx\");
>
> HeaderPlaceHolder.Controls.Add(ctl);

 

Creating Custom Server Controls

Freitag, 26. Juni 2015

19:14

 

Server controls perform the same role as user controls but are defined as a single C# class. There is no support for a

declarative HTML file, and features like server-side HTML elements and building on other controls are not available.

But that's not to say that server controls are less useful---they can be used to generate content in formats other than

HTML, and they can be packaged and reused in multiple projects (something that is hard to do with user controls).

 

Code:

**public class ButtonCounterServerControl** : WebControl\
{\
**protected override void** RenderContents(HtmlTextWriter output)\
{\
int countVal = (int)(Page.Session\[\"server_control_counter\"\] ?? 0);\
**if** (Page.IsPostBack && Page.Request.Form\[\"button\"\] == \"serverControl\")\
{\
Page.Session\[\"server_control_counter\"\] = ++countVal;\
}

output.RenderBeginTag(HtmlTextWriterTag.Div);\
output.Write(\"Server Control Button presses: \");\
output.RenderBeginTag(HtmlTextWriterTag.Span);\
output.Write(countVal);\
output.RenderEndTag();\
output.RenderEndTag();\
output.RenderBeginTag(HtmlTextWriterTag.Div);\
output.AddAttribute(HtmlTextWriterAttribute.Name, \"button\");\
output.AddAttribute(HtmlTextWriterAttribute.Value, \"serverControl\");\
output.AddAttribute(HtmlTextWriterAttribute.Type, \"submit\");\
output.RenderBeginTag(HtmlTextWriterTag.Button);\
output.Write(\"Submit (Server Control)\");\
output.RenderEndTag();\
output.RenderEndTag();\
}\
}

## Registering and Using the Server Control in a WEbForm file

\<%@ Register Assembly=\"WorkingWithControls\" TagPrefix=\"SC\" Namespace=\"WorkingWithControls\" %>

 

Und Usage:

**\<form** id=\"form1\" runat=\"server\"**\>**\
**\<div>**\
Button presses: **\<span** id=\"counter\" runat=\"server\"**\>\</span>**\
**\</div>**\
**\<div>\<button** type=\"submit\"**\>**Submit**\</button>\</div>**\
**\<CC:UCButton** ID=\"userControl\" runat=\"server\" **/>**\
***[\<SC:ButtonCounterServerControl ID=\"serverControl\" runat=\"server\" />]{.underline}***\
**\</form>**

 

 

 

 

## HtmlTextWriter 

The HtmlTextWriter class defines two ways of writing HTML, which we will call constrained and unconstrained and

which we describe both in the sections that follow.

 

 

Freitag, 12. Juni 2015

12:45

 

private IEnumerable\<Order> GetOrders(\[Control\] bool showDispatched)

 

Damit wird dann automatisch in binding erstellt zwischen BackendClass und Webseite.

 

z.b.

In webseite:

\<asp:CheckBox runat=\"server\" ID=\"showDispatched\" Checked=\"false\" AutoPostBack=\"true\"/>Show Dispatched Orders?

 

Wenn nun die Backend eine Methode

GetOrders(\[Control\] bool showDispatched) hat dann wird bei click dann die Funktion aufgerufen.

 

**Difference betweeen ASP.NET WebForms and ASP.NET MVC**

Sonntag, 21. Juni 2015

19:31

 

If you are visiting ASP.NET forums and communities, you will find following questions frequently i.e.

-   What is the difference between ASP.NET MVC and ASP.NET WebForms?

-   Is ASP.NET MVC going to replace ASP.NET WebForms?

-   ASP.NET MVC vs ASP.NET WebForms \| ASP.NET WebForms Vs MVC model?

In this web development tutorial, I'll try to answer and explain such queries.

![ASP.NET MVC Vs ASP.NET WebForms](./assets/media/image3.png){width="5.245138888888889in" height="4.216666666666667in"}

First of all, let me clear that ASP.NET MVC is not replacing ASP.NET WebForms. Both these development models exist and can be used to develop ASP.NET applications. Although both has pros and cons, that we will discuss and compare here.

Before going into deeper details let's have a high level comparison as:

![ASP.NET MVC Vs ASP.NET WebForms](./assets/media/image4.png){width="5.707638888888889in" height="1.8111111111111111in"}

\*\*\*ASP.NET WebForms developers migrating to ASP.NET MVC initially feel a little uncomfortable because they are unable to find many key features that were available in WebForms approach. There are many questions comes to their minds like below:

-   Web is still stateless but where is the **Viewstate**?

-   Where is that **Code behind file**?

-   What is that **Razor syntax**? Why I need it?

-   Where to find **Page_Load** method? that is used to put code for almost every page.

-   What about **Binding and Rich Server Controls**? Where these controls gone?

-   and many more...

 

 

Following table explains the difference to answer above questions by clearly explaining the limitations of each approach.

+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| **ASP.NET Web Forms**                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                  |
|                                                                                                                                                                                                                                                                |                                                                                                                                                                                                                                  |
|                                                                                                                                                                                                                                                                | **ASP.NET MVC**                                                                                                                                                                                                                  |
+================================================================================================================================================================================================================================================================+==================================================================================================================================================================================================================================+
| ASP.NET Web Forms uses Page controller pattern approach for rendering layout. In this approach, every page has it's own controller i.e. code-behind file that processes the request.                                                                           | ASP.NET MVC uses Front Controller approach. That approach means ,a common controller for all pages, processes the requests.                                                                                                      |
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| No separation of concerns. As we discussed that every page (.aspx) has it's own controller (code behind i.e. aspx.cs/.vb file), so both are tightly coupled.                                                                                                   | Very clean separation of concerns. View and Controller are neatly separate.                                                                                                                                                      |
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Because of this coupled behavior, automated testing is really difficult.                                                                                                                                                                                       | Testability is key feature in ASP.NET MVC. Test driven development is quite simple using this approach. Please [follow here](http://msdn.microsoft.com/en-us/magazine/dd942838.aspx) for demo on building testable applications. |
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| In order to achieve stateful behavior, viewstate is used. Purpose was to give developers, the same experience of a typical WinForms application.                                                                                                               | ASP.NET MVC approach is stateless as that of the web. So here no concept of viewstate.                                                                                                                                           |
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Statefulness has a lots of problem for web environment in case of excessively large viewstate. Large viewstate means increase in page size.                                                                                                                    | As controller and view are not dependent and also no viewstate concept in ASP.NET MVC, so output is very clean.                                                                                                                  |
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| ASP.NET WebForms model follows a Page Life cycle.                                                                                                                                                                                                              | No Page Life cycle like WebForms. Request cycle is simple in ASP.NET MVC model.                                                                                                                                                  |
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Along with statefulness, microsoft tries to introduce server-side controls as in Windows applications. Purpose was to provide  somehow an abstraction to the details of HTML. In ASP.NET Web Forms, minimal knowledge of HTML, JavaScript and CSS is required. | In MVC, detailed knowledge of HTML, JavaScript and CSS is required.                                                                                                                                                              |
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Above abstraction was good but provides limited control over HTML, JavaScript and CSS which is necessary in many cases.                                                                                                                                        | Full control over HTML, JavaScript and CSS.                                                                                                                                                                                      |
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| With a lots of control libraries availability and limited knowledge of other related technologies, ASP.NET WebForms is RAD(Rapid Application Development) approach.                                                                                            | It's a step back. For developers decrease in productivity.                                                                                                                                                                       |
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| It's good for small scale applications with limited team size.                                                                                                                                                                                                 | It's better as well as recommended approach for large-scale applications where different teams are working together.                                                                                                             |
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

This article explains the pros and cons associated with each model. And in last point, I concluded that which model is suitable in a scenario. Hopefully, it will be a reference for choosing the right approach.

 

*Aus \<<http://www.webdevelopmenthelp.net/2013/10/difference-between-asp-net-webform-and-asp-net-mvc.html>\>*

 

 

 

**ASP.NET MVC3 Vs MVC4 Vs MVC5 Vs MVC6**

Sonntag, 21. Juni 2015

19:33

 

> **UPDATE**: This ASP.NET MVC tutorial initially targetting MVC3, MVC4 and MVC5 version. Now I have listed down features from next version of ASP.NET MVC6 (code name as ASP.NET vNext).

![MVC Architecture](./assets/media/image5.png){width="9.820833333333333in" height="3.660416666666667in"}

Microsoft has added exciting features in every new version of ASP.NET MVC that make developers more comfortable building scalable web applications easily. In this ASP.NET MVC tutorial, we will have a quick look into new and important features introduced in major versions of Microsoft **ASP.NET MVC** starting from **MVC3** to **MVC5 **(the latest one so far).

![MVC3 Vs MVC4 Vs MVC5 Vs MVC6](./assets/media/image6.png){width="6.245138888888889in" height="1.5284722222222222in"}

**[MVC3 Vs MVC4 Vs MVC5 Vs MVC6]{.underline}**

> **Note:** If you wanted to get a practical example for building your first ASP.NET MVC 5 Application using Entity Framework, please [follow here](http://www.webdevelopmenthelp.net/2014/06/building-first-application-using-mvc-entity-framework.html).

![MVC3 Vs MVC4 Vs MVC5](./assets/media/image7.jpg){width="7.924305555555556in" height="3.0375in"}

**ASP.NET MVC3**

-   **New Project Templates** having support for **HTML 5** and **CSS 3**.

-   Improved **Model validation**.

-   **Razor View Engine** introduced with a bundle of [new features](http://weblogs.asp.net/scottgu/archive/2010/07/02/introducing-razor.aspx).

-   Having support for **Multiple View Engines** i.e. *Web Forms* view engine, *Razor* or open source. You can follow here for a detailed comparison on difference between [WebForm View Engine and Razor View Engine](http://www.webdevelopmenthelp.net/2014/10/aspx-view-engine-vs-razor-view-engine.html).

-   **Controller improvements** like *ViewBag* dynamic property and *ActionResults* Types etc. Dynamic property is a new feature introduced in C# 4.0. ViewBag being a dynamic property has an advantage over ViewData that it doesn't require checking NULL values. For detailed difference between ViewBag and ViewData can be found [here](http://www.webdevelopmenthelp.net/2014/06/asp-net-mvc-pass-data-controller-view.html).

-   **Unobtrusive *JavaScript*** approach that actually separates the functionality from presentation layer on a web page.

-   Improved **Dependency Injection** with new *IDependencyResolver.*

-   **Partial page output caching**.

**ASP.NET MVC 4**

-   ***ASP.NET Web API***, a framework that simplifies the creation of *HTTP services* and serving a wide range of clients. Follow to create your first [ASP.NET Web API service](http://www.webdevelopmenthelp.net/2013/09/3-simple-steps-to-create-your-first-asp-net-web-api-service.html).

-   **Adaptive rendering** and other look-n-feel improvements to Default Project Templates.

-   A truly **Empty Project Template**.

-   Based on jQuery Mobile, new **Mobile Project Template** introduced.

-   Support for adding controller to other project folders also.

-   Task Support for **Asynchronous Controllers**.

-   Controlling [Bundling and Minification](http://www.asp.net/mvc/tutorials/mvc-4/bundling-and-minification) through web.config.

-   Support for **OAuth and OpenID** logins using *DotNetOpenAuth* library.

-   Support for ***Windows Azure SDK* 1.6** and new releases.

 

**ASP.NET MVC5**

[**Creating your first ASP.NET MVC 5 Application in 4 simple steps**](http://www.webdevelopmenthelp.net/2014/02/building-your-first-asp-net-mvc5-application-in-4-simple-steps.html)

-   **ASP.NET Identity** for authentication and identity management. Thesedays, modern applications are developed for broader range of clients such as web, mobile in mind. Also, users are actively using their social identities from various social channels like facebook, youtube, twitter etc. ASP.NET Identity is a new Membership system to handle authentication and authorization for variety of clients as well as using user's existing social identities.

-   **Authentication Filters** for authenticating user by custom or third-party authentication provider.

-   With the help of **Filter overrides**, we can now override filters on a method or controller.

-   **Bootstrap** replaced the default MVC template.

-   **Attribute Routing** is now integrated into MVC5. Basically, MVC Routing is an excellent way to create human friendly and Search Engine Optimized URLs. You can easily get [understanding about Routing in ASP.NET MVC](http://www.webdevelopmenthelp.net/2014/03/routing-in-asp-net-mvc.html) here. Attribute based routing enables us to define routes along with action methods as follows:

*  \[Route("Students/{id}")\]*

*  public ActionResult GetStudentById(string id)*

*{        *

*           // code logic here.        *

*           return View();*

*}*

**ASP.NET MVC6 \| ASP.NET vNext**

-   **Single Programming Model** for ASP.NET MVC and ASP.NET Web API.

-   Optimized for **Cloud Computing**.

-   Supporting **side by side deployment** of runtime and framework along with application.

-   Out of the box support for **dependency injection**.

-   vNext is **Open Source** and supports running on multiple platforms including Linux and Mac.

-   New **JSON-based** project Extension.

-   In order to dynamically compile code, **Roslyn compiler** is used.\
    For details on new features in **ASP.NET vNext**, follow [here](http://www.webdevelopmenthelp.net/2015/06/features-of-asp-net-vnext.html).

Hopefully, this article will help you in comparing core features of ASP.NET MVC in different versions.

 

*Aus \<<http://www.webdevelopmenthelp.net/2014/02/asp-net-mvc3-vs-mvc4-vs-mvc5.html>\>*

 

 

 

Working with Form Data

Mittwoch, 1. Juli 2015

12:35

Code:

**public class FormKeyValuePair**\
{\
**public** string Key\
{\
**get**;\
**set**;\
}\
**public** string Value\
{\
**get**;\
**set**;\
}\
}\
**public partial class FormData** : System.Web.UI.Page\
{\
**protected void** Page_Load(object src, EventArgs args)\
{\
**if** (Request.HttpMethod == \"POST\")\
{\
DataBind();\
}\
}\
**public** IEnumerable\<FormKeyValuePair> GetFormData()\
{\
var keys = Request.Form.Keys.Cast\<string>().Where(k => !k.StartsWith(\"\_\_\"));\
**foreach** (string key **in** keys)\
{\
**yield return new** FormKeyValuePair { Key = key,\
Value = Request.Form\[key\]\
};\
}\
}\
}

 

It may seem a little odd, but the HtmlForm control that represents server-side form elements doesn't provide access to the form data. Instead, we have to use the **Request.Form** property, which returns a NameValueCollection object (which is defined in the System.Collections.Specialized namespace).

 

You can also use this technique to create a set of buttons and figure out which one the user clicked---the trick is

to assign all of the buttons the same name value and vary the value attributes. You can use this approach to support

multiple groups of buttons by using different name values

 

e.g\
\...

\<input type=\"hidden\" name=\"consent\" value=\"false\" />

\<input type=\"checkbox\" name=\"consent\" value=\"true\" />

\...

 

 

Request Validation

Mittwoch, 1. Juli 2015

12:44

Code

\<div>Enter some HTML:\<input name=\"html\" />\</div>

By default, ASP.NET checks forms when they are posted to make sure that the user isn't trying to push dangerous

strings into the application, a process known as request validation.

 

See [Input](onenote:#Request%20Validation&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={D57C4AB5-6DCD-4384-A12B-43435AF71668}&object-id={57E6CF26-2FC4-01EF-3316-C99291693A06}&32&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet%20Schule/ASP%20Net.one)

 

# WHAT IS DANGEROUS INPUT?

Dangerous input is any string of characters that a browser would interpret as valid HTML elements, rather than

as content. Dangerous input can be entered accidentally, but it is usually an attempt to subvert the application

in some way. The most common type of subversion is Cross-Site Scripting (known as XSS) in which a script

element is supplied as input to the application in the hope that the application will displayed the contents of the

input in the response, ideally in a response to a different user. Web browsers will execute the JavaScript code

in the script element in the belief that it is a legitimate part of the HTML document. There are different types of

XSS attack, but the one we see most frequently is request hijacking, where the request is sent to the attacker's

server, either to capture security credentials or to steal the session cookie so that the attacker can create

requests that appear to be part of the user's current session (this is often referred to as session impersonation).

A quick test for vulnerability is to enter \<script>alert(\'XSS\')\</script> into the input fields in a form and

submit the form to the server. If the browser displays a popup alert box when you request the Web Form that

displays the entered values, then you have a problem. This isn't an exhaustive test, but it is a good starting point.

We demonstrate request hijacking later in the chapter.

 

 

## How to solve this:

### Using Eager Request Validation

 

In web.config

\<configuration>

\<system.web>

\<compilation debug=\"true\" targetFramework=\"4.5\" />

\<httpRuntime targetFramework=\"4.5\" **requestValidationMode=\"4.0\"** />

\</system.web>

\</configuration>

 

### Using Lazy Request Validation

One of the benefits of using lazy validation is that we can work with unvalidated data, which is useful when

we need to be able to accept HTML fragments from the user. We access the unvalidated form data using the

HttpRequest.Unvalidated.Form collection.

 

\<configuration>

\<system.web>

\<compilation debug=\"true\" targetFramework=\"4.5\" />

\<httpRuntime targetFramework=\"4.5\" **requestValidationMode=\"4.5\"** />

\</system.web>

\</configuration>

 

**protected void** Page_Load(object sender, EventArgs e)\
{\
**if** (Request.HttpMethod == \"POST\")\
{\
**try**\
{\
nameResult.InnerText = Request.Form\[\"name\"\];\
}\
**catch** (HttpRequestValidationException)\
{\
nameResult.InnerText = \"Dangerous data!\";\
}\
}\
}

###  

### Request Validation in Controls (with lazy...)

When using lazy validation, we can also disable validation for individual controls by using the

ValidationRequestMode attribute

// Disable Validation == Dangerous

\<asp:TextBox ID=\"name\" runat=\"server\" ValidateRequestMode=\"Disabled\" />

 

 

# Tip 

Lazy validation is the default when the Web.config file doesn't specify a requestValidationMode attribute.

 

# Displaying Dangerous Data (see [Using Lazy Request Validation](onenote:#Request%20Validation&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={D57C4AB5-6DCD-4384-A12B-43435AF71668}&object-id={57E6CF26-2FC4-01EF-3316-C99291693A06}&90&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet%20Schule/ASP%20Net.one))

\<div>The HTML you entered was: \<%= Request.Unvalidated.Form\[\"html\"\] %>\</div>

 

Client-Side Development

Mittwoch, 1. Juli 2015

13:50

We explain the bundles feature for managing scripts and style sheets,

show you how to use the Web API feature to create web services and demonstrate model binding can be used

to drive client-side form data validation.

 

 

 

## ASP.Net Bundles feature

It can simplify the management and maintenance of the script files and style sheets that an application uses. Bundles can also be used to optimize the requests that a browser has to make in order to get script files and style sheets.

 

### Managing Minification

Most JavaScript libraries contain two files. The first is an uncompressed version that is easy to read and that you

can use to debug client-side code problems. The other file is compressed (or minified) to reduce size. It isn't really

compressed in the sense that the word is usually used, but all of the whitespace is removed and meaningful variable

and function names are replaced with short alphanumeric names. The convention is that minified files contain .min in their name

 

### Using Bundles

The bundles feature is new to ASP.NET 4.5, and it helps manage the problems we described in the previous section.

A bundle is a set of files that we treat as a single unit and that automatically deals with file versions and switching

between the uncompressed and minified version of files.

 

#### *Preparing the Project for Bundles*

Bundles are configured when the application first starts. So in Global.asx we register the bundle.

 

See: [Bundle Code](onenote:#Client-Side%20Development&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={BE44AD00-6F5E-4B19-A7E8-AB729F8104EB}&object-id={3233F32E-630B-0A60-0E93-1EB52566B396}&72&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet%20Schule/ASP%20Net.one) and [Applying a Script Bundle](onenote:#Client-Side%20Development&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={BE44AD00-6F5E-4B19-A7E8-AB729F8104EB}&object-id={3233F32E-630B-0A60-0E93-1EB52566B396}&74&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet%20Schule/ASP%20Net.one)

 

#### *Creating a Style Bundle*

Bundles can also be used for CSS style sheets. Dealing with style sheets isn't as complex or problematic as dealing

with JavaScript. The main issue we face is the need to ensure that the right style sheets are applied to a Web Form.

As the styles used by a project become more complex and span more and more files, the amount of work needed to

keep the link elements in Web Forms up-to-date becomes a burden---and it is very easy to omit a file or mistype a file

name.

 

See [Creating a Style Bundle](onenote:#Client-Side%20Development&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={BE44AD00-6F5E-4B19-A7E8-AB729F8104EB}&object-id={3233F32E-630B-0A60-0E93-1EB52566B396}&A5&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet%20Schule/ASP%20Net.one)

 

#### *Using Bundling Optimizations*

 

Bundles are useful as a management and maintenance tool because they free us of the tedious work of keeping

script and link elements updated. But they have another trick as well---they can optimize the content sent to the

browser. There are two ways to optimize bundles. The first is local optimization and the second is the use of a

Content Delivery Network (CDN).

 

#### *Using Local Optimization*

Web.config

\<configuration>

\<system.web>

\<compilation **debug=\"false\"** targetFramework=\"4.5\" />

\<httpRuntime targetFramework=\"4.5\" />

\</system.web>

\</configuration>

 

##### Fixing the File Duplication Issue

 

The first problem we have to deal with is that enabling optimizations disables the feature that detects files referenced

in multiple bundles. You can see the effect of this in the profiler, where two URLs are requested for JavaScript files:

 

<http://localhost:63223/bundle/jquery?v=37cfAnNlsc0DRT6NbRj2m9jH9p2KI8RM1_wA0IiL9AQ1>

<http://localhost:63223/bundle/jqueryui?v=Fe-fsVpEKFt3H04DJcBWMZHKgQrUqzCWpQybW3Z8y_U1>

 

These URLs reference the name of the bundle and include a unique version identifier that allows content to be

cached by the browser without preventing newer versions of the bundles from being deployed. For our purposes,

it means that the minified content of the jquery-1.8.2.js file is being sent to the browser twice---once on its own

and once concatenated with the minified content of the jQuery UI file

 

#### *Fixing the Relative Image Issue*

If you look closely at the profile results for the optimized request, you will notice that the last request resulted in a 404

error message indicating that the requested file was not found. This request is for an image file that jQuery UI uses to

add a visual effect to buttons.

![Computergenerierter Alternativtext: Red Gr n Blue ](./assets/media/image8.png){width="2.9715277777777778in" height="0.9055555555555556in"}

 

## Bundle Code

**public class Global** : System.Web.HttpApplication\
{\
**protected void** Application_Start(object sender, EventArgs e)\
{\
BundleConfig.RegisterBundles(BundleTable.Bundles);\
}\
}

 

**public class BundleConfig**\
{\
**public static void** RegisterBundles(BundleCollection bundles)\
{\
*// bundles will be defined here*\
Bundle jquery = **new** ScriptBundle(\"\~/bundle/jquery\").Include(\"\~/Scripts/jquery-{version}.js\");\
Bundle jqueryui = **new** ScriptBundle(\"\~/bundle/jqueryui\").Include(\"\~/Scripts/jquery-{version}.js\",\"\~/Scripts/jquery-ui-{version}.js\");\
bundles.Add(jquery);\
bundles.Add(jqueryui);\
}\
}

 

## Applying a Script Bundle

\<head runat=\"server\"\>

\<title>\</title>

\<link rel=\"stylesheet\" href=\"MainStyles.css\" />

\<link rel=\"stylesheet\" href=\"ErrorStyles.css\" />

\<link rel=\"stylesheet\" href=\"Content/themes/base/jquery-ui.css\" />

**\<%: System.Web.Optimization.Scripts.Render(\"\~/bundle/jqueryui\") %>**

\<script>

\$(document).ready(function () {

\$(\'input\[type=submit\]\').button();

});

\</script>

\</head>

 

\<head>

\<title>\</title>

\<link rel=\"stylesheet\" href=\"MainStyles.css\" />

\<link rel=\"stylesheet\" href=\"ErrorStyles.css\" />

\<link rel=\"stylesheet\" href=\"Content/themes/base/jquery-ui.css\" />

**\<script src=\"/Scripts/jquery-1.8.2.js\"\>\</script>**

**\<script src=\"/Scripts/jquery-ui-1.10.2.js\"\>\</script>**

\<script>

\$(document).ready(function () {

\$(\'input\[type=submit\]\').button();

});

\</script>

\</head>

 

## Creating a Style Bundle

**public static void** RegisterBundles(BundleCollection bundles)\
{\
Bundle jquery = **new** ScriptBundle(\"\~/bundle/jquery\").Include(\"\~/Scripts/jquery-{version}.js\");\
Bundle jqueryui = **new** ScriptBundle(\"\~/bundle/jqueryui\").Include(\"\~/Scripts/jquery-{version}.js\",\"\~/Scripts/jquery-ui-{version}.js\");\
Bundle basicStyles = **new** StyleBundle(\"\~/bundle/basicCSS\").Include(\"\~/MainStyles.css\", \"\~/ErrorStyles.css\");\
Bundle jqueryUIStyles = **new** StyleBundle(\"\~/bundle/jqueryUICSS\").IncludeDirectory(\"\~/Content/themes/base\", \"\*.css\");\
bundles.Add(jquery);\
bundles.Add(jqueryui);\
bundles.Add(basicStyles);\
bundles.Add(jqueryUIStyles);\
}

// Adding a Style bundle to the head element

\<head runat=\"server\"\>

\<title>\</title>

**\<%: System.Web.Optimization.Styles.Render(\"\~/bundle/basicCSS\",**

**\"\~/bundle/jqueryUICSS\") %>**

\<%: System.Web.Optimization.Scripts.Render(\"\~/bundle/jquery\", \"\~/bundle/jqueryui\") %>

\<script>

\$(document).ready(function () {

\$(\'input\[type=submit\]\').button();

});

\</script>

\</head>

 

 

Web API

Mittwoch, 1. Juli 2015

14:03

> ASP.NET Framework has included a range of different technologies for creating **web services** over the years, and each
>
> one has been tailored to the prevailing development practice at the time. ASP.NET 4.5 includes the **Web API feature**,
>
> which can be used **to create simple and light-weight web services that are closely modeled on the nature of HTTP, using**
>
> **the different kinds of HTTP methods (GET, PUT, POST, DELETE, and so on) to specify different data operations**. This is the
>
> foundation for the Representation State Transfer (REST) style of Web API, known more commonly as a RESTful service,
>
> where an operation is specified by the combination of a URL and the HTTP method used to request it.
>
>  
>
> Transport Objects = JSON (see [JSON](onenote:JSON.one#JSON&section-id={7AFD1489-21F9-4932-A30F-C788A63753B3}&page-id={921F78DB-7506-49D0-9E0E-08D57F5474C9}&object-id={8046F570-A77C-4E61-91D3-2857805EFA6D}&10&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet%20Schule)) and REST (Style of API) => Representation State Transfer => RESTful service.
>
>  
>
> Web API controllers are not accessible by default, so we have to use the URL routing feature to map URL onto the class. See [Navigation / URL Routing / Paths](onenote:#Navigation%20\%20URL%20Routing%20\%20Paths&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={B4D8DB19-7FBD-4D7A-82C1-0ED685E015B6}&object-id={A24E8BAD-9D3B-0DEA-127D-C2762F4F2560}&10&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet%20Schule/ASP%20Net.one)
>
>  

## Hint:

> To access Data from JavaScript or any else client site Scripting you can use WEB Api ( WebServices ) with REST and JSON... :-) Nice and simple
>
>  

## Naming Convention 

> \<nameClass>Controller.cs

## Note

> REST is a style of API rather than a well-defined specification. There is disagreement about what exactly makes
>
> a web service RESTful. One point of contention is that purists do not consider web services that return JSON as being
>
> RESTful. Like any disagreement about an architectural pattern, the reasons for the disagreement are arbitrary and dull.
>
> We try to be pragmatic about how patterns are applied, and JSON services are RESTful as far as we are concerned.

 

 

Lifecycles and Context

Sonntag, 21. Juni 2015

20:09

Dazu muss die Global.asax angeschaut werden.

 

Dort werden alle Globalen einstellungen (Routing u.a ) verwaltet u.a. SessionStart, Application begin Request u.a.

 

 

## Understand Global.asax

The Categories of Methods Defined by the Global Application Class

+---------------------------------+----------------------------------------------------+
| Methods                         | Description                                        |
+=================================+====================================================+
| Application_Start               | These methods deal with the application lifecycle. |
|                                 |                                                    |
| Application_End                 |                                                    |
+---------------------------------+----------------------------------------------------+
| Application_BeginRequest        | These methods handle request lifecycle events.     |
|                                 |                                                    |
| Application_AuthenticateRequest |                                                    |
|                                 |                                                    |
| Application_Error               |                                                    |
+---------------------------------+----------------------------------------------------+
| Session_Start                   | These methods handle module events.                |
|                                 |                                                    |
| Session_End                     |                                                    |
+---------------------------------+----------------------------------------------------+

 

 

 

 

![](./assets/media/image9.png){width="4.471527777777778in" height="5.377083333333333in"}

## Understanding the Request Lifecycle

 

The Request Lifecycle Events Defined by the HttpApplication Class

+---------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Name                      | Description                                                                                                                                                                                                             |
+===========================+=========================================================================================================================================================================================================================+
| BeginRequest              | Triggered by the ASP.NET Framework as the first event when a new request is received.                                                                                                                                   |
+---------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| AuthenticateRequest       | The AuthenticateRequest event is triggered when the ASP.NET Framework needs to identify the user who has made the request. When all of the event handlers have been processed, PostAuthenticateRequest is triggered.    |
|                           |                                                                                                                                                                                                                         |
| PostAuthenticateRequest   |                                                                                                                                                                                                                         |
+---------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| AuthorizeRequest          | AuthorizeRequest is triggered when the ASP.NET Framework needs to authorize the request. When all of the event handlers have been processed, PostAuthorizeRequest is triggered.                                         |
+---------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| ResolveRequestCache       | ResolveRequestCache is triggered when the ASP.NET Framework wants to try and resolve the request from cached data--- When the event handlers have been                                                                  |
|                           |                                                                                                                                                                                                                         |
| PostResolveRequestCache   | processed, PostResolveRequestCache is triggered.                                                                                                                                                                        |
+---------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| MapRequestHandler         | MapRequestHandler is triggered when the ASP.NET Framework wants to locate a handler for the request.                                                                                                                    |
|                           |                                                                                                                                                                                                                         |
| PostMapRequestHandler     | The PostMapRequestHandler event is triggered once the handler has been selected.                                                                                                                                        |
+---------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| AcquireRequestState       | AcquireRequestState is triggered when the ASP.NET Framework requires the state associated with the request (such as session state). When all of the event handlers are processed, PostAcquireRequestState is triggered. |
|                           |                                                                                                                                                                                                                         |
| PostAcquireRequestState   |                                                                                                                                                                                                                         |
+---------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| PreRequestHandlerExecute  | These events are triggered immediately before and immediately after the handler is asked to process the request.                                                                                                        |
|                           |                                                                                                                                                                                                                         |
| PostRequestHandlerExecute |                                                                                                                                                                                                                         |
+---------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| ReleaseRequestState       | ReleaseRequestState is triggered when the ASP.NET Framework no longer requires the state associated with the request. When the event handlers have been processed, PostReleaseRequestState event is triggered.          |
|                           |                                                                                                                                                                                                                         |
| PostReleaseRequestState   |                                                                                                                                                                                                                         |
+---------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| UpdateRequestCache        | This event is triggered so that modules responsible for caching can update their state.                                                                                                                                 |
+---------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| LogRequest                | LogRequest is triggered when the ASP.NET Framework wants to log details of this request. When all of the event handlers have been processed, PostLogRequest is triggered.                                               |
|                           |                                                                                                                                                                                                                         |
| PostLogRequest            |                                                                                                                                                                                                                         |
+---------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| EndRequest                | EndRequest is triggered when the ASP.NET Framework has finished processing the request and is ready to send the response to the browser.                                                                                |
+---------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| PreSendRequestHeaders     | PreSendRequestHeaders is triggered just before the HTTP headers are sent to the browser.                                                                                                                                |
+---------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| PreSendRequestContent     | PreSendRequestContent is triggered after the headers have been sent but before the content is sent to the browser.                                                                                                      |
+---------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Error                     | Error is triggered when an error is encountered---this can happen at any point in the request process.                                                                                                                  |
+---------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

# THE LIFE OF A REQUEST LIFECYCLE HTTP APPLICAT ION OBJECT

> The ASP.NET Framework will create **[multiple instances]{.underline}** of the HttpApplication class to process requests, and these instances can be reused so that they process several requests over their lifetime.
>
>  
>
> The ASP.NET Framework has complete freedom to create HttpApplication instances as and when they are required and to destroy them when they are no longer needed.
>
>  
>
> This means that your global application class must be written so that multiple instances can exist at the same time and that these instances can be used to process several requests before they are destroyed.
>
>  
>
> The only thing you can rely on is that an instance will be used to process one request at a time, meaning that you only have to worry about concurrent access to shared data objects.

 

Understand Modules and Handlers

Montag, 22. Juni 2015

16:30

 

# Beschreibung

A **[module]{.underline}** is a class that implements the System.Web.IHttpModule interface and that handles one or more of the request lifecycle events. They can look at headers, setup state data, authenticate users\...

 

**[Handlers]{.underline}** generate the response for the client.

Any class that implements the System.Web.IHttpHandler interface can act as a target for incoming HTTP requests,

and the details of how to respond to that request are left entirely to the handler implementation. e.g. CodeBehind Class managing = Custom Handler

 

## MODULES VERSUS HANDLERS

> Modules and handlers are both classes that implement simple interfaces, operate on the same context objects,
>
> and participate in the request lifecycle. So, how do you choose which to use when you want to customize the way
>
> requests are handled?
>
>  
>
> The answer is pretty simple. If you want to customize the way that a response for an existing web application
>
> framework, such as Web Forms, is processed, then use a module. Modules are simple and quick to build. You can
>
> use them to prepare a request before it is passed to the handler and tweak the response that is generated before
>
> it is sent back to the client.
>
>  
>
> On the other hand, if you want to create a new kind of web application stack, such as a new file format for
>
> producing dynamic HTML or some kind of exciting web service, then you should use a handler e.g. WebForm generates a C# class bound to website = Handler.
>
>  
>
> Put another way, modules prepare requests for handlers and handlers generate responses for clients. Don't generate
>
> responses in modules and don't implement request features (like state management and security) in handlers.

 

 

 

The lifecycle events indicate how far in the processing pipeline a request has reached, which allows a

module to respond just at the points that are relevant to its functionality. A module can perform three kinds of work:

it can prepare the request for a later stage of processing, it can update the state of the application, or it can generate

some part of the response.

 

z.B. Special Authorization, Timing order Logging .. Lohnt sich wenn logik in mehreren Projecten genutzt werden muss. => C# Class Lib wobei Reference auf System.Web vorhanden sein sollte.

 

Logging => zB.b HandleEvent().... System.Diagnostic.Debug.WriteLine(\",....\");

 

Diese Module bzw Handlers können in Class Bibliotheken geschrieben werden oder mit VS Template. Wenn als Class dann gilt das folgende. :-)

Module können folgendermaßen registriert werden.

-   in der web.config =>

> \<system.webServer>
>
> **\<modules>**
>
> **\<add name=\"ParamsProtection\" type=\"Events.ParamsModule\"/>**
>
> **\</modules>**
>
> \</system.webServer>\
> oder
>
> \<system.webServer>
>
> **\<handlers>**
>
> **\<add name=\"CustomJSON\" path=\"\*.json\" verb=\"GET\" type=\"Handlers.CustomHandler\"/>**
>
> **\<add name=\"CustomText\" path=\"Time.text\" verb=\"\*\" type=\"Handlers.CustomHandler\"/>**
>
> **\</handlers>**
>
> \</system.webServer>

-   Register themself with ASP.Net Framework. (executed right before Application_Start)\
    Create a class that contains statements we want to execute.\
     

> \[assembly: PreApplicationStartMethod(typeof(CommonModules.ModuleRegistration), \"RegisterModules\")\]\
> **namespace CommonModules**\
> {\
>         **public class ModuleRegistration**\
>         {\
>                 **public static void** RegisterModules()\
>                 {\
>                         Type\[\] moduleTypes = {**typeof**(CommonModules.TimerModule),**typeof**(CommonModules.LogModule)};\
>                         **foreach** (Type t **in** moduleTypes)\
>                         {\
>                                 HttpApplication.RegisterModule(t);\
>                         }\
>                 }\
>         }\
> }\
> \
> Dann nur die C# classlib als Reference in das zu benutzende Project

## Modules

![Machine generated alternative text: Application Starts Application Exits Global Application Class Instantiated Modules Instantiated Request Lifecycle Events (BeginRequest, AuthenticateRequest, Handler Executed Request Lifecycle Events (\..., EndRequest, PreSendRequestHeaders, PreSendRequestContent) Global Application Class Instantiated ication_Start Request Received Response Sent Application_End ](./assets/media/image10.png){width="6.670138888888889in" height="5.754861111111111in"}

 

 

 

## Handler Events

![Machine generated alternative text: Application Starts Global Application Class Instantiated Request Received Response Sent Application_End Global Application Class Instantiated Modules Instantiated Request Lifecycle Events BeginRequest AuthenticateRequest Handler Instantiated/Reused Request Lifecycle Events PostMapRequestHandler Handler ProcessRequest Called Request Lifecycle Events PostRequestHandlerExecute P reSendRequestContent Application Exits ](./assets/media/image11.png){width="6.4625in" height="7.679166666666666in"}

 

**Tip**

The handler is the only part of the request handling that is specific to Web Forms---and this is how the ASP .NET Framework is able to support alternative frameworks such as MVC. As you'll learn in Chapter 15, handlers are set up based on the kinds of files they can process.

 

The MVC Framework simply has its own handler that deals with MVC files, such as those with the CSHTML file type. Adam's Pro ASP.NET MVC Framework book, also published by Apress, contains more details.

 

 

Hint:

Modules are instantiated when a new HttpApplication object is created. Each HttpApplication gets its own set of module objects. The Init method is called when the module is instantiated and, like the HttpApplication object it is associated with, the module may be used to process multiple requests (although only one request at a time). When writing module code, remember that there may be multiple instances of the module at any moment and take care to ensure that there is no unintended consequence of handling multiple requests (so, for example, make sure that you reset the state of your module when you receive the BeginRequest event and not in the Init method).

 

 

Sample Modules

Freitag, 26. Juni 2015

14:35

 

## Debug Logging

Hier ein Beispiel wie man Urls die angefordert werden loggen kann.

 

Und nicht vergessen, diese Module dann in der Web.config zu registrieren.

 

\<modules>

\<add name=\"Simple\" type=\"PathsAndUrls.SimpleModule\"/>

\</modules>

 

 

Code:

**public class SimpleModule** : IHttpModule\
{\
*/// \<summary>*\
*/// You will need to configure this module in the Web.config file of your*\
*/// web and register it with IIS before being able to use it. For more information*\
*/// see the following link: <http://go.microsoft.com/?linkid=8101007>*\
*/// \</summary>*\
\
**public void** Init(HttpApplication app)\
{\
app.BeginRequest += (src, args) => ProcessRequest(app);\
}\
**private void** ProcessRequest(HttpApplication app)\
{\
*// hier wird der Pfad ausgewertet und zu einer anderne Seite gesprungen*\
**if** (app.Request.FilePath == \"/Test.aspx\")\
{\
app.Server.Transfer(\"/Content/RequestReporter.aspx\");\
}

WriteMsg(\"URL requested: {0} {1}\", app.Request.RawUrl, app.Request.FilePath);\
}\
**private void** WriteMsg(string formatString, **params** object\[\] vals)\
{\
Debug.WriteLine(formatString, vals);\
}\
**public void** Dispose()\
{\
*// nothing to dispose*\
}\
}

 

 

## Path rewriting

**public class PathModule** : IHttpModule\
{\
*/// \<summary>*\
*/// You will need to configure this module in the Web.config file of your*\
*/// web and register it with IIS before being able to use it. For more information*\
*/// see the following link: <http://go.microsoft.com/?linkid=8101007>*\
*/// \</summary>*\
\
**private static readonly** string\[\] extensions = { \".aspx\", \".ashx\" };

 

**public void** Init(HttpApplication app)\
{\
app.BeginRequest += (src, args) => HandleRequest(app);\
}

 

**private void** HandleRequest(HttpApplication app)\
{\
**if** (app.Request.CurrentExecutionFilePathExtension == String.Empty)\
{\
string target = **null**;\
string vpath = app.Request.CurrentExecutionFilePath;\
**if** (vpath == \"/\")\
{\
target = \"/Default.aspx\";\
}\
**else**\
{\
**foreach** (string ext **in** extensions)\
{\
**if** (File.Exists(app.Request.MapPath(vpath + ext)))\
{\
target = vpath + ext;\
**break**;\
}\
}\
}\
**if** (target != **null**)\
{\
app.Context.RewritePath(target);\
}\
}\
}

 

**public void** Dispose()\
{\
*// do nothing*\
}\
}

### Web.config

\<modules>

\<add name=\"Rewriter\" type=\"PathsAndURLs.PathModule\"/>

\</modules>

 

 

Sample Handler / Eigene Routing Engine

Freitag, 26. Juni 2015

14:30

 

Als Handler könnte man sich ein automatisches System vorstellen, das je nach Url nun default Seiten aufruft. d.h. wenn keine Segemente vorhanden sind die auf eine Seite zeigen.. Das ist sozusagen ein eigene Simple Routing Engine

 

Und nicht vergessen das wir diesen Handler nun in webConfig registrieren müssen.

\<handlers>

\<add name=\"ExtensionLess\" path=\"\*.\" verb=\"\*\" type=\"xxx.yyyHandler\"/>

\</handlers>

 

 

Code:

**public class ExtensionlessHandler** : IHttpHandler\
{\
        **public void** ProcessRequest(HttpContext context)\
        {\
                context.Response.Write(\"\<p>Expressionless Handler\</p>\");\
                string vpath = context.Request.Path;\
                \
                **if** (vpath == \"/\")\
                {\
                        context.Server.Transfer(\"/Default.aspx\");\
                } **else if** (File.Exists(context.Request.MapPath(vpath + \".aspx\")))\
                {\
                        context.Server.Transfer(vpath + \".aspx\");\
                } **else** {\
                        context.Response.StatusCode = 404;\
                        context.ApplicationInstance.CompleteRequest();\
                }\
        }\
        \
        **public** bool IsReusable\
        {\
                **get** { **return false**; }\
        }\
}

 

 

Understanding Context Objects

Montag, 22. Juni 2015

16:34

 

> We usually need to do more than just record that we have received an event (although that can be important when
>
> debugging a problem).
>
>  
>
> *[Details about the state of the application, the request being handled, and the response being constructed are built up using context objects]{.underline}*.
>
>  
>
> We need to use these objects in our global application class if we want to act in any meaningful way when we receive a lifecycle event.
>
>  
>
>  

## Context Objects:

+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| HttpContext     | The HttpContext class is used to track the state of the request from start to finish, and it acts as a gateway to all of                                                                           |
|                 |                                                                                                                                                                                                    |
|                 | the information available about that request, including the HttpRequest and HttpResponse objects                                                                                                   |
+=================+====================================================================================================================================================================================================+
| HttpApplication | z,b Zugriff darauf => Context.ApplicationInstance                                                                                                                                                  |
+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| HttpRequest     | The HttpRequest object describes the HTTP request that is being processed. We will keep returning to the HttpRequest class throughout the book, especially when it comes to dealing with form data |
+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| HttpResponse    | The HttpResponse object represents the response as it is being constructed and provides methods and properties that let you customize it.                                                          |
+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

>  
>
>  

## Completing Requests

> CompleteRequest();

 

Page LifeCycle

Donnerstag, 25. Juni 2015

12:43

 

The Page class provides methods and properties to help you generate a response for a Web Form. This includes

managing the elements and controls defined by your Web Form markup. The Page class has a lot of features and, in

this section, we are going to show you the general-purpose members that it defines.

 

 

## GET AND POST: PICK THE RIGHT ONE

Just because the IsPostBack property doesn't differentiate between GET and POST requests doesn't mean that you should treat them as being the same in your application.

 

The rule of thumb is that GET requests should be used for all read-only information retrieval, while POST requests should be used for any operation that changes the application state. In standards-compliance terms, GET requests are for safe interactions (having no side effects besides information retrieval), and POST requests are for unsafe interactions (making a decision or changing something). These conventions are set by the World Wide Web Consortium (W3C), at [www.w3.org/Protocols/rfc2616/rfc2616-sec9.html](http://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html).

 

GET requests are addressable---all the information is contained in the URL, so it's possible to bookmark and link to these addresses. Do not use GET requests for operations that change state. Many web developers learned this the hard way in 2005, when Google Web Accelerator was released to the public. This application pre-fetched all the content linked from each page, which is legal within the HTTP because GET requests should be safe.

 

![Computergenerierter Alternativtext: PreRequestHandlerExecute PAGE LIFECYCLE Prelnit Init InitComplete Pre Load Load Load Custom Events LoadComplete PreRender - PreRender PreRenderComplete Save StateComplete Render Method Called Render Method Called • • Unload Unload PostRequestHandlerExecute ](./assets/media/image12.png){width="5.726388888888889in" height="7.6506944444444445in"}

 

Managing Request Execution

Donnerstag, 25. Juni 2015

12:46

# Using URL Redirection

 

![](./assets/media/image13.png){width="6.0in" height="2.3208333333333333in"}

 

There are 2 ways of redirection

1.  Status code 302 => temporary Redirection (Browser should always ask for default.aspx(above))

2.  Status code 301 => Permanent Redirection

 

## HowTo:

Use HttpResponse for Redirection

-   Response.Redirect(\"/SecondPage.aspx\", false);

-   Oder manuell\
    Response.RedirectLocation = \"/CurrentTimeHandler.ashx\";

> Response.StatusCode = 301;
>
> Context.ApplicationInstance.CompleteRequest();
>
>  

Wobei die letztere Version kein Vorteil bringt...

We are going to show you techniques for disrupting the normal flow of a request. There are good

reasons for wanting to disrupt the flow---to direct the user to another page, for example, or to pre-empt the default

handler selection process for selected requests. Each of the techniques we describe changes some aspect of the way

that the request is handled and we explain the use of each one, the reasons why you might find it useful, and

its limitations.

 

 

Caching

Freitag, 26. Juni 2015

10:25

 

## WebSite Caching

Dazu in Webseite den folgenden Eintrag\
\<%@ OutputCache Duration=\"60\" VaryByParam=\"none\" %>

 

Wobei das bedeuten würde das die seite 60 secunden im Cache bleibt. VaryByParam kann z.B. quantity;price beinhalten was bedeutet das wenn sich einer dieser beiden werte ändert der cache nun nicht gezogen wird bzw wenn man dann wieder werte eingibt die gecached sind, dann wird er Cache gezogen :-)

 

 

Navigation / URL Routing / Paths

Dienstag, 21. April 2015

14:58

 

> Routing kann mit verschiedenen Wegen implementiert werden. Der Weg hier ist der einfachste.
>
> Siehe aber auch [Sample Handler / Eigene Routing Engine](onenote:#Sample%20Handler%20\%20Eigene%20Routing%20Engine&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={91105EC0-F92F-4D82-A97A-507245548CEB}&object-id={8150612A-8B3A-0D3E-0AE6-D38503CF543F}&12&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet%20Schule/ASP%20Net.one) (Handler)
>
>  
>
> Path(s) can be virtual or Physical.

  ------------------------------------------------------------------------------------------------------------
  Physical      c:\\myProject\\Content\\mywebsite.html
  ------------- ----------------------------------------------------------------------------------------------
  Virtual       [Http://localhost:xxxx/Content/mywebsite.html](Http://localhost:xxxx/Content/mywebsite.html)

  ------------------------------------------------------------------------------------------------------------

>  
>
> Mapping will be done with routing.
>
> \~ => relative Path to root directory
>
>  
>
> Das kann auch selber gebaut werden mit Handlern und Modulen.
>
> Siehe [Sample Handler / Eigene Routing Engine](onenote:#Sample%20Handler%20\%20Eigene%20Routing%20Engine&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={91105EC0-F92F-4D82-A97A-507245548CEB}&object-id={8150612A-8B3A-0D3E-0AE6-D38503CF543F}&12&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet%20Schule/ASP%20Net.one) und [Path rewriting](onenote:#Sample%20Modules&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={9CF07D6B-7D83-466A-B2E5-3EF5001E611E}&object-id={407D44EA-846E-0941-05CF-5E9161C639BE}&39&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet%20Schule/ASP%20Net.one)
>
>  

## Using the Friendly URLs Package

> Microsoft has developed a NuGet package that uses the URL routing feature to support friendly URLs
>
> Microsoft.AspNet.FriendlyUrls\
>  
>
> To set up the FriendlyUrls library, we need to add a global application class to the project and use the
>
> Application_Start method to initialize the routing configuration
>
>  
>
> \-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--
>
>  
>
> **HttpRequest** führt Informationen über Beschaffung und Verwaltung von Pfaden.
>
>  
>
> Normales Routing über namen sind u.U problematisch da bei Änderungen alle Bezüge in den Sourcen geändert werden müssen.
>
>  
>
> Hiermit müssen dann keine Namen angegeben werden.
>
>  
>
> Routing kann man über *RouteTable.Routes* auslesen bzw anpassen. RouteTable gehört zum ASP.Net Framework
>
>  

## Lösung:

1.  Eine Configurations Klasse erstellen. !!! Reihenfolge ist wichtig

2.  In global.asax initialisieren

>  

## Code Config Class:

> Richtet \"\" und \"list\" so ein das es auf listing.aspx zeigt
>
>  
>
> Damit können Url(s) wie die folgende aufgerufen werden.
>
>  
>
> <http://localhost:2000/>
>
> <http://localhost:2000/list>
>
> <http://localhost:2000/list/2>
>
>  
>
>  
>
> Hint: NameSpace ausmarkiert, da es in global.asax eingebunden werden soll und damit keinen extra Namespace haben soll\... Muss aber nicht so gemacht werden
>
>  

### Code:

> **//namespace SportsStore.App_Start**\
> {\
> **using System.Web.Routing**;
>
> **public class RouteConfig**\
> {\
> **public static void** RegisterRoutes(RouteCollection routes)\
> {
>
> routes.MapPageRoute(null,\"list/{page}\",\"\~/Pages/Listing.aspx\");
>
> routes.MapPageRoute(**null**, \"\", \"\~/Pages/Listing.aspx\");\
> routes.MapPageRoute(**null**, \"list\", \"\~/Pages/Listing.aspx\");\
> }\
> }\
> }
>
>  

### Html aufruf dieser route

> <http://localhost:53506/list/2>
>
>  

### Routing mit angabe von einer variable

> (page) => routing segment variable
>
>  
>
> routes.MapPageRoute(**null**, \"list/{page}\", \"\~/Pages/Listing.aspx\");
>
>  
>
>  

## Registrierung Route in Global.asax:

>  
>
> **protected void** Application_Start(object sender, EventArgs e)\
> {\
> RouteConfig.RegisterRoutes(RouteTable.Routes);\
> }
>
>  

# Glossar

RouteData => Zugriff von Code auf Routing Daten

 

## Manipulating Paths

The System.Web.VirtualPathUtility class defines a set of static methods

 

## Overriding Default Documents used by IIS ( default.html, htm usw )

Web.config

\<defaultDocument enabled=\"true\"\>

\<files>

\<clear/>

\<add value=\"Content/RequestReporter.aspx\"/>

\</files>

\</defaultDocument>

 

# Tips:

 

## Auslesen wert aus routing

string currentCategory = (string)RouteData.Values\[\"category\"\] ?? Request.QueryString\[\"category\"\];

 

Oder

csLink.HRef = RouteTable.Routes.GetVirtualPath(null,\"cart\", null).VirtualPath;

 

## Route setzen mit

// Hier werden category und page gesetzt = Variables...

routes.MapPageRoute(null, \"list/{category}/{page}\",\"\~/Pages/Listing.aspx\" );

 

# Using URL Redirection

 

![Computergenerierter Alternativtext: GET Default.aspx Redirect: SecondPage.aspx GET SecondPage.aspx 200 + «Contenb Default.aspx SecondPage.aspx ](./assets/media/image13.png){width="6.0in" height="2.3208333333333333in"}

 

There are 2 ways of redirection

1.  Status code 302 => temporary Redirection (Browser should always ask for default.aspx(above))

2.  Status code 301 => Permanent Redirection

 

## HowTo:

Use HttpResponse for Redirection

-   Response.Redirect(\"/SecondPage.aspx\", false);

-   Oder manuell\
    Response.RedirectLocation = \"/CurrentTimeHandler.ashx\";

> Response.StatusCode = 301;
>
> Context.ApplicationInstance.CompleteRequest();
>
>  

Wobei die letztere Version kein Vorteil bringt...

 

 

Error Handling

Freitag, 26. Juni 2015

13:53

## GETTING IIS EXPRESS TO SERVE REMOTE REQUESTS

IIS Express only accepts local requests by default. This is fine most of the time, but it doesn't help when it comes to testing error page policies that respond differently to local and remote requests. We don't like using this kind of policy, but in this sidebar, we show you the steps we use to allow remote connections, just in case you are not obsessively following every piece of advice we give. One word of caution: don't use this technique to deliver your application to users---IIS Express is not a production application server.

 

First, we need to update the configuration that IIS Express has for our example project. Right-click on the IIS Express notification icon in the taskbar and select Show All Applications. Select the ErrorHandling project in the list and click on the link labeled Config, which opens the applicationhost.config file. Search for ErrorHandling and you will find an element like this:

\...

\<site name=\"ErrorHandling\" id=\"93\"\>

\<application path=\"/\" applicationPool=\"Clr4IntegratedAppPool\"\>

\<virtualDirectory path=\"/\" physicalPath=\"C:\\ErrorHandling\" />

\</application>

\<bindings>

\<binding protocol=\"http\" bindingInformation=\"\*:20172:localhost\" />

\</bindings>

\</site>

 

-   z.B. Allgemeine Umleitung auf eine Fehler Seite.

 

> Web.config
>
> \<configuration>
>
> \<system.web>
>
> \<compilation debug=\"true\" targetFramework=\"4.5\" />
>
> \<httpRuntime targetFramework=\"4.5\" />
>
> \<customErrors mode=\"On\" defaultRedirect=\"/Failure.html\"\>
>
> \</customErrors>
>
> \</system.web>
>
> \</configuration>

 

-   Creating a Dynamic Error Page\
     

> If you look closely at the figure, you can see that the URL to which the browser has been redirected contains a query string, as follows:
>
> <http://localhost:58486/Failure.html?aspxerrorpath=/default.aspx>
>
>  
>
> The aspxerrorpath parameter provides the URL that we requested when the error occurred, and we can use this information to create a more helpful error page by generating content dynamically using a Web Form
>
>  
>
> Web
>
> \<p>\<a href=\"\<%: Request\[\"aspxerrorpath\"\] %>\"\>Please try again.\</a>\</p>
>
> ...
>
>  

-   Redirect on certain error codes\
     

> \<system.web>
>
> \<compilation debug=\"true\" targetFramework=\"4.5\" />
>
> \<httpRuntime targetFramework=\"4.5\" />
>
> \<customErrors mode=\"On\" defaultRedirect=\"/DynamicFailure.aspx\"\>
>
> **\<error statusCode=\"404\" redirect=\"/NotFoundASP.html\"/>**
>
> \</customErrors>
>
> \</system.web>
>
>  

 

 

Working with Data Source Control

Dienstag, 7. April 2015

14:24

 

[Data Binding in ASP.Net](onenote:ASP%20Net.one#Data%20Binding%20in%20ASP.Net&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={FCA62D18-F24F-4336-9A6C-306C9045FEEF}&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet Schule)

[Data Binding Expressions](onenote:ASP%20Net.one#Data%20Binding%20Expressions&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={3B1ADB00-029B-488E-ABFE-F19A0F6FAAAF}&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet Schule)

[Using SqlDataSource](onenote:ASP%20Net.one#Using%20SqlDataSource&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={AECDB443-345C-4728-B61E-77D8AFB2EB86}&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet Schule)

[Using ObjectDataSource](onenote:ASP%20Net.one#Using%20ObjectDataSource&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={044E5544-63DF-4732-9845-A4F82685C85F}&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet Schule)

[Using EntityDataSource](onenote:ASP%20Net.one#Using%20EntityDataSource&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={BF5D556C-690C-45DB-9506-CB6E8D3FB30A}&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet Schule)

[Using QueryExtender](onenote:ASP%20Net.one#Using%20QueryExtender&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={3D26927D-1C6E-460E-AF50-EB361BBA9F34}&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet Schule)

 

Data Binding in ASP.Net

Dienstag, 7. April 2015

19:04

![](./assets/media/image14.png){width="6.245138888888889in" height="4.679166666666666in"}

Databinding and Datasource Is Build in ASP.Net

 

Data aware controls have a DataSourceID property that is used to bind a control to a Data Source Control

 

The process of getting data into controls is known as data binding---although this is a loosely defined term, and

Microsoft has applied it to different techniques and features over the years. In ASP.NET 4.5, data binding has been

enhanced through the addition of strongly typed controls.

 

 

Data Binding Expressions

Dienstag, 7. April 2015

19:04

 

-   \<%# Eval(...) %> OneWay

-   \<%# Bind(...) %> TwoWay

-   \<%# Xpath(...) %> XML

 

z.B.

 

\<%# Eval(\"FieldName\") %>

 

Oder im Repeater

 

\<td>\<%#: Item.Name %>\</td>

\<td>\<%#: Item.Category %>\</td>

\<td>\<%#: Item.Price.ToString(\"F2\") %>\</td>

 

 

Model Binding / Data Binding

Freitag, 26. Juni 2015

17:47

## GetPerson

Person model = **new** Person();\
string nameFormValue = Request.Form\[\"name\"\];\
**if** (nameFormValue == **null** \|\| nameFormValue == String.Empty)\
{\
**throw new** FormatException(\"Please provide your name\");\
}\
**else** if (nameFormValue.Length \< 3 \|\| nameFormValue.Length \> 20)\
{\
**throw new** FormatException(\"Your name must be 3-20 characters\");\
}\
**else** if (!Regex.IsMatch(nameFormValue, @\"\^\[A-Za-z\\s\]+\$\"))\
{\
**throw new** FormatException(\"Your name can only contain letters and spaces\");\
}\
**else**\
{\
model.Name = nameFormValue;\
}\
string ageFormValue = Request.Form\[\"age\"\];\
**if** (ageFormValue == **null** \|\| ageFormValue == String.Empty)\
{\
**throw new** FormatException(\"Please provide your age\");\
}\
**else**\
{\
int ageValue;\
**if** (!int.TryParse(ageFormValue, **out** ageValue))\
{\
**throw new** FormatException(\"Please provide your age in years\");\
}\
**else**\
{\
**if** (ageValue \< 5 \|\| ageValue \> 100)\
{\
**throw new** FormatException(\"Please provide an age between 5 and 100\");\
}\
**else**\
{\
model.Age = ageValue;\
}\
}\
}\
model.Cell = Request.Form\[\"cell\"\];\
model.Zip = Request.Form\[\"zip\"\];\
**return** model;

## ModelBinding

**protected void** Page_Load(object sender, EventArgs e)\
{\
**if** (IsPostBack)\
{\
DisplayPerson(GetPerson());\
}\
}

**protected** Person GetPerson()\
{\
Person model = **new** Person();\
IValueProvider provider = **new** FormValueProvider(ModelBindingExecutionContext);\
**if** (**this**.TryUpdateModel\<Person>(model, provider))\
{\
**return** model;\
}\
**else**\
{\
**throw new** FormatException(\"Could not model bind\");\
}\
}

 

**protected void** DisplayPerson(Person person)\
{\
sname.InnerText = person.Name;\
sage.InnerText = person.Age.ToString();\
scell.InnerText = person.Cell;\
szip.InnerText = person.Zip;\
}

## Model Validation Attributes

**public class Person**\
{\
\[Required(ErrorMessage = \"You must enter your name\")\]\
\[StringLength(20, MinimumLength = 3, ErrorMessage = \"Names are 3-20 characters\")\]\
\[RegularExpression(@\"\^\[A-Za-z\\s\]+\$\", ErrorMessage = \"Names are alpha characters\")\]\
**public** string Name\
{\
**get**;\
**set**;\
}\
\[Required(ErrorMessage = \"You must enter your age\")\]\
\[Range(5, 100, ErrorMessage = \"Ages are 5-100\")\]\
**public** int Age\
{\
**get**;\
**set**;\
}\
**public** string Cell\
{\
**get**;\
**set**;\
}\
**public** string Zip\
{\
**get**;\
**set**;\
}\
}

## Using a Custom Validation Method

**public class CustomChecks**\
{\
**public static** ValidationResult CheckZip(string zipCode)\
{\
**return** zipCode != **null** && zipCode.ToLower().StartsWith(\"ny\") ?\
ValidationResult.Success : **new** ValidationResult(\"Enter a NY zip code\");\
}\
}

## Handling Model Binding and Validation Errors

webSite:

**\<asp:PlaceHolder** id=\"errorPanel\" Visible=\"false\" runat=\"server\"**\>**\
**\<div** class=\"error panel\"**\>**\
There are problems with the data you entered:\
**\<ul>**\
**\<asp:Repeater** SelectMethod=\"GetModelValidationErrors\" ViewStateMode=\"Disabled\" ItemType=\"System.String\" runat=\"server\"**\>**\
**\<ItemTemplate>**\
**\<li>**\<%# *Item* %>**\</li>**\
**\</ItemTemplate>**\
**\</asp:Repeater>**\
**\</ul>**\
**\</div>**\
**\</asp:PlaceHolder>**

Code:

**protected void** Page_Load(object sender, EventArgs e)\
{\
**if** (IsPostBack)\
{\
DisplayPerson(GetPerson());\
errorPanel.Visible = !ModelState.IsValid;\
}\
}

**protected** Person GetPerson()\
{\
Person model = **new** Person();\
IValueProvider provider = **new** FormValueProvider(ModelBindingExecutionContext);\
TryUpdateModel\<Person>(model, provider);\
**return** model;\
}

**public** IEnumerable\<string> GetModelValidationErrors()\
{\
**if** (!ModelState.IsValid)\
{\
**foreach** (KeyValuePair\<string, ModelState> pair **in** ModelState)\
{\
**foreach** (ModelError error **in** pair.Value.Errors)\
{\
**if** (!String.IsNullOrEmpty(error.ErrorMessage))\
{\
**yield return** error.ErrorMessage;\
}\
}\
}\
}\
}

 

 

 

One of the major additions to Web Forms in ASP.NET 4.5. Model binding simplifies the process of creating instances of the classes used to represent business objects in web applications and is a powerful tool for reducing errors and simplifying code-behind classes. It is closely related to data binding

 

Old way would be, to get all Values from Request and save them manuell in the POCO .

e.g. [GetPerson](onenote:#Model%20Binding%20\%20Data%20Binding&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={19463BB3-02A5-48E4-AA55-E7B3F457C948}&object-id={F05D1BC1-EC40-05D0-14BD-3FAC52917392}&1F&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet%20Schule/ASP%20Net.one)

 

## Better

The first thing we do is to apply model binding to automate the process of getting form values and using

them to populate the properties of the Person object.

 

See: [ModelBinding](onenote:#Model%20Binding%20\%20Data%20Binding&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={19463BB3-02A5-48E4-AA55-E7B3F457C948}&object-id={F05D1BC1-EC40-05D0-14BD-3FAC52917392}&B1&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet%20Schule/ASP%20Net.one)

 

 

## Applying Model Validation Attributes

See [Model Validation Attributes](onenote:#Model%20Binding%20\%20Data%20Binding&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={19463BB3-02A5-48E4-AA55-E7B3F457C948}&object-id={F05D1BC1-EC40-05D0-14BD-3FAC52917392}&BD&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet%20Schule/ASP%20Net.one)

 

## Using a Custom Validation Method

The validation attributes don't always provide quite the effect you require, but you can extend the validation process

by applying the CustomValidation attribute, which allows for custom validation methods to be defined and applied

to data values.

 

To use a Custom Validation Method we need to use the following Attribute:

**\[CustomValidation(typeof(Binding.CustomChecks), \"CheckZip\")\]**

 

See. [Using a Custom Validation Method](onenote:#Model%20Binding%20\%20Data%20Binding&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={19463BB3-02A5-48E4-AA55-E7B3F457C948}&object-id={F05D1BC1-EC40-05D0-14BD-3FAC52917392}&E3&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet%20Schule/ASP%20Net.one)

 

## Handling Model Binding and Validation Errors

 

See: [Handling Model Binding and Validation Errors](onenote:#Model%20Binding%20\%20Data%20Binding&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={19463BB3-02A5-48E4-AA55-E7B3F457C948}&object-id={F05D1BC1-EC40-05D0-14BD-3FAC52917392}&F4&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet%20Schule/ASP%20Net.one)

 

## Using Binding Attributes

 

The Model Binding Value Provider Classes

  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  ControlValueProvider       Gets a value from a property in a control.
  -------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------
  CookieValueProvider        Gets values from the cookies in the request.

  FormValueProvider          Gets values from the form data in the request.

  QueryStringValueProvider   Gets values from the request query string.

  ProfileValueProvider       Gets values from the user's profile data. See Chapter 18 for details of profile data.

  RouteDataValueProvider     Gets values from the variable segment values of the route used to request the current Web Form. See Chapters 23 and 24 for details of the routing feature.

  ViewStateValueProvider     Gets values from the view state associated with the request.
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

 

Using SqlDataSource

Dienstag, 7. April 2015

19:04

 

![](./assets/media/image15.png){width="5.254861111111111in" height="3.5756944444444443in"}

Wie ADO Net

 

Datenbanken werden im Folder APP_DATA gehalten.

 

 

ConnStr steht in WebConfig.

 

ProWebForm

\<asp:SqlDataSource id=\"Customers\" runat=\"server\" ConnectionString=\"\<%\$ ConnectionStrings:ConnStr %>\" SelectCommand=\"GetCustomers\" SelectCommandType=\"StoredProcedure\" />

 

 

![](./assets/media/image16.png){width="5.207638888888889in" height="1.9243055555555555in"}

 

Using ObjectDataSource

Dienstag, 7. April 2015

19:05

 

![](./assets/media/image17.png){width="5.207638888888889in" height="2.9625in"}

Provides declarative data binding between objects and controls. ( N-Tier )

 

Diese Klassen liegen dann im Folder APP_CODE

 

Es kann auch dann Linq to SQL Classes und damit dann unsere DAL füllen

 

![](./assets/media/image18.png){width="5.207638888888889in" height="1.7833333333333334in"}![](./assets/media/image19.png){width="5.207638888888889in" height="3.0375in"}

 

Using EntityDataSource

Dienstag, 7. April 2015

19:05

 

:-) EF Model.

 

Model liegt dann im Root Folder

![](./assets/media/image20.png){width="5.207638888888889in" height="2.047222222222222in"}

 

![](./assets/media/image21.png){width="5.9625in" height="1.8298611111111112in"}

 

Using QueryExtender

Dienstag, 7. April 2015

19:05

 

![Computergenerierter Alternativtext: QueryExtender Example Kasp :EntityDataSource -e/ asp : LingDataSourc0 TargetContr011Dz \" edsCustomers \" •asp : SearchExpression Da taF ContactName : Control parameter / •p •z/ asp : SearchExpressio» K/ asp : QueryExtender:• ](./assets/media/image22.png){width="5.207638888888889in" height="2.8208333333333333in"}

Creates Filter for data retrieved from a data source-

 

NO explicit where clause required in the data source

 

Allows different views of data to be shown

 

![Computergenerierter Alternativtext: EntityOataS0urce ConnectionString. ksLT OataEntities\" DefaultContainerNane.-AdventureV&rksLT DataEntities- EntitySetNa.e.-Custæers-s 4/ asp: EntityDataSeurco Tar-get (asp: roper-ty xpress on\' run at---server --- Where Clause Na.e•-SaIesPerson--- U asp; P\' ppertyExpression» c/asp : Querfixtender) ](./assets/media/image23.png){width="6.084722222222222in" height="2.6979166666666665in"}

 

 

Entity Framework

Dienstag, 7. April 2015

14:24

 

Siehe [EAF-Schulung](onenote:../Schulung/#base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente)

 

 

Managing State Data

Donnerstag, 25. Juni 2015

13:04

 

-   Application\[\"\"\]

-   Session\[\"\"\] -\> Dazu kann auch ein State Service genutzt werden => State Server oder aber auch eine SQL Datenbank, wenn Performance nicht so wichtig ist wie Daten Persistierung

-   ViewState\[\"\"\] => View Data -\> Hidden Elements on web site oder auch EnableViewState. Will be used when web control has runat=\"server\"

-   Control View State

-   Cookies

 

 

## Storing User Data

Called \"Profiles\" feature. SQL Based

-   Sql anlegen für Profile

-   Web.config anpassen\
    \<profile defaultProvider=\"profileDb\"\>

> \<providers>
>
> \<add name=\"profileDb\" connectionStringName=\"profileDb\"
>
> type=\"System.Web.Profile.SqlProfileProvider\"/>
>
> \</providers>
>
> \<properties>
>
> \<add name=\"counter\" type=\"int\"/>
>
> \</properties>
>
> \</profile>

-   Nutzen der ProfileDten in Webseite\
     

> \<div class=\"nameContainer\"\>
>
> \<input id=\"requestedUser\" value=\"Joe\" runat=\"server\" />
>
> \<button type=\"submit\"\>Submit\</button>
>
> \</div>

-   Nutzern der ProfileDaten in Webseite C# class\
     

> ProfileBase profile = ProfileBase.Create(user);
>
> int counter = (int)(profile\[\"counter\"\]);
>
> profile\[\"counter\"\] = ++counter;
>
> profile.Save();
>
> return counter;
>
>  

 

**[Tip]{.underline}** If you don't want to use a database, you can implement a profile provider, which acts as an interface

between the ASP.NET Framework and your custom profile data store. See <http://msdn.microsoft.com/en-us/library/0580x1f5(v=vs.100).aspx> for details.

 

To create the Database call aspnet_regsql.exe see: [aspnet_reqsql](onenote:#aspnet_reqsql&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={CE43DA47-B0F5-4584-801C-528CBF66F48E}&object-id={F2F080D7-BDB7-013C-265C-FDFD44252EBA}&12&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet%20Schule/ASP%20Net.one)

 

 

## Tip 

We get our view state figures using the handy ASP.NET View State Helper tool from Binary Fortress, which is

available from <http://www.binaryfortress.com/ASPNET-ViewState-Helper>. The tool is free, but you can make a

donation if you find it useful. We like Binary Fortress---they make the multi-monitor taskbar tool that we use on our

development desktops and that we recommend if you have multiple monitors

 

## Disable View State in Web.config

\<configuration>

\<system.web>

\<compilation debug=\"true\" targetFramework=\"4.5\" />

\<httpRuntime targetFramework=\"4.5\" />

**\<pages enableViewState=\"false\"\>**

\<controls>

\<add tagPrefix=\"CC\" tagName=\"Counter\" src=\"\~/Custom/Counter.ascx\"/>

\<add tagPrefix=\"CC\" assembly=\"ControlState\" namespace=\"ControlState.Custom\"/>

\</controls>

\</pages>

\</system.web>

\</configuration>

 

 

 

 

Master Pages

Dienstag, 7. April 2015

14:24

 

-   [Working With MasterPages](onenote:ASP%20Net.one#Working%20With%20MasterPages&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={06A1FD78-437A-47EC-B5AD-C837BC9412BD}&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet Schule)

-   [Creating Master Pages](onenote:ASP%20Net.one#Creating%20Master%20Pages&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={A88004DF-CE0B-4DC1-B2A3-AE9651DB2E22}&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet Schule)

-   [Content Pages](onenote:ASP%20Net.one#Content%20Pages&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={51033F1D-A8CB-4428-B5BC-8E57D195C5A6}&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet Schule)

 

 

Working With MasterPages

Mittwoch, 8. April 2015

13:36

 

Master Page erstellt einen globalen Rahmen für Header, Footer, Menus u.a. und mit Platzhaltern kann dann andere Daten angezeigt werden.

 

File extension .master

 

Master Pages can be nested

 

## Dynamically Changing Master Pages

They can be dynamicall changed using the Page_PreInit Method in the CodeBehind file

z.B. this.MasterPageFile = \"\~/xxx.master\";

 

 

## Using the Master Page Code-Behind Class

-   \<%@ MasterType TypeName = \"WebForms.Basic\" %>

> \<asp:Content ID = \"Content2\" ContentPlaceHolderID = \"ListEntries\" runat = \"server\"\>
>
> **\<% = Master.DisplayList(GetColors()) %>**
>
> \</asp:Content>
>
>  

 

Creating Master Pages

Mittwoch, 8. April 2015

13:40

 

Tags:

 

\<%\@Master %>

 

\<asp.ContenPlaceHolder id=\"ph1\" runat=\"server\" />

 

Am besten mit Divs arbeiten.

 

Content Pages

Mittwoch, 8. April 2015

13:43

 

Wird in den Content tags des Masters eingefügt.

 

Erzeugen:

-   Master Page RMB \"Add Content Page\"

-   Add New Item -\> WebForm using Master Page

-   Selber erstellen, dann muss MasterPageFile und \<asp:Content controls einbauen

 

 

Ajax Controls

Dienstag, 7. April 2015

14:24

 

-   [ASP Net Ajax Controls](onenote:ASP%20Net.one#ASP%20Net%20Ajax%20Controls&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={7826030A-CAAF-48F6-B839-91660E61B5C1}&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet Schule)

>  
>
>  
>
>  

## Definitions

-   **Postback Operation**: Action triggered by an end user or by code that sends data back to a web server for processing

-   **Partial-Page Updates**: Data in a section of a page is updates rather than the entire page

-   **AJAX**: Asynchronous JavaScript and XML

-   **XML**: Extensible Markup Language

-   **JSON**: JavaScript Object Notation

-   **DOM**: Document Object Model

-   **REST**: Representational State Transfer

## AJAX

-   Relies upon XMLHttpRequest object, JavaScript, CSS and JSON

-   A technology for making asynchronous (parallel) calls from a WebPage

-   Messages sent back and forth between Web pages and server using XMLHttpRequest

-   Results in minimal(or zero) page refreshes

-   Can integrate with Web Services or Rest Apis

-   Works with all mainstream browsers

 

ASP Net Ajax Controls

Mittwoch, 8. April 2015

13:54

![](./assets/media/image24.png){width="4.688888888888889in" height="2.811111111111111in"}

-   [ScriptManager Control](onenote:ASP%20Net.one#ScriptManager%20Control&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={B24C55EC-F04C-4702-8DE5-4B405F3F8009}&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet Schule)

-   [UpdatePanel Control](onenote:ASP%20Net.one#UpdatePanel%20Control&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={8794FA64-FECD-4953-91AD-A77F4B7B8139}&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet Schule)

-   [Update Progress Control](onenote:ASP%20Net.one#Update%20Progress%20Control&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={7B7AA9F1-F03C-4B75-A10B-85495A61F523}&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet Schule)

 

AJAX using XMLHttpRequest ( JSON, REST )

 

## Tip. Ajax enable existing websites

-   ScriptManager in ggf vorhandene Master files

-   Implement UpdatePanels for needed Controls ( e.g. Grid or so )

 

ScriptManager Control

Mittwoch, 8. April 2015

13:54

 

> The ScriptManager control is a key control when scripting:

-   Required in all ASP-Net AJAX enables pages

-   Manages all framework and custom scripts used by a page

-   Used to reference custom scripts

-   Generatges client-side Web Service Proxy objects

-   Controls debug and release modes for script debugging

-   Coordinates asynchronous operations

>  
>
>  
>
>  
>
>  
>
> Tag:
>
>  
>
> \<asp:ScriptManager id=\"sm\" runat=\"server\"\>
>
> \<Scripts>
>
> \<asp:ScriptReference Path=\"\~/Scripts/Custom.js\" />
>
> \</Scripts>
>
> \</asp:Scriptmanager>
>
>  
>
> Property:
>
> IsInAsyncPostBack
>
> z.b.
>
> Protected void Page_Load(xxxx)
>
> {
>
> If (sm.IsInAsyncPostBack)
>
> DataBindControls();
>
> }
>
>  
>
> Partial-Page updates can be disabled using the ScriptManager\'s \"EnablePartialRendering\" property. Can be used for debugging bzw error suchen. d.h bei exceptions wird dann genauer angezgit wo der Fehler ist.

![](./assets/media/image25.png){width="4.9430555555555555in" height="0.8770833333333333in"}

## Create scripts

-   Create a java script js in extra file

-   Add a scriptmanager on page

-   Set Script in Property scripts of scriptmanager

>  

 

![](./assets/media/image26.png){width="4.688888888888889in" height="2.216666666666667in"}

 

 

## Beispiel:

![](./assets/media/image27.png){width="5.6506944444444445in" height="1.7451388888888888in"}

 

 

UpdatePanel Control

Mittwoch, 8. April 2015

13:55

![Computergenerierter Alternativtext: I auednepdn os9nb xdsvunepa speqlsod a6ed-P!ued pue puuaepdn ](./assets/media/image28.png){width="4.1506944444444445in" height="2.3208333333333333in"}

Require ScriptManager Control

 

## UpdatePanel control features:

-   AJAX enables ortions of a page

-   Can handle actions triggered by html elements

-   Supports nested UpdatePanel controls

-   Provides a template named ContentTemplate (Template für ajax enabled stuff)

 

## How does it work

-   The UpdatePanel converts normal postback operations into asynchronous postbacks using XMLHttpRequest

-   Controls in the template as well as ViewState are sent to the server

-   Response Message data is automatically updated in the page

-   No Java Script is required out of the box

!!! ViewState größe kann geschwindigkeit beinflussen. !!!

 

Es kann auch Javascript eingefügt werden.

![Computergenerierter Alternativtext: • The following example demonstrates how to use the UpdatePanel\'s ContentTemplate: •asp: U#atepanel runat---\" ten at Kasp:Gr1dview \" \'con ten tTenpIa to / asp : runa server \" Server ](./assets/media/image29.png){width="4.688888888888889in" height="2.5569444444444445in"}

## Einstellen trigger UpdatePanel

 

![Computergenerierter Alternativtext: 3 ... , , d 。 - uo 3 uqns 》 「 3 Od 艮 01 \$ \~ 5a4 雟 , \~ 0 , 丷 ](./assets/media/image30.png){width="5.207638888888889in" height="3.754861111111111in"}

 

![Computergenerierter Alternativtext: Creating UpdatePanel Triggers • The UpdatePanel control\'s region can be refreshed when a control event fires (or a value changes) outside Of the panel\'s ContentTemplate: Kasp : Conten a to KConten t» ggers : ASYnCPOS Control ggers Clasp : tepane» Kasp : Button Text:\" ](./assets/media/image31.png){width="4.688888888888889in" height="3.047222222222222in"}

 

Update Progress Control

Mittwoch, 8. April 2015

13:55

 

> Used for notifications
>
>  
>
> Wird im UpdateControl mit eingebaut.
>
>  

## !!! WebSite um ajaxload gifs zu erstellen

> <http://ajaxload.info>

![](./assets/media/image32.png){width="5.207638888888889in" height="2.792361111111111in"}

 

 

Security / Authentication / Authorization

Dienstag, 7. April 2015

14:24

 

-   ([Using the ASP.Net Configuration WebSite](onenote:ASP%20Net.one#Using%20the%20ASP.Net%20Configuration%20WebSite&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={D9FE6309-F32E-44C8-B8C8-0F0D38B85786}&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet Schule))

-   [aspnet_reqsql](onenote:ASP%20Net.one#aspnet_reqsql&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={CE43DA47-B0F5-4584-801C-528CBF66F48E}&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet Schule)

-   [Security Server Controls](onenote:ASP%20Net.one#Security%20Server%20Controls&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={DF73CFC2-35BF-460C-93D6-9D50BB26E058}&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet Schule)

-   Membershib (sql database)

## Concepts:

-   **Authentication** - Who are you

-   **Authorization** - What actions are you allowed to perfom ?

-   **Impersination** - Switch user to perform specific actions

 

## Built-In Security modes:

-   Forms Authentication ([Forms Authentication](onenote:ASP%20Net.one#Forms%20Authentication&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={5F6D5F7C-C083-482C-9933-DAA1277026A3}&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet Schule))

-   Windows Authentication (Basic, Digest, NLTM, Kerberos) ([Windows Authentication](onenote:ASP%20Net.one#Windows%20Authentication&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={04BBF545-F551-448E-A4E9-56F22632A7FB}&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet Schule))\
    (Mostly used by Intranet )

 

Forms Authentication

Donnerstag, 9. April 2015

13:45

 

Allows user credentials to be verified using a Custom UI and credential store.

 

## Features:

-   Login through a web page

-   Automatically redirect anonymous users to a login page

-   Authenticated users identified by an **authentication token stored in a Cookie or in the URL**

-   Relies on the FormsAuthentication class

-   Configured in **web.config**.

 

Dazu muss in der main web.config \<authentication mode=\"Forms\" /> eingetragen werden.

Und noch der RoleManager.

Default ist, das die Authentication implementierung nach einem LoginDialog such der \"Login.aspx\" heißt. Das kann aber mit Tags angepasst werden.

 

!! Ggf jeder Folder hat ein eigene WebConfig mit Security settings.

 

Klasse für codebehind => FormsAuthentication

![](./assets/media/image33.png){width="4.688888888888889in" height="0.9152777777777777in"}

 

\<system.web>

\<authentication mode=\"Forms\"\>

\<forms loginUrl=\"\~/Pages/Login.aspx\"\>

\</forms>

\</authentication>

Password setzen

\<authentication mode=\"Forms\"\>

\<forms loginUrl=\"\~/Pages/Login.aspx\"\>

**\<credentials passwordFormat=\"Clear\"\>**

**\<user name=\"admin\" password=\"secret\" />**

**\</credentials>**

\</forms>

\</authentication>

 

\</configSections>

\<location path=\"admin\"\>

\<system.web>

\<authorization>

\<deny users=\"?\"/>

\</authorization>

\</system.web>

\</location>

 

Windows Authentication

Donnerstag, 9. April 2015

13:49

 

Should only be used for Intranet websites

##  

## Features:

-   Can be used in combination with Basic, NTLM, Digest, Kerberos and more

-   User authentication by Internet Information services (IIS)

-   Easisest of all to use

-   Request flow:

    1.  Clients make request

    2.  IIS authenticates request, forwars to ASP.NET

    3.  APS:NET accesses requested resources

NTLM - Windows Server- Website Properties -\> Web-\>Use NTLM

 

Danach kann mit windows rechten die Website eingegrenzt werden !!

 

![](./assets/media/image34.png){width="6.0in" height="5.065972222222222in"}

 

 

Using the ASP.Net Configuration WebSite

Donnerstag, 9. April 2015

13:56

## Tip VS \> 2012

 

Ab VS 2013 und \> gibt es die Configuration Web Site nicht mehr. Dazu dieses Batchfile nutzen.

 

REM Damit startet man einen IIS Express der dann das WebConfig startet

REM siehe <http://blogs.msdn.com/b/webdev/archive/2013/08/19/asp-net-web-configuration-tool-missing-in-visual-studio-2013.aspx>

REM

REM Danach dann

REM

REM [http://localhost:8082/asp.netwebadminfiles/default.aspx?applicationPhysicalPath=\[appPath\]&applicationUrl=/](http://localhost:8082/asp.netwebadminfiles/default.aspx?applicationPhysicalPath=%5bappPath%5d&applicationUrl=/)

REM substituting the \[appPath\] with the absolute path to the Visual Studio Project folder with the solution file in it.

 

\"C:\\Program Files (x86)\\IIS Express\\iisexpress.exe\" /path:c:\\windows\\Microsoft.NET\\Framework\\v4.0.30319\\ASP.NETWebAdminFiles /vpath:\"/asp.netwebadminfiles\" /port:8089 /clr:4.0 /ntlm

 

REM [http://localhost:8089/asp.netwebadminfiles/default.aspx?applicationPhysicalPath=c:\\Users\\MKraus\\Documents\\Visual Studio 2013\\Projects\\Membership\\&applicationUrl=/](http://localhost:8089/asp.netwebadminfiles/default.aspx?applicationPhysicalPath=c:\Users\MKraus\Documents\Visual%20Studio%202013\Projects\Membership\&applicationUrl=/)\"

 

Defines Users, Roles and Access

 

aspnet_reqsql

Donnerstag, 9. April 2015

14:07

 

![](./assets/media/image35.png){width="7.48125in" height="4.603472222222222in"}

Security settings tool for install Security DB in Sql Server instead of Express like [Using the ASP.Net Configuration WebSite](onenote:ASP%20Net.one#Using%20the%20ASP.Net%20Configuration%20WebSite&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={D9FE6309-F32E-44C8-B8C8-0F0D38B85786}&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet Schule)

 

## Path location

c:\\windows\\Microsoft.Net\\Framework\\v4.xxxxxxx\\aspnet_reqsql.exe

Oder in vs studio command prompt einfach **aspnet_reqsql** eingeben.

 

Security Server Controls

Donnerstag, 9. April 2015

14:11

 

## List of Server Controls

-   Login ([Login Control](onenote:ASP%20Net.one#Login%20Control&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={26D496C2-D327-4F98-97C8-D03FC738A489}&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet Schule))

-   LoginView ([LoginView Control](onenote:ASP%20Net.one#LoginView%20Control&section-id={DFEE248F-D0A0-4AE2-9E1E-631A69323D6F}&page-id={C14BE640-B3F3-4207-8028-97145BBBFF25}&base-path=https://d.docs.live.net/d1f45074fc2290d1/Dokumente/AspNet Schule))

-   PasswordRecovery

-   LoginStatus

-   LoginName

-   CreateUserWizard

-   ChangePassword

 

Login Control

Donnerstag, 9. April 2015

16:30

 

##  

The LoginControl supports templates for customized login screens.

##  

## Tag:

\<asp:Login id=\"Login\" runat=\"server\" CreateUserUrl=\"RegisterUser.aspx\" CreateUserText=\"Create a User Account\" />

 

 

 

# CreateUserWizard Control

## Tag

\<asp:CreateUserWizard id=\"createUserWizard1\" runat=\"server\" ContinueDestinationPageUrl=\"default.aspx\"/>

 

LoginView Control

Donnerstag, 9. April 2015

18:56

 

Shows different messages bases upon the authentication status of the user.

 

Diese Dialog kann angepasst werden. Dazu am besten in ein Web Project template schauen

 

## Tag:

\<asl:LoginView id=\"loginView1\" runat=\"server\"

> \<AnonymousTemplate>
>
> Please login below
>
> \</AnonymousTemplate>
>
> \<LoggedInTemplate>
>
> Welcome
>
> \<asp:LoginName id=\"loginName\" runat=\"server\" />
>
> \<L/oggedInTemplate>

\</asp:LoginView>

 

 

Dynamic Data

Dienstag, 7. April 2015

14:24

 

It\'s a template for quick Data Driven ( Linq to sql or entities ) website

 

 

Web Deployment

Dienstag, 7. April 2015

14:24

 

 

TODO

Mittwoch, 1. April 2015

20:55

 

-   Wie man web Config started.

-   Validation ?? Framework

>  
>
>  

 

 

Different States

Montag, 27. April 2015

21:01

 

  ---------------------------------------------------------------------------------------------------------------
  Session State   Für ein User (Session). Darin kann alles gepackt werden. In Memory oder z.b. auch in Database
  --------------- -----------------------------------------------------------------------------------------------

  ---------------------------------------------------------------------------------------------------------------
