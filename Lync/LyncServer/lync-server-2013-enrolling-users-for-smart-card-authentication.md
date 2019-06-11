---
title: 'Lync Server 2013: Registrieren von Benutzern für die Smartcard-Authentifizierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enrolling users for smart card authentication
ms:assetid: a6445a83-a94b-423f-ba2a-12b5f84c5d75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308570(v=OCS.15)
ms:contentKeyID: 54973691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11e74f35119a083aacd8440aec53594b8091b8e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="5a7dd-102">Registrieren von Benutzern für die Smartcard-Authentifizierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a7dd-102">Enrolling users for smart card authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a7dd-103">_**Letztes Änderungsdatum des Themas:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="5a7dd-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="5a7dd-p101">Allgemein bestehen zwei Verfahren für das Registrieren von Benutzern für die SmartCard-Authentifizierung. Das einfachere Verfahren sieht die direkte Registrierung der Benutzer für die SmartCard-Authentifizierung mithilfe der Webregistrierung vor, während bei der komplexeren Methode ein Enrollment Agent verwendet wird. Dieses Thema legt den Schwerpunkt auf die Selbstregistrierung der Benutzer für SmartCard-Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="5a7dd-p101">There are generally two methods for enrolling users for smart card authentication. The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent. This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="5a7dd-107">Weitere Informationen zur Registrierung für Benutzer als Registrierungs-Agent finden Sie unter Registrieren für Zertifikate im Auftrag anderer Benutzer unter [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367).</span><span class="sxs-lookup"><span data-stu-id="5a7dd-107">For more information on enrolling on behalf of users as an enrollment agent, see Enroll for Certificates on Behalf of Other Users at [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367).</span></span>

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="5a7dd-108">So registrieren Sie Benutzer für die SmartCard-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="5a7dd-108">To Enroll Users for Smart Card Authentication</span></span>

1.  <span data-ttu-id="5a7dd-109">Melden Sie sich mit den Anmeldeinformationen eines lync-fähigen Benutzers bei der Windows 8-Workstation an.</span><span class="sxs-lookup"><span data-stu-id="5a7dd-109">Log in to the Windows 8 workstation using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="5a7dd-110">Starten Sie Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="5a7dd-110">Launch Internet Explorer.</span></span>

3.  <span data-ttu-id="5a7dd-111">Navigieren Sie zur **Website Registrierungs** Seite für die Zertifizierungsstelle https://MyCA.contoso.com/certsrv)(z. b.</span><span class="sxs-lookup"><span data-stu-id="5a7dd-111">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5a7dd-112">Wenn Sie Internet Explorer 10 verwenden, müssen Sie diese Website möglicherweise im Kompatibilitätsmodus anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5a7dd-112">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

4.  <span data-ttu-id="5a7dd-113">Wählen Sie auf der Seite **Willkommen** die Option **Zertifikat anfordern** aus.</span><span class="sxs-lookup"><span data-stu-id="5a7dd-113">On the **Welcome** Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="5a7dd-114">Wählen Sie im nächsten Schritt **Erweiterte Anforderung** aus.</span><span class="sxs-lookup"><span data-stu-id="5a7dd-114">Next, select **Advanced Request**.</span></span>

6.  <span data-ttu-id="5a7dd-115">Wählen Sie **Eine Anforderung an diese Zertifizierungsstelle erstellen und einreichen** aus.</span><span class="sxs-lookup"><span data-stu-id="5a7dd-115">Select **Create and submit a request to this CA**.</span></span>

7.  <span data-ttu-id="5a7dd-116">Wählen Sie im Abschnitt **Zertifikatvorlage** den Eintrag **SmartCard-Benutzer** aus und füllen Sie die erweiterte Zertifikatanforderung mit den folgenden Werten aus:</span><span class="sxs-lookup"><span data-stu-id="5a7dd-116">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>
    
      - <span data-ttu-id="5a7dd-117">**Schlüsseloptionen** – bestätigen Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="5a7dd-117">**Key Options** confirm he following settings:</span></span>
        
          - <span data-ttu-id="5a7dd-118">Aktivieren Sie das Optionsfeld **Neuen Schlüsselsatz erstellen**</span><span class="sxs-lookup"><span data-stu-id="5a7dd-118">Select the **Create new key set** radio button</span></span>
        
          - <span data-ttu-id="5a7dd-119">Wählen Sie für **CSP** die Option **Microsoft Basis-SmartCard-Krypto-Anbieter**</span><span class="sxs-lookup"><span data-stu-id="5a7dd-119">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>
        
          - <span data-ttu-id="5a7dd-120">Wählen Sie für **Schlüsselverwendung** den Wert **Exchange** aus (dies ist die einzige verfügbare Option).</span><span class="sxs-lookup"><span data-stu-id="5a7dd-120">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>
        
          - <span data-ttu-id="5a7dd-121">Geben Sie unter **Schlüsselgröße** den Wert **2048** ein</span><span class="sxs-lookup"><span data-stu-id="5a7dd-121">For **Key Size**, enter **2048**</span></span>
        
          - <span data-ttu-id="5a7dd-122">Überprüfen Sie, ob **Automatischer Schlüsselcontainername** aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="5a7dd-122">Confirm that **Automatic key container name** is selected</span></span>
        
          - <span data-ttu-id="5a7dd-123">Lassen Sie die anderen Felder deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="5a7dd-123">Leave the other boxes unchecked.</span></span>
    
      - <span data-ttu-id="5a7dd-124">Bestätigen Sie unter **Weitere Optionen** die folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="5a7dd-124">Under **Additional Options** confirm the following values:</span></span>
        
          - <span data-ttu-id="5a7dd-125">Wählen Sie für **Anforderungsformat** den Wert **CMC** aus.</span><span class="sxs-lookup"><span data-stu-id="5a7dd-125">For **Request Format** select **CMC**.</span></span>
        
          - <span data-ttu-id="5a7dd-126">Wählen Sie für **Hashalgorithmus** den Wert **sha1** aus.</span><span class="sxs-lookup"><span data-stu-id="5a7dd-126">For **Hash Algorithm** select **sha1**.</span></span>
        
          - <span data-ttu-id="5a7dd-127">Geben Sie als **Anzeigename** den Wert **Smardcard Certificate** ein.</span><span class="sxs-lookup"><span data-stu-id="5a7dd-127">For **Friendly Name** enter **Smardcard Certificate**.</span></span>

8.  <span data-ttu-id="5a7dd-128">Wenn Sie ein physisches Smartcard-Lesegerät verwenden, setzen Sie die SmartCard in das Gerät ein.</span><span class="sxs-lookup"><span data-stu-id="5a7dd-128">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9.  <span data-ttu-id="5a7dd-129">Klicken Sie auf **Senden**, um die Zertifikatanforderung einzureichen.</span><span class="sxs-lookup"><span data-stu-id="5a7dd-129">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="5a7dd-130">Wenn Sie dazu aufgefordert werden, geben Sie die PIN ein, die zum Erstellen der virtuellen SmartCard verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="5a7dd-130">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5a7dd-131">Der Standardwert der PIN für virtuelle SmartCards ist „12345678“.</span><span class="sxs-lookup"><span data-stu-id="5a7dd-131">The default virtual smart card PIN value is ‘12345678’.</span></span>

    
    </div>

11. <span data-ttu-id="5a7dd-132">Nachdem das Zertifikat ausgestellt wurde, klicken Sie auf **Dieses Zertifikat installieren**, um den Registrierungsvorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="5a7dd-132">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5a7dd-133">Wenn bei der Zertifikatanforderung ein Fehler mit der Meldung „Der Webbrowser unterstützt nicht die Generierung von Zertifikatanforderungen“ auftritt, kann das Problem auf drei verschiedene Weisen gelöst werden:</span><span class="sxs-lookup"><span data-stu-id="5a7dd-133">If your certificate request fails with the error “This Web browser does not support the generation of certificate requests,” there are three possible ways to resolve the issue:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="5a7dd-134">Aktivieren Sie in Internet Explorer die Kompatibilitätsansicht</span><span class="sxs-lookup"><span data-stu-id="5a7dd-134">Enable Compatibility View in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="5a7dd-135">Aktivieren Sie die Option „Intraneteinstellungen einschalten“ in Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="5a7dd-135">Enable the Turn on Intranet settings option in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="5a7dd-136">Aktivieren Sie in den Internet Explorer-Optionen auf der Registerkarte „Sicherheit“ die Einstellung „Alle Zonen auf Standardstufe zurücksetzen“.</span><span class="sxs-lookup"><span data-stu-id="5a7dd-136">Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.</span></span></P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

