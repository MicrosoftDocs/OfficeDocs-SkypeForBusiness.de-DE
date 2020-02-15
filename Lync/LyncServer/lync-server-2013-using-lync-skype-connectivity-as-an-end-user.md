---
title: 'Lync Server 2013: Verwenden von lync-Skype-Konnektivität als Endbenutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Lync-Skype connectivity as an end user
ms:assetid: ad22f731-118c-4349-8790-b1a72941cbdd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440175(v=OCS.15)
ms:contentKeyID: 57793365
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df22148fae23e0872fc9f33a54792590b634f46d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-lync-skype-connectivity-in-lync-server-2013-as-an-end-user"></a><span data-ttu-id="9098f-102">Verwenden von lync-Skype-Konnektivität in lync Server 2013 als Endbenutzer</span><span class="sxs-lookup"><span data-stu-id="9098f-102">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9098f-103">_**Letztes Änderungsstand des Themas:** 2016-12-27_</span><span class="sxs-lookup"><span data-stu-id="9098f-103">_**Topic Last Modified:** 2016-12-27_</span></span>

<span data-ttu-id="9098f-104">Mit lync-Skype-Konnektivität können Skype-Benutzer und lync-Benutzer sich gegenseitig als Kontakte hinzufügen, Chatnachrichten austauschen und Audio-und Videoanrufe tätigen.</span><span class="sxs-lookup"><span data-stu-id="9098f-104">Lync-Skype Connectivity enables Skype users and Lync users to add each other as contacts, exchange instant messages and make audio and video calls.</span></span> <span data-ttu-id="9098f-105">Wenn ein Skype-Benutzer einen lync-Benutzer hinzufügt, erstellt ein Skype-Benutzer einen Kontakt in Skype, der den SIP-Uniform Resource Identifier (Session Initiation Protocol) des lync-Benutzers enthält.</span><span class="sxs-lookup"><span data-stu-id="9098f-105">When a Skype user adds a Lync user, a Skype user will create a contact in Skype containing the session initiation protocol (SIP) uniform resource identifier (URI) of the Lync user.</span></span> <span data-ttu-id="9098f-106">Wenn ein lync-Benutzer einen Skype-Kontakt hinzufügt, erstellt der lync-Benutzer umgekehrt einen Kontakt in lync, der das Microsoft-Konto (MSA) des Skype-Benutzers und nicht den Skype-Benutzernamen enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="9098f-106">Conversely, when a Lync user adds a Skype contact, the Lync user will create a contact in Lync that will contain the Microsoft Account (MSA) of the Skype user, and not the Skype user name.</span></span>

<span data-ttu-id="9098f-107">**Was ist eine MSA?**</span><span class="sxs-lookup"><span data-stu-id="9098f-107">**What is an MSA?**</span></span> <span data-ttu-id="9098f-108">Skype-Benutzer müssen sich mit einem Microsoft-Konto (früher als Windows Live ID bezeichnet) bei Skype anmelden, um mit lync-Kontakten zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="9098f-108">Skype users must sign in to Skype with a Microsoft account (previously called Windows Live ID) in order to communicate with Lync contacts.</span></span><span data-ttu-id="9098f-109">Ein Microsoft-Konto besteht aus der Kombination aus einer e-Mail-Adresse und einem Kennwort, die Sie auch für die Anmeldung bei Diensten wie Microsoft OneDrive Speichertechnologie, Windows Phone, Microsoft Xbox Live Online Game Service und Microsoft Outlook Messaging verwenden können. und Zusammenarbeitsclient (und zuvor Microsoft Hotmail-webbasierter e-Mail-Dienst oder Windows Live Messenger).</span><span class="sxs-lookup"><span data-stu-id="9098f-109"> A Microsoft account consists of the combination of an email address and a password, which you can also use to sign in to services such as Microsoft OneDrive storage technology, Windows Phone, Microsoft Xbox LIVE online game service, and Microsoft Outlook messaging and collaboration client (and, previously, Microsoft Hotmail web-based e-mail service or Windows Live Messenger).</span></span><span data-ttu-id="9098f-110">Wenn Sie eine e-Mail-Adresse und ein Kennwort verwenden, um sich bei diesen oder anderen Diensten anzumelden, verfügen Sie bereits über ein Microsoft-Konto.</span><span class="sxs-lookup"><span data-stu-id="9098f-110"> If you use an email address and a password to sign in to these or other services, you already have a Microsoft account.</span></span><span data-ttu-id="9098f-111">Ausführliche Informationen zum Erstellen eines Microsoft-Kontos finden Sie auf [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061)der Microsoft-Konto-Anmeldeseite unter.</span><span class="sxs-lookup"><span data-stu-id="9098f-111"> For details about creating a Microsoft Account, see the Microsoft account sign-up page at [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061).</span></span> <span data-ttu-id="9098f-112">Sie können Ihr vorhandenes Skype-Konto mit Ihrem Microsoft-Konto für einmaliges Anmelden in einer Vielzahl von Anwendungen und Diensten zusammenführen.</span><span class="sxs-lookup"><span data-stu-id="9098f-112">You can merge your existing Skype account with your Microsoft account for single sign-on, across a variety of applications and services.</span></span> <span data-ttu-id="9098f-113">Nachdem das Konto zusammengeführt wurde, kann ein Skype-Benutzer eine Kontakt Anfrage an lync-Benutzer senden.</span><span class="sxs-lookup"><span data-stu-id="9098f-113">Once the account is merged a Skype user can send a contact request to Lync users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9098f-114">Damit lync-und Skype-Benutzer vollständig miteinander kommunizieren können, müssen die folgenden Voraussetzungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="9098f-114">In order for Lync and Skype users to fully communicate with each other, the following requirements must be met:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="9098f-115">Skype-Benutzer müssen bei Ihrem Skype-Client mit einem Microsoft-Konto (MSA) angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="9098f-115">Skype users must be logged into their Skype client with a Microsoft Account (MSA).</span></span></P>
> <LI>
> <P><span data-ttu-id="9098f-116">Lync-Benutzer müssen für die Verbindung mit öffentlichen Chat Diensten durch ihren lync-Administrator aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="9098f-116">Lync users must be enabled for public IM connectivity by their Lync administrator.</span></span></P>
> <LI>
> <P><span data-ttu-id="9098f-117">Wenn ein Skype-Benutzer einen lync-Kontakt hinzufügt, vergewissern Sie sich, dass das Wort lync unter dem Namen des Kontakts angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9098f-117">When a Skype user adds a Lync contact, verify that the word Lync appears below the contact’s name.</span></span> <span data-ttu-id="9098f-118">Dies deutet darauf hin, dass ein lync-URI gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="9098f-118">This indicates that a Lync URI has been found.</span></span></P>
> <LI>
> <P><span data-ttu-id="9098f-119">Wenn ein Skype-Benutzer einen lync-Kontakt hinzufügt und keine Suchergebnisse für diese lync-Domäne zurückgegeben werden, ist der PIC-bereit stellungsprozess möglicherweise nicht abgeschlossen, oder die lync-Domäne wurde noch nicht eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="9098f-119">When a Skype user adds a Lync contact and zero search results are returned for that Lync domain, the PIC provisioning process may not have completed, or the Lync domain has not yet been set up.</span></span></P>
> <LI>
> <P><span data-ttu-id="9098f-120">Je nach den Datenschutzeinstellungen der lync-und Skype-Benutzer funktionieren Chat, Video und Anwesenheit möglicherweise erst, wenn die neuen Kontakte von jedem Benutzer akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="9098f-120">Depending on the privacy settings of the Lync and Skype users, IM, video, and presence may not work until the new contacts are accepted by each user.</span></span></P></LI></UL>



</div>

<span data-ttu-id="9098f-121">**So fügen Sie lync 2013 einen Skype-Kontakt hinzu**</span><span class="sxs-lookup"><span data-stu-id="9098f-121">**To add a Skype contact to Lync 2013**</span></span>

1.  <span data-ttu-id="9098f-122">Klicken Sie in lync auf **Kontakt hinzufügen, fügen Sie einen Kontakt nicht in meine Organisation hinzu**.</span><span class="sxs-lookup"><span data-stu-id="9098f-122">From Lync, click **Add a Contact, Add a Contact Not in My Organization**.</span></span>

2.  <span data-ttu-id="9098f-123">Wählen Sie in der Liste der verfügbaren Kontakt Anbieter **Skype**aus.</span><span class="sxs-lookup"><span data-stu-id="9098f-123">From the list of available contact providers, select **Skype**.</span></span>

3.  <span data-ttu-id="9098f-124">Geben Sie in das Feld **Chat Adresse** das Microsoft-Konto (MSA) des Skype-Benutzers ein.</span><span class="sxs-lookup"><span data-stu-id="9098f-124">In the **IM Address** field, enter the Microsoft Account (MSA) of the Skype user.</span></span>

4.  <span data-ttu-id="9098f-125">Wählen Sie im Dropdownfeld **zur Kontaktgruppe hinzufügen** eine Kontaktgruppe aus, der der Benutzer hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9098f-125">In the **Add to contact group** dropdown box, select a contact group to add the user to.</span></span>

5.  <span data-ttu-id="9098f-126">Wählen Sie im Dropdownfeld **Datenschutz Beziehung festlegen** die entsprechende Kontakteinstellung aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9098f-126">In the **Set privacy relationship** dropdown box, select the appropriate contact setting and then click **OK**.</span></span>

6.  <span data-ttu-id="9098f-127">Der Benutzer wird nun als Kontakt in lync angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9098f-127">The user will now appear as a contact in Lync.</span></span> <span data-ttu-id="9098f-128">Wählen Sie den Benutzer aus, klicken Sie mit der rechten Maustaste auf den Benutzernamen, und klicken Sie auf Visiten **Karte** anzeigen, um die Benutzereigenschaften anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9098f-128">Select the user, right-click the user name, and click **See Contact Card** to view the user properties.</span></span> <span data-ttu-id="9098f-129">Sie können nun einen Audio-oder Videoanruf mit dem neu hinzugefügten Skype-Benutzer einrichten.</span><span class="sxs-lookup"><span data-stu-id="9098f-129">You can now establish an audio or video call with the newly added Skype user.</span></span>

<span data-ttu-id="9098f-130">Weitere Informationen zur Unterstützung von Kontakten finden Sie unter [Hinzufügen eines Kontakts in lync](https://support.office.com/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a).</span><span class="sxs-lookup"><span data-stu-id="9098f-130">For additional information on support for contacts, see [Add a contact in Lync](https://support.office.com/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a).</span></span>

<span data-ttu-id="9098f-131">Wenn ein Microsoft-Konto eines Skype-Benutzers einen benutzerdefinierten Domänennamen wie <strong>Bob@contoso.com</strong> verwendet, kann ein lync-Benutzer dieses Microsoft-Konto auf zwei Arten zu lync hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="9098f-131">When a Skype user’s Microsoft account uses a custom domain name, such as <strong>bob@contoso.com</strong> , a Lync user can add that Microsoft account to Lync in two ways:</span></span>

1.  <span data-ttu-id="9098f-132">Verwenden Sie das Symbol " **Kontakt hinzufügen** " oder</span><span class="sxs-lookup"><span data-stu-id="9098f-132">Use the **Add a Contact** icon, or</span></span>

2.  <span data-ttu-id="9098f-133">Verwenden Sie das Feld **jemanden suchen oder einen Raum oder ein Ziffernblatt wählen** .</span><span class="sxs-lookup"><span data-stu-id="9098f-133">Use the **Find someone or a room, or a dial a number** field.</span></span>

<span data-ttu-id="9098f-134">In jeder Instanz muss der lync-Benutzer die e-Mail-Adresse des Skype-Benutzers im folgenden Format eingeben: <strong>Benutzer (Domänenname) @MSN. com</strong> .</span><span class="sxs-lookup"><span data-stu-id="9098f-134">In each instance, the Lync user must enter the Skype user’s email in the following format: <strong>user(domain name)@msn.com</strong> .</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9098f-135">Dieser Schritt ist für Microsoft-Konten, die die folgenden Domänennamen verwenden, nicht erforderlich: <STRONG>@Live. com, @hotmail. com oder @Outlook. com</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="9098f-135">This step is not required for Microsoft accounts that use the following domain names: <STRONG>@live.com, @hotmail.com or @outlook.com</STRONG>.</span></span> <span data-ttu-id="9098f-136">Weitere Informationen zu unterstützten benutzerdefinierten Domänennamen finden Sie unter <A href="https://support.microsoft.com/kb/897567">Supported Public Chat Domains</A>.</span><span class="sxs-lookup"><span data-stu-id="9098f-136">For more information on supported custom domain names, see <A href="https://support.microsoft.com/kb/897567">Supported public IM domains</A>.</span></span>



</div>

<span data-ttu-id="9098f-137">**So fügen Sie lync einen Skype-Kontakt hinzu, wenn Sie einen benutzerdefinierten Domänennamen verwenden**</span><span class="sxs-lookup"><span data-stu-id="9098f-137">**To add a Skype contact to Lync when using a custom domain name**</span></span>

1.  <span data-ttu-id="9098f-138">Klicken Sie in lync auf **Kontakt hinzufügen, fügen Sie einen Kontakt nicht in meine Organisation hinzu**.</span><span class="sxs-lookup"><span data-stu-id="9098f-138">From Lync, click **Add a Contact, Add a Contact Not in My Organization**.</span></span>

2.  <span data-ttu-id="9098f-139">Wählen Sie in der Liste der verfügbaren Kontakt Anbieter **Skype**aus.</span><span class="sxs-lookup"><span data-stu-id="9098f-139">From the list of available contact providers, select **Skype**.</span></span>

3.  <span data-ttu-id="9098f-140">Geben Sie im Feld **Chat Adresse** das Microsoft-Konto (MSA) des Skype-Benutzers im Format <strong>Benutzer (Domänenname) @MSN. com</strong>ein.</span><span class="sxs-lookup"><span data-stu-id="9098f-140">In the **IM Address** field, enter the Microsoft Account (MSA) of the Skype user in the format <strong>user(domain name)@msn.com</strong>.</span></span> <span data-ttu-id="9098f-141">Für Benutzer Bob@contoso.com wäre der Eintrag also <strong>Bob (contoso. com) @MSN. com.<strong></span><span class="sxs-lookup"><span data-stu-id="9098f-141">So for user bob@contoso.com, the entry would be <strong>bob(contoso.com)@msn.com<strong> .</span></span>

4.  <span data-ttu-id="9098f-142">Wählen Sie im Dropdown-Listenfeld **zu Kontaktgruppe hinzufügen** eine Kontaktgruppe aus, der der Benutzer hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9098f-142">In the **Add to contact group** drop-down list box, select a contact group to add the user to.</span></span>

5.  <span data-ttu-id="9098f-143">Wählen Sie im Dropdown-Listenfeld **Datenschutz Beziehung festlegen** die entsprechende Kontakteinstellung aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9098f-143">In the **Set privacy relationship** drop-down list box, select the appropriate contact setting and then click **OK**.</span></span>

6.  <span data-ttu-id="9098f-144">Ein lync-Benutzer kann auch den **Suchbegriff "jemand" oder einen Raum verwenden oder ein Nummern** Feld in lync wählen und eine Adresse hinzufügen, die dem folgenden <strong>Benutzer (Domänenname) @MSN. com</strong> ähnelt.</span><span class="sxs-lookup"><span data-stu-id="9098f-144">A Lync user can also use the **Find someone or a room, or dial a number** field in Lync, and add an address that resembles the following <strong>user(domain name)@msn.com</strong> .</span></span> <span data-ttu-id="9098f-145">Für das Bob@contoso.com Microsoft-Konto wäre der Eintrag also <strong>Bob (contoso. com) @MSN. com</strong> .</span><span class="sxs-lookup"><span data-stu-id="9098f-145">So for the bob@contoso.com Microsoft account, the entry would be <strong>bob(contoso.com)@msn.com</strong> .</span></span>

7.  <span data-ttu-id="9098f-146">Führen Sie die Schritte 4 und 5 weiter oben in diesem Verfahren aus, um den Kontakt einer Kontaktgruppe hinzuzufügen und die entsprechende Datenschutz Beziehung auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="9098f-146">Follow steps 4 and 5 earlier in this procedure to add the contact to a contact group and to select the appropriate privacy relationship.</span></span>

<span data-ttu-id="9098f-147">**So fügen Sie Skype einen lync-Kontakt hinzu**</span><span class="sxs-lookup"><span data-stu-id="9098f-147">**To add a Lync contact to Skype**</span></span>

1.  <span data-ttu-id="9098f-148">Melden Sie sich bei Skype an.</span><span class="sxs-lookup"><span data-stu-id="9098f-148">Sign in to Skype.</span></span> <span data-ttu-id="9098f-149">Der Skype-Benutzer muss bei seinem Skype-Client mit einem Microsoft-Konto (MSA) angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="9098f-149">The Skype user must be logged into their Skype client with a Microsoft Account (MSA).</span></span>

2.  <span data-ttu-id="9098f-150">Wählen Sie das Symbol Kontakte hinzufügen aus.</span><span class="sxs-lookup"><span data-stu-id="9098f-150">Select the Add Contacts icon.</span></span>

3.  <span data-ttu-id="9098f-151">Geben Sie den SIP-URI des lync-Benutzers ein.</span><span class="sxs-lookup"><span data-stu-id="9098f-151">Enter the SIP URI of the Lync user.</span></span> <span data-ttu-id="9098f-152">Beispiel: bob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9098f-152">For example, bob@contoso.com.</span></span>

4.  <span data-ttu-id="9098f-153">Wenn Skype die Übereinstimmung in den Suchergebnissen findet, suchen Sie nach dem Wort **lync** unter dem Namen des lync-Benutzers.</span><span class="sxs-lookup"><span data-stu-id="9098f-153">When Skype finds the match in the search results, look for the word **Lync** below the Lync user’s name.</span></span> <span data-ttu-id="9098f-154">Dies deutet darauf hin, dass Skype erfolgreich den SIP-URI des lync-Clients gefunden hat.</span><span class="sxs-lookup"><span data-stu-id="9098f-154">This indicates Skype successfully located the Lync client’s SIP URI.</span></span> <span data-ttu-id="9098f-155">Klicken Sie auf den Namen.</span><span class="sxs-lookup"><span data-stu-id="9098f-155">Click the name.</span></span>

5.  <span data-ttu-id="9098f-156">Klicken Sie in der oberen rechten Ecke des Fensters auf zu Kontakten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9098f-156">In the top right corner of the window, click Add to Contacts.</span></span>

6.  <span data-ttu-id="9098f-157">Der neue Kontakt wird nun Ihrer Kontaktliste hinzugefügt, aber anstelle des Statussymbols wird ein Fragezeichen angezeigt, bis Sie Ihre Anfrage annehmen.</span><span class="sxs-lookup"><span data-stu-id="9098f-157">The new contact is now added to your contact list, but you’ll see a question mark instead of their status icon until they accept your request.</span></span> <span data-ttu-id="9098f-158">Wenn Ihr neuer Kontakt Ihre Anfrage annimmt, können Sie sehen, wann diese online sind, Chat Unterhaltungen initiieren und Audio-und Videoanrufe tätigen.</span><span class="sxs-lookup"><span data-stu-id="9098f-158">When your new contact accepts your request, you will be able to see when they are online, initiate IM conversations, and make audio and video calls.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9098f-159">Der lync Server Administrator muss die Richtlinieneinstellungen des lync-Benutzers so konfigurieren, dass eingehende Anforderungen zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="9098f-159">The Lync Server administrator must configure the Lync user’s policy settings to allow incoming requests.</span></span> <span data-ttu-id="9098f-160">Wenn dies nicht der Fall ist, erhält der lync-Benutzer keine Kontaktanforderungen vom Skype-Benutzer.</span><span class="sxs-lookup"><span data-stu-id="9098f-160">If not, the Lync user will not receive contact requests from the Skype user.</span></span> <span data-ttu-id="9098f-161">In Abhängigkeit von der Konfiguration der Richtlinieneinstellungen des lync-Benutzers wird die Anforderung zum Hinzufügen des Skype-Benutzers auf der <STRONG>neuen</STRONG> Registerkarte des lync-Clients angezeigt. Um mit der Kommunikation mit dem Skype-Benutzer zu beginnen, muss der lync-Benutzer den Skype-Benutzer entweder der Favoritenliste oder einer Kontaktliste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9098f-161">Depending on the configuration of the Lync user’s policy settings, the request to add the Skype user will appear on the Lync client’s <STRONG>New</STRONG> tab. To begin communicating with the Skype user, the Lync user must add the Skype user to either the Favorites list or a contact list.</span></span> <span data-ttu-id="9098f-162">Das folgende Bild zeigt den Speicherort der <STRONG>neuen</STRONG> Registerkarte im lync-Client.</span><span class="sxs-lookup"><span data-stu-id="9098f-162">The image below shows the location of the <STRONG>New</STRONG> tab in the Lync client.</span></span>

    
    </div>

<span data-ttu-id="9098f-163">Ein lync-Benutzer muss lync-Warnungen konfigurieren, um sicherzustellen, dass von einem Skype-Benutzer gesendete Anforderungen angezeigt werden und vom lync-Benutzer erkannt werden können.</span><span class="sxs-lookup"><span data-stu-id="9098f-163">A Lync user must configure Lync alerts to ensure that requests sent from a Skype user appear and are discoverable by the Lync user.</span></span> <span data-ttu-id="9098f-164">Um lync-Warnungen zu konfigurieren, führen Sie das folgende Verfahren aus.</span><span class="sxs-lookup"><span data-stu-id="9098f-164">To configure Lync alerts, complete the procedure that follows.</span></span>

<span data-ttu-id="9098f-165">**So konfigurieren Sie lync-Warnungen**</span><span class="sxs-lookup"><span data-stu-id="9098f-165">**To configure Lync Alerts**</span></span>

1.  <span data-ttu-id="9098f-166">Klicken Sie auf dem lync-Client auf das **options** Symbol.</span><span class="sxs-lookup"><span data-stu-id="9098f-166">From the Lync client, click the **Options** icon.</span></span>

2.  <span data-ttu-id="9098f-167">Wählen Sie **Warnungen**aus.</span><span class="sxs-lookup"><span data-stu-id="9098f-167">Select **Alerts**.</span></span>

3.  <span data-ttu-id="9098f-168">Überprüfen Sie unter **Allgemeine Warnungen**, **Wenn mich jemand zu seiner Kontaktliste hinzufügt, auf Benachrichtigen**.</span><span class="sxs-lookup"><span data-stu-id="9098f-168">Under **General alerts**, check **Tell me when someone adds me to his or her contact list**.</span></span>

4.  <span data-ttu-id="9098f-169">Wählen Sie unter Kontakte, die **lync nicht verwenden** **die Option Einladungen zulassen, aber alle anderen Kommunikationen blockieren**aus.</span><span class="sxs-lookup"><span data-stu-id="9098f-169">Under **Contacts not using Lync**, select **Allow invites but block all other communications**.</span></span>

5.  <span data-ttu-id="9098f-170">Klicken Sie auf **OK** , um das Fenster Optionen zu schließen.</span><span class="sxs-lookup"><span data-stu-id="9098f-170">Click **OK** to close the Options window.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

