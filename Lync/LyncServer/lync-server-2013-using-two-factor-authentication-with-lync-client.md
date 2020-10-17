---
title: 'Lync Server 2013: Verwenden der zweistufigen Authentifizierung mit lync-Client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using two-factor authentication with Lync client
ms:assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn338071(v=OCS.15)
ms:contentKeyID: 55115593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a90dd3c40267f0994e7f41eabb689c869182cea7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508642"
---
# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a><span data-ttu-id="54d50-102">Verwenden der zweistufigen Authentifizierung mit lync-Client und lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54d50-102">Using two-factor authentication with Lync client and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54d50-103">_**Letztes Änderungsstand des Themas:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="54d50-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="54d50-104">In diesem Thema wird beschrieben, wie Sie die zweistufige Authentifizierung mit lync 2013-Client nutzen.</span><span class="sxs-lookup"><span data-stu-id="54d50-104">This topic described how to take advantage of two-factor authentication with Lync 2013 client.</span></span>

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a><span data-ttu-id="54d50-105">Erstmalige Anmeldung bei lync 2013</span><span class="sxs-lookup"><span data-stu-id="54d50-105">Sign in to Lync 2013 for the first time</span></span>

<span data-ttu-id="54d50-106">Die lync-Anmeldeinformationen werden normalerweise bei der Installation von lync 2013 automatisch konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="54d50-106">Your Lync sign-in information is usually configured automatically when Lync 2013 is installed.</span></span> <span data-ttu-id="54d50-107">Das erste Mal, wenn Sie lync verwenden, müssen Sie den Client möglicherweise manuell starten.</span><span class="sxs-lookup"><span data-stu-id="54d50-107">But the first time you use Lync, you might have to manually start the client.</span></span>

<span data-ttu-id="54d50-108">**So melden Sie sich zum ersten Mal bei lync an**</span><span class="sxs-lookup"><span data-stu-id="54d50-108">**To sign in to Lync for the first time**</span></span>

1.  <span data-ttu-id="54d50-109">Melden Sie sich beim Netzwerk Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="54d50-109">Log on to your organization’s network.</span></span>

2.  <span data-ttu-id="54d50-110">Wählen **Start** Sie \> **Alle Programme** starten \> **Microsoft \> lync lync 2013**aus.</span><span class="sxs-lookup"><span data-stu-id="54d50-110">Select **Start** \> **All Programs** \> **Microsoft Lync \> Lync 2013**.</span></span>
    
    <span data-ttu-id="54d50-111">Der lync-Anmeldebildschirm sollte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="54d50-111">You should see the Lync sign-in screen.</span></span>
    
      - <span data-ttu-id="54d50-112">Wenn das Feld Anmeldeadresse bereits ausgefüllt ist, vergewissern Sie sich, dass die angezeigte Adresse richtig ist.</span><span class="sxs-lookup"><span data-stu-id="54d50-112">If the sign-in address box is already filled in, confirm that the address shown is correct.</span></span>
    
      - <span data-ttu-id="54d50-113">Wenn es nicht richtig ist oder wenn das Feld leer ist, geben Sie Ihre lync-Anmeldeadresse ein (Dies ist normalerweise identisch mit Ihrer e-Mail-Adresse).</span><span class="sxs-lookup"><span data-stu-id="54d50-113">If it’s not correct, or if the box is empty, enter your Lync sign-in address (this is usually the same as your email address).</span></span>
    
      - <span data-ttu-id="54d50-114">Wenn das Feld leeres Kennwort angezeigt wird, fügen Sie Ihr Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="54d50-114">If an empty password box is displayed, add your password.</span></span>

3.  <span data-ttu-id="54d50-115">Wählen Sie **Anmelden**aus.</span><span class="sxs-lookup"><span data-stu-id="54d50-115">Select **Sign-in**.</span></span>

</div>

<div>

## <a name="sign-out-of-lync"></a><span data-ttu-id="54d50-116">Abmelden bei lync</span><span class="sxs-lookup"><span data-stu-id="54d50-116">Sign out of Lync</span></span>

<span data-ttu-id="54d50-117">Wenn Sie lync abgeschlossen haben, können Sie die Anzeige schließen, sich von Ihrer Sitzung abmelden oder aus dem Programm heraus beenden, und zwar im Menü Datei.</span><span class="sxs-lookup"><span data-stu-id="54d50-117">When you’re finished using Lync, you can close the display, sign out of your session, or exit from the program, all from the File menu.</span></span> <span data-ttu-id="54d50-118">In der folgenden Tabelle werden die Unterschiede in den Optionen erläutert.</span><span class="sxs-lookup"><span data-stu-id="54d50-118">The following table explains the differences in the options.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="54d50-119">Option</span><span class="sxs-lookup"><span data-stu-id="54d50-119">Option</span></span></th>
<th><span data-ttu-id="54d50-120">Funktion</span><span class="sxs-lookup"><span data-stu-id="54d50-120">What it does</span></span></th>
<th><span data-ttu-id="54d50-121">Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="54d50-121">How to perform it</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54d50-122">Schließen</span><span class="sxs-lookup"><span data-stu-id="54d50-122">Close</span></span></p></td>
<td><p><span data-ttu-id="54d50-123">Schließt die lync-Anzeige, lässt jedoch zu, dass die mit Ihrer Benutzer-ID identifizierte lync-Sitzung weiterhin ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="54d50-123">Closes your Lync display but lets the Lync session identified with your user ID continue to run.</span></span> <span data-ttu-id="54d50-124">Dies ist so, dass Sie weiterhin Benachrichtigungen erhalten und mit anderen Personen interagieren können.</span><span class="sxs-lookup"><span data-stu-id="54d50-124">This is so you can continue to get notifications and interact with others.</span></span></p>
<p><span data-ttu-id="54d50-125">Sie können die Anzeige jederzeit wiederherstellen, indem Sie auf der Taskleiste oder im Infobereich am unteren Rand des Bildschirms auf das lync-Symbol klicken.</span><span class="sxs-lookup"><span data-stu-id="54d50-125">You can get the display back at any time by clicking the Lync icon on the taskbar or the notification area at the bottom of your screen.</span></span></p></td>
<td><p><span data-ttu-id="54d50-126">Führen Sie im lync-Hauptfenster einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="54d50-126">On the Lync main window, do one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="54d50-127">Klicken Sie auf die Schaltfläche <strong>Optionen</strong> und anschließend auf <strong>Datei</strong> &gt; <strong>Schließen</strong>.</span><span class="sxs-lookup"><span data-stu-id="54d50-127">Select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Close</strong>.</span></span></p></li>
<li><p><span data-ttu-id="54d50-128">Klicken Sie in der oberen rechten Ecke des Fensters auf die Schaltfläche <strong>Schließen</strong> (X).</span><span class="sxs-lookup"><span data-stu-id="54d50-128">Click the <strong>Close</strong> button (X) in the upper-right corner of the window.</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54d50-129">Abmelden</span><span class="sxs-lookup"><span data-stu-id="54d50-129">Sign out</span></span></p></td>
<td><p><span data-ttu-id="54d50-130">Beendet die lync-Sitzung, die Ihrer Benutzer-ID zugeordnet ist, lync wird jedoch weiterhin im Hintergrund ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="54d50-130">Ends the Lync session associated with your user ID, but Lync continues to run in the background.</span></span> <span data-ttu-id="54d50-131">Wenn Sie sich abmelden, wird das Anmeldefenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="54d50-131">When you sign out, the sign-in window will appear.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="54d50-132">Wählen Sie beim abmelden die Option <STRONG>Meine Anmeldeinformationen löschen</STRONG> aus, um den Datensatz Ihrer Anmelde-ID und Ihres Kennworts vom Computer zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="54d50-132">Select <STRONG>Delete my sign-in information</STRONG> when you sign out to remove the record of your logon ID and password from the computer.</span></span> <span data-ttu-id="54d50-133">Dadurch wird möglicherweise die Unterstützung von Personen bei der Behandlung von Anmeldeproblemen erleichtert.</span><span class="sxs-lookup"><span data-stu-id="54d50-133">Doing this might make it easier for support people to troubleshoot sign-in issues.</span></span> <span data-ttu-id="54d50-134">Es kann auch dazu beitragen, dass Ihre Anmeldeinformationen sicherer sind, da unbefugte Benutzer sich nicht mit Ihren Anmeldeinformationen anmelden können.</span><span class="sxs-lookup"><span data-stu-id="54d50-134">It can also help ensure your sign-in information is more secure by making it difficult for unauthorized users to log on with your credentials.</span></span>


</div></td>
<td><p><span data-ttu-id="54d50-135">Wählen Sie im lync-Hauptfenster die Schaltfläche <strong>Optionen</strong> aus, und wählen Sie dann <strong>Datei</strong> &gt; <strong>Abmelden aus</strong>.</span><span class="sxs-lookup"><span data-stu-id="54d50-135">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Sign Out</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54d50-136">Beenden</span><span class="sxs-lookup"><span data-stu-id="54d50-136">Exit</span></span></p></td>
<td><p><span data-ttu-id="54d50-137">Beendet die lync-Sitzung und beendet lync auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="54d50-137">Ends your Lync session and shuts down Lync on your computer.</span></span> <span data-ttu-id="54d50-138">Wenn Sie lync nach dem Beenden neu starten möchten, wählen Sie <strong>Start</strong> &gt; <strong>Alle Programme</strong> starten &gt; <strong>Microsoft lync</strong> &gt; <strong>lync 2013</strong>aus.</span><span class="sxs-lookup"><span data-stu-id="54d50-138">After exiting, if you want to restart Lync, select <strong>Start</strong> &gt; <strong>All Programs</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</span></span></p></td>
<td><p><span data-ttu-id="54d50-139">Wählen Sie im lync-Hauptfenster die Schaltfläche <strong>Optionen</strong> aus, und wählen Sie dann <strong>Datei</strong> &gt; <strong>Beenden</strong>aus.</span><span class="sxs-lookup"><span data-stu-id="54d50-139">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Exit</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a><span data-ttu-id="54d50-140">Anmelden bei lync mit einer Smartcard</span><span class="sxs-lookup"><span data-stu-id="54d50-140">Sign in to Lync with a Smart Card</span></span>

<span data-ttu-id="54d50-141">Einige Organisationen verwenden jetzt einen mehrstufigen Anmeldevorgang, die sogenannte zweistufige Authentifizierung, um die Sicherheit für Ihre lync 2013 Benutzer zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="54d50-141">Some organizations now use a multi-step sign-in process, called two-factor authentication, to increase security for their Lync 2013 users.</span></span> <span data-ttu-id="54d50-142">Wenn Sie diese Option voraussichtlich verwenden, benötigen Sie eine Smartcard zur Anmeldung bei lync.</span><span class="sxs-lookup"><span data-stu-id="54d50-142">If you’re expected to use this option, you’ll need a “smart card” to sign in to Lync.</span></span> <span data-ttu-id="54d50-143">Smartcards gibt es in zwei Varianten: physisch und virtuell:</span><span class="sxs-lookup"><span data-stu-id="54d50-143">Smart cards come in two varieties, physical and virtual:</span></span>

  - <span data-ttu-id="54d50-144">**Physischer**     Computer Die Größe einer Kreditkarte.</span><span class="sxs-lookup"><span data-stu-id="54d50-144">**Physical**   About the size of a credit card.</span></span> <span data-ttu-id="54d50-145">Sie fügen es bei der Anmeldung in ein Smartcard-Lesegerät ein.</span><span class="sxs-lookup"><span data-stu-id="54d50-145">You insert it into a smart card reader when you log in.</span></span>

  - <span data-ttu-id="54d50-146">**Virtuell**     Es handelt sich nicht um ein physisches Objekt, sondern um eine elektronische ID, die auf einen speziellen Chip auf Ihrem Computer geschrieben wird, der im Wesentlichen die Smartcard in Ihren Computer einbaut.</span><span class="sxs-lookup"><span data-stu-id="54d50-146">**Virtual**   Not a physical object, but an electronic identifier that gets written to a special chip on your computer, which in essence builds the smart card into your computer.</span></span> <span data-ttu-id="54d50-147">Nur für die Verwendung mit Windows 8 Computern verfügbar, die den TPM-Chip (Trusted Platform Module) enthalten.</span><span class="sxs-lookup"><span data-stu-id="54d50-147">Available only for use with Windows 8 computers that contain the TPM (Trusted Platform Module) chip.</span></span>

<div>

## <a name="enroll-your-smart-card"></a><span data-ttu-id="54d50-148">Registrieren der Smartcard</span><span class="sxs-lookup"><span data-stu-id="54d50-148">Enroll your smart card</span></span>

<span data-ttu-id="54d50-149">Bevor Sie sich mit einer Smartcard anmelden können, muss die Karte "registriert" sein, d. h., Ihre Benutzeranmeldeinformationen müssen mit der Karte identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="54d50-149">Before you can sign in with a smart card, the card must be “enrolled”—that is, your user credentials have to be identified with the card.</span></span> <span data-ttu-id="54d50-150">Dies ist der Fall, wenn die Karte physisch oder virtuell ist.</span><span class="sxs-lookup"><span data-stu-id="54d50-150">This is the case whether the card is physical or virtual.</span></span> <span data-ttu-id="54d50-151">Dieser Vorgang wurde möglicherweise bereits von Ihrem lync Server Administrator ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="54d50-151">This process may already been carried out by your Lync Server administrator.</span></span> <span data-ttu-id="54d50-152">Wenden Sie sich an Sie, wenn Sie nicht sicher sind, ob dies geschehen ist.</span><span class="sxs-lookup"><span data-stu-id="54d50-152">Check with them if you’re not sure whether that has been done.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="54d50-153">Da jede virtuelle Smartcard nur dem Gerät zugeordnet ist, auf dem Sie installiert ist, muss für jeden Windows 8 von Ihnen verwendeten Computer eine separate Karte registriert werden.</span><span class="sxs-lookup"><span data-stu-id="54d50-153">Since each virtual smart card is associated only with the device it’s installed on, a separate card will need to be enrolled for each Windows 8 computer you use.</span></span>



</div>

<span data-ttu-id="54d50-154">**So registrieren Sie Ihre Smartcard manuell**</span><span class="sxs-lookup"><span data-stu-id="54d50-154">**To manually enroll your smart card**</span></span>

1.  <span data-ttu-id="54d50-155">Melden Sie sich an dem Computer an, auf dem Sie lync betreiben.</span><span class="sxs-lookup"><span data-stu-id="54d50-155">Log on to the computer you’ll be running Lync on.</span></span>

2.  <span data-ttu-id="54d50-156">Wechseln Sie mithilfe von Internet Explorer zur Webregistrierungs Seite der Zertifizierungsstelle Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="54d50-156">Using Internet Explorer, browse to your organization’s Certificate Authority Web Enrollment page.</span></span>
    
    <span data-ttu-id="54d50-157">Fragen Sie Ihren lync Server-Administrator nach der Webadresse dieser Ressource, wenn Sie Sie nicht bereits haben.</span><span class="sxs-lookup"><span data-stu-id="54d50-157">Ask your Lync Server administrator for the web address of this resource if you don’t already have it.</span></span> <span data-ttu-id="54d50-158">Die URL sieht in etwa wie folgt aus: https://MyCA.\ [YourCompanyName \] . com/certsrv.</span><span class="sxs-lookup"><span data-stu-id="54d50-158">The URL will look something like this: https://MyCA.\[yourcompanyname\].com/certsrv.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54d50-159">Wenn Sie Internet Explorer 10 verwenden, müssen Sie diese Website möglicherweise im Kompatibilitätsmodus anzeigen.</span><span class="sxs-lookup"><span data-stu-id="54d50-159">If you’re using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

3.  <span data-ttu-id="54d50-160">Wenn Sie aufgefordert werden, sich bei der Zertifizierungsseite anzumelden, melden Sie sich mit Ihrem Domänenkonto an (statt als Administrator Ihres Computers).</span><span class="sxs-lookup"><span data-stu-id="54d50-160">When you’re prompted to log on to the certification page, log on using your domain account (rather than as administrator of your computer).</span></span>

4.  <span data-ttu-id="54d50-161">Wählen Sie auf der Willkommensseite der Website die Option **Zertifikat anfordern**aus.</span><span class="sxs-lookup"><span data-stu-id="54d50-161">On the website Welcome Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="54d50-162">Wählen Sie **Erweiterte Anforderung**aus.</span><span class="sxs-lookup"><span data-stu-id="54d50-162">Select **Advanced Request**.</span></span>

6.  <span data-ttu-id="54d50-163">Wählen Sie **erstellen, und senden Sie eine Anforderung an diese Zertifizierungsstelle, und**klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="54d50-163">Select **Create and submit a request to this CA**, then click **Next**.</span></span>

7.  <span data-ttu-id="54d50-164">Jetzt sehen Sie eine Seite namens Smartcard-Registrierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="54d50-164">Now you’ll see a page called Smart Card Enrollment Station.</span></span> <span data-ttu-id="54d50-165">Genehmigen Sie die Anforderung zum Installieren des ActiveX-Steuerelements, und füllen Sie dann das Formular für die erweiterte Zertifikatanforderung wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="54d50-165">Approve the request to install the ActiveX control, and then complete the Advanced Certificate Request form as follows:</span></span>
    
    1.  <span data-ttu-id="54d50-166">Wählen Sie in der Dropdownliste **Zertifikatvorlage** die Option **Smartcard-Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="54d50-166">Select **Smartcard user** from the **Certificate Template** dropdown list.</span></span>
    
    2.  <span data-ttu-id="54d50-167">Wählen Sie **neuen Schlüssel festlegen erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="54d50-167">Select **Create new key set**.</span></span>
    
    3.  <span data-ttu-id="54d50-168">Suchen Sie die Herstellerinformationen auf dem Etikett Ihrer Smartcard, und wählen Sie diesen Hersteller in der Dropdownliste **CSP** aus.</span><span class="sxs-lookup"><span data-stu-id="54d50-168">Find the manufacturer information on the label of your smart card and select that manufacturer from the **CSP** dropdown list.</span></span>
    
    4.  <span data-ttu-id="54d50-169">Wählen Sie **CSP** als Anforderungs Format aus, sofern es nicht bereits ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="54d50-169">Select **CSP** as the Request Format, if it’s not already selected.</span></span>
    
    5.  <span data-ttu-id="54d50-170">Wählen Sie in der Dropdownliste Hash Algorithmus die Option **SHA1** aus, sofern Sie noch nicht ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="54d50-170">Select **sha1** from the Hash Algorithm dropdown list, if it’s not already selected.</span></span>
    
    6.  <span data-ttu-id="54d50-171">Geben Sie Ihrem Zertifikat einen Namen, den Sie erkennen, und klicken Sie auf über **Mitteln**.</span><span class="sxs-lookup"><span data-stu-id="54d50-171">Give your certificate a name you’ll recognize, and click **Submit**.</span></span>

8.  <span data-ttu-id="54d50-172">Legen Sie jetzt Ihre leere Smartcard in das Kartenlesegerät ein, das mit der Registrierungsstelle verbunden ist, und klicken Sie auf **registrieren**.</span><span class="sxs-lookup"><span data-stu-id="54d50-172">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

9.  <span data-ttu-id="54d50-173">Wenn Sie dazu aufgefordert werden, geben Sie Ihre persönliche Identifikationsnummer (PIN) ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="54d50-173">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54d50-174">Wenn Ihr technischer Support-Mitarbeiter Ihnen keine spezielle PIN für die Registrierung Ihrer Smartcard gegeben hat, verwenden Sie den standardmäßigen Smartcard-PIN-Wert, also 12345678.</span><span class="sxs-lookup"><span data-stu-id="54d50-174">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

10. <span data-ttu-id="54d50-175">Wählen Sie die Option aus, um zu erzwingen, dass der Benutzer die PIN ändert, wenn die Smartcard zum ersten Mal verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="54d50-175">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

11. <span data-ttu-id="54d50-176">Legen Sie jetzt Ihre leere Smartcard in das Kartenlesegerät ein, das mit der Registrierungsstelle verbunden ist, und klicken Sie auf **registrieren**.</span><span class="sxs-lookup"><span data-stu-id="54d50-176">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

12. <span data-ttu-id="54d50-177">Wenn Sie dazu aufgefordert werden, geben Sie Ihre persönliche Identifikationsnummer (PIN) ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="54d50-177">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54d50-178">Wenn Ihr technischer Support-Mitarbeiter Ihnen keine spezielle PIN für die Registrierung Ihrer Smartcard gegeben hat, verwenden Sie den standardmäßigen Smartcard-PIN-Wert, also 12345678.</span><span class="sxs-lookup"><span data-stu-id="54d50-178">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

13. <span data-ttu-id="54d50-179">Wählen Sie die Option aus, um zu erzwingen, dass der Benutzer die PIN ändert, wenn die Smartcard zum ersten Mal verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="54d50-179">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

14. <span data-ttu-id="54d50-180">Klicken Sie auf **OK** , um zu bestätigen, dass das angezeigte Zertifikat über Ihre Informationen verfügt.</span><span class="sxs-lookup"><span data-stu-id="54d50-180">Click **OK** to confirm that the certificate displayed has your information on it.</span></span>

15. <span data-ttu-id="54d50-181">Wenn Sie festgestellt haben, dass das Zertifikat ausgestellt wurde, klicken Sie auf **dieses Zertifikat installieren** , um den Registrierungsvorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="54d50-181">Once you see the notice that the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a><span data-ttu-id="54d50-182">Anmelden bei lync mit ihren Smartcard-Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="54d50-182">Sign in to Lync with your smart card credentials</span></span>

<span data-ttu-id="54d50-183">Bevor Sie Ihre Smartcard zum ersten Mal verwenden, sollten Sie auf der lync-Anmeldeseite auf **Meine Anmeldeinformationen löschen** klicken.</span><span class="sxs-lookup"><span data-stu-id="54d50-183">Before you use your smart card for the first time, it’s recommended that you click **Delete my sign-in info** on the Lync sign-in page.</span></span> <span data-ttu-id="54d50-184">Dadurch werden alle auf Ihrem Computer gespeicherten Anmeldeinformationen gelöscht, und eine mögliche Fehlerquelle wird eliminiert.</span><span class="sxs-lookup"><span data-stu-id="54d50-184">Doing this clears any sign-in credentials stored on your computer, and eliminates a possible source of error.</span></span>

<span data-ttu-id="54d50-185">**So melden Sie sich mit ihren Smartcard-Anmeldeinformationen bei lync an**</span><span class="sxs-lookup"><span data-stu-id="54d50-185">**To sign in to Lync with your smart card credentials**</span></span>

1.  <span data-ttu-id="54d50-186">Starten Sie den lync-Client.</span><span class="sxs-lookup"><span data-stu-id="54d50-186">Start the Lync client.</span></span>

2.  <span data-ttu-id="54d50-187">Geben Sie auf dem Anmeldebildschirm den Namen Ihres Anmeldebenutzer Kontos in das Feld **Anmeldeadresse** ein, und klicken Sie dann auf **Anmelden**.</span><span class="sxs-lookup"><span data-stu-id="54d50-187">On the Sign in screen, type your sign in user account name in the **Sign-in address** box, and then click **Sign In**.</span></span>

3.  <span data-ttu-id="54d50-188">Wenn Sie eine virtuelle Smartcard verwenden, überspringen Sie diesen Schritt.</span><span class="sxs-lookup"><span data-stu-id="54d50-188">If you are using a virtual smart card, skip this step.</span></span>
    
    <span data-ttu-id="54d50-189">Wenn Sie eine physische Smartcard verwenden, legen Sie die Smartcard in das Smartcard-Lesegerät ein, und klicken Sie dazu auf OK, und klicken Sie dann auf **OK** , wenn die Karte erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="54d50-189">If you are using a physical smart card, insert the smart card into your smart card reader and prompted to do so, and then click **OK** when the card is detected.</span></span>

4.  <span data-ttu-id="54d50-190">Geben Sie die PIN-Nummer für Ihre Smartcard ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="54d50-190">Type in the PIN number you for your smart card and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54d50-191">Wenn Sie Ihrer Support Person keine Smartcard-PIN-Nummer zugewiesen haben, verwenden Sie den Standardwert 12345678.</span><span class="sxs-lookup"><span data-stu-id="54d50-191">If you were not assigned a smart card PIN number by your support person, use the default value, which is 12345678.</span></span>

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

