---
title: 'Lync Server 2013: Registrieren von Benutzern für die Smartcard-Authentifizierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enrolling users for smart card authentication
ms:assetid: a6445a83-a94b-423f-ba2a-12b5f84c5d75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308570(v=OCS.15)
ms:contentKeyID: 54973691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 635565936712fe542c807ea4d4c65f584e836bdc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137424"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="9625b-102">Registrieren von Benutzern für die Smartcard-Authentifizierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9625b-102">Enrolling users for smart card authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9625b-103">_**Letztes Änderungsstand des Themas:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="9625b-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="9625b-104">Im Allgemeinen gibt es zwei Methoden für die Registrierung von Benutzern für die Smartcard-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9625b-104">There are generally two methods for enrolling users for smart card authentication.</span></span> <span data-ttu-id="9625b-105">Die einfachere Methode besteht darin, dass Benutzer sich direkt für die Smartcard-Authentifizierung mithilfe der Webregistrierung registrieren, während die komplexere Methode einen Registrierungs-Agent verwendet.</span><span class="sxs-lookup"><span data-stu-id="9625b-105">The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent.</span></span> <span data-ttu-id="9625b-106">Dieses Thema konzentriert sich auf die Selbstregistrierung für Smartcard-Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="9625b-106">This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="9625b-107">Weitere Informationen zur Registrierung im Namen von Benutzern als Registrierungs-Agent finden Sie unter Registrieren für Zertifikate im Namen anderer Benutzer unter [https://go.microsoft.com/fwlink/p/?LinkID=313367](https://go.microsoft.com/fwlink/p/?linkid=313367).</span><span class="sxs-lookup"><span data-stu-id="9625b-107">For more information on enrolling on behalf of users as an enrollment agent, see Enroll for Certificates on Behalf of Other Users at [https://go.microsoft.com/fwlink/p/?LinkID=313367](https://go.microsoft.com/fwlink/p/?linkid=313367).</span></span>

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="9625b-108">So registrieren Sie Benutzer für die Smartcard-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="9625b-108">To Enroll Users for Smart Card Authentication</span></span>

1.  <span data-ttu-id="9625b-109">Melden Sie sich mit den Anmeldeinformationen eines lync-aktivierten Benutzers bei der Windows 8-Workstation an.</span><span class="sxs-lookup"><span data-stu-id="9625b-109">Log in to the Windows 8 workstation using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="9625b-110">Starten Sie Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="9625b-110">Launch Internet Explorer.</span></span>

3.  <span data-ttu-id="9625b-111">Wechseln Sie zur **Webregistrierungs Seite der Zertifizierungsstelle** (beispielsweise https://MyCA.contoso.com/certsrv)</span><span class="sxs-lookup"><span data-stu-id="9625b-111">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9625b-112">Wenn Sie Internet Explorer 10 verwenden, müssen Sie diese Website möglicherweise im Kompatibilitätsmodus anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9625b-112">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

4.  <span data-ttu-id="9625b-113">Wählen Sie auf der **Willkommens** Seite **ein Zertifikat anfordern**aus.</span><span class="sxs-lookup"><span data-stu-id="9625b-113">On the **Welcome** Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="9625b-114">Wählen Sie dann **Erweiterte Anforderung**aus.</span><span class="sxs-lookup"><span data-stu-id="9625b-114">Next, select **Advanced Request**.</span></span>

6.  <span data-ttu-id="9625b-115">Wählen Sie **erstellen, und senden Sie eine Anforderung an diese Zertifizierungsstelle**.</span><span class="sxs-lookup"><span data-stu-id="9625b-115">Select **Create and submit a request to this CA**.</span></span>

7.  <span data-ttu-id="9625b-116">Wählen Sie **Smartcard-Benutzer** im Abschnitt **Zertifikatvorlage** aus, und schließen Sie die erweiterte Zertifikatanforderung mit den folgenden Werten ab:</span><span class="sxs-lookup"><span data-stu-id="9625b-116">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>
    
      - <span data-ttu-id="9625b-117">**Schlüsseloptionen** bestätigen die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="9625b-117">**Key Options** confirm he following settings:</span></span>
        
          - <span data-ttu-id="9625b-118">Optionsfeld " **neuen Tastenkombination erstellen** " auswählen</span><span class="sxs-lookup"><span data-stu-id="9625b-118">Select the **Create new key set** radio button</span></span>
        
          - <span data-ttu-id="9625b-119">Wählen Sie für **CSP**die Option **Microsoft Base Smart Card Crypto Provider** aus.</span><span class="sxs-lookup"><span data-stu-id="9625b-119">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>
        
          - <span data-ttu-id="9625b-120">Wählen Sie für die **Schlüsselverwendung** **Exchange** aus (Dies ist die einzige verfügbare Option).</span><span class="sxs-lookup"><span data-stu-id="9625b-120">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>
        
          - <span data-ttu-id="9625b-121">Geben Sie für die **Schlüsselgröße** **2048**</span><span class="sxs-lookup"><span data-stu-id="9625b-121">For **Key Size**, enter **2048**</span></span>
        
          - <span data-ttu-id="9625b-122">Bestätigen, dass der **Name des automatischen Schlüsselcontainers** ausgewählt ist</span><span class="sxs-lookup"><span data-stu-id="9625b-122">Confirm that **Automatic key container name** is selected</span></span>
        
          - <span data-ttu-id="9625b-123">Lassen Sie die anderen Felder deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="9625b-123">Leave the other boxes unchecked.</span></span>
    
      - <span data-ttu-id="9625b-124">Bestätigen Sie unter **zusätzliche Optionen** die folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="9625b-124">Under **Additional Options** confirm the following values:</span></span>
        
          - <span data-ttu-id="9625b-125">Für das **Anforderungs Format** wählen Sie **CMC**aus.</span><span class="sxs-lookup"><span data-stu-id="9625b-125">For **Request Format** select **CMC**.</span></span>
        
          - <span data-ttu-id="9625b-126">Für **Hash Algorithmus** wählen Sie **SHA1**aus.</span><span class="sxs-lookup"><span data-stu-id="9625b-126">For **Hash Algorithm** select **sha1**.</span></span>
        
          - <span data-ttu-id="9625b-127">Geben Sie für **Anzeige Name** das **Smardcard-Zertifikat**ein.</span><span class="sxs-lookup"><span data-stu-id="9625b-127">For **Friendly Name** enter **Smardcard Certificate**.</span></span>

8.  <span data-ttu-id="9625b-128">Wenn Sie einen physischen Smartcard-Leser verwenden, legen Sie die Smartcard in das Gerät ein.</span><span class="sxs-lookup"><span data-stu-id="9625b-128">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9.  <span data-ttu-id="9625b-129">Klicken Sie auf über **Mitteln** , um die Zertifikatanforderung zu senden.</span><span class="sxs-lookup"><span data-stu-id="9625b-129">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="9625b-130">Wenn Sie dazu aufgefordert werden, geben Sie die PIN ein, die zum Erstellen der virtuellen Smartcard verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="9625b-130">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9625b-131">Der standardmäßige virtuelle Smartcard-PIN-Wert lautet "12345678".</span><span class="sxs-lookup"><span data-stu-id="9625b-131">The default virtual smart card PIN value is ‘12345678’.</span></span>

    
    </div>

11. <span data-ttu-id="9625b-132">Nachdem das Zertifikat ausgestellt wurde, klicken Sie auf **dieses Zertifikat installieren** , um den Registrierungsvorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="9625b-132">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9625b-133">Wenn Ihre Zertifikatanforderung mit dem Fehler "dieser Webbrowser unterstützt nicht die Generierung von Zertifikatanforderungen" fehlschlägt, gibt es drei Möglichkeiten, das Problem zu beheben:</span><span class="sxs-lookup"><span data-stu-id="9625b-133">If your certificate request fails with the error “This Web browser does not support the generation of certificate requests,” there are three possible ways to resolve the issue:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="9625b-134">Aktivieren der Kompatibilitätsansicht in Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="9625b-134">Enable Compatibility View in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="9625b-135">Aktivieren Sie die Option Intranet-Einstellungen aktivieren in Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="9625b-135">Enable the Turn on Intranet settings option in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="9625b-136">Aktivieren Sie im Menü Internet Explorer Optionen die Einstellung alle Zonen auf Standardebene Zurücksetzen auf der Registerkarte Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="9625b-136">Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.</span></span></P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

