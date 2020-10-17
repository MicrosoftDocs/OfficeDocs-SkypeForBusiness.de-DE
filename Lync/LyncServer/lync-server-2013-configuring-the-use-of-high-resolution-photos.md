---
title: 'Lync Server 2013: Konfigurieren der Verwendung von hochauflösenden Fotos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the use of high-resolution photos in Lync Server 2013
ms:assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688150(v=OCS.15)
ms:contentKeyID: 49733753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e817e86d6f05291192593e2345b9e4bc1c0b6db3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517352"
---
# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a><span data-ttu-id="9a4ad-102">Konfigurieren der Verwendung von hochauflösenden Fotos in Microsoft lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a4ad-102">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a4ad-103">_**Letztes Änderungsstand des Themas:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="9a4ad-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="9a4ad-104">Microsoft lync Server 2010 haben Benutzern die Möglichkeit geboten, Fotos Ihrer Kontakte anzuzeigen (und ihren eigenen Fotos für andere zur Verfügung zu stellen).</span><span class="sxs-lookup"><span data-stu-id="9a4ad-104">Microsoft Lync Server 2010 provided the ability for users to view photos of their contacts (and to make their own photos available to others).</span></span> <span data-ttu-id="9a4ad-105">In der Regel werden diese Fotos als Teil des thumbnailPhoto-Attributs des Benutzers in Active Directory gespeichert.</span><span class="sxs-lookup"><span data-stu-id="9a4ad-105">Typically these photos were stored as part of the user's thumbnailPhoto attribute in Active Directory.</span></span> <span data-ttu-id="9a4ad-106">Dies bringt eine strenge Beschränkung der Größe und Auflösung der Fotos mit sich: Das Attribut "thumbnailPhoto" kann lediglich Fotos einer Größe von maximal 48 x 48 Pixel aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="9a4ad-106">That placed a serious limitation on the size and resolution of the photos: the thumbnailPhoto attribute can only hold a photograph with a maximum size of 48 pixels by 48 pixels.</span></span>

<span data-ttu-id="9a4ad-107">In Microsoft lync Server 2013 können Fotos jedoch im Microsoft Exchange Server 2013 Postfach eines Benutzers gespeichert werden; Das ermöglicht Foto Größen von bis zu 648 Pixeln von 648 Pixel.</span><span class="sxs-lookup"><span data-stu-id="9a4ad-107">In Microsoft Lync Server 2013, however, photos can be stored in a user's Microsoft Exchange Server 2013 mailbox; that allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="9a4ad-108">Darüber hinaus können Exchange 2013 diese Fotos bei Bedarf automatisch für die Verwendung in unterschiedlichen Produkten anpassen.</span><span class="sxs-lookup"><span data-stu-id="9a4ad-108">In addition to that, Exchange 2013 can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="9a4ad-109">Normalerweise bedeutet dies drei verschiedene Foto Größen und-Auflösungen:</span><span class="sxs-lookup"><span data-stu-id="9a4ad-109">Typically that means three different photo sizes and resolutions:</span></span>

  - <span data-ttu-id="9a4ad-110">48 x 48 Pixel - die für das Active Directory thumbnailPhoto-Attribut verwendete Größe.</span><span class="sxs-lookup"><span data-stu-id="9a4ad-110">48 pixels by 48 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="9a4ad-111">Wenn Sie ein Foto in Exchange 2013 hochladen, erstellt Exchange automatisch eine Pixel Version von 48 Pixel für 48 dieses Fotos und aktualisiert das thumbnailPhoto-Attribut des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="9a4ad-111">If you upload a photo to Exchange 2013 Exchange will automatically create a 48 pixel by 48 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="9a4ad-112">Beachten Sie jedoch, dass die umgekehrte nicht true ist: Wenn Sie das thumbnailPhoto-Attribut in Active Directory das Foto im Exchange 2013 Postfach des Benutzers nicht automatisch aktualisiert wird, manuell aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="9a4ad-112">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange 2013 mailbox will not automatically be updated.</span></span>

  - <span data-ttu-id="9a4ad-113">96 Pixel um 96 Pixel, zur Verwendung in Microsoft Outlook 2013-Webanwendung, Microsoft Outlook 2013, Microsoft lync Web App und lync 2013.</span><span class="sxs-lookup"><span data-stu-id="9a4ad-113">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App, and Lync 2013.</span></span>

  - <span data-ttu-id="9a4ad-114">648 Pixel durch 648 Pixel für die Verwendung in lync 2013 und Microsoft lync Web App.</span><span class="sxs-lookup"><span data-stu-id="9a4ad-114">648 pixels by 648 pixels for use in Lync 2013 and Microsoft Lync Web App.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9a4ad-p104">Sofern Sie ausreichende Ressourcen besitzen, empfiehlt es sich, Fotos im Format 648 x 648 Pixel hochzuladen. Dies sorgt für eine maximale Auflösung und optimale Bildqualität in allen Office 2013-Anwendungen. Ein JPEG-Foto mit 648 x 648 Pixel und einer Tiefe von 24 Bit ergibt eine Datei mit einer Größe von rund 240 KB. Dies bedeutet, dass Sie für je vier Benutzerfotos rund ein MB Festplattenspeicher benötigen.</span><span class="sxs-lookup"><span data-stu-id="9a4ad-p104">If you have the resources, it is recommended that you upload 648x648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications. Each JPEG photo with a size of 648x648 and a depth of 24 bits results in a file size of approximately 240 kilobytes. That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span>



</div>

<span data-ttu-id="9a4ad-118">Hochauflösende Fotos, auf die mithilfe von Exchange Webdienste zugegriffen werden kann, können von Benutzern hochgeladen werden, die Outlook 2013-Webanwendung ausführt; Benutzer dürfen Ihr eigenes Foto nur aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="9a4ad-118">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="9a4ad-119">Administratoren können das Foto allerdings mit dem Exchange-Verwaltungsshell und einer Reihe von Windows PowerShell Befehlen, die dem folgenden ähneln, aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="9a4ad-119">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

<span data-ttu-id="9a4ad-120">Der erste Befehl im vorherigen Beispiel verwendet das Get-Content-Cmdlet, um den Inhalt der Datei C: \\ FotosKenmyer.jpg zu lesen \\ und diese Daten in einer Variablen mit dem Namen "$Photo" zu speichern.</span><span class="sxs-lookup"><span data-stu-id="9a4ad-120">The first command in the preceding example uses the Get-Content cmdlet to read the contents of the file C:\\Photos\\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="9a4ad-121">Im zweiten Befehl wird das Exchange-Cmdlet Set-UserPhoto verwendet, um das Foto hochzuladen und das Foto an das Benutzerkonto von Ken Myers anzufügen.</span><span class="sxs-lookup"><span data-stu-id="9a4ad-121">In the second command, the Exchange cmdlet Set-UserPhoto is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9a4ad-122">In diesem Beispiel wird der Active Directory-Anzeigename von Ken Myer als Benutzerkontoidentität verwendet.</span><span class="sxs-lookup"><span data-stu-id="9a4ad-122">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="9a4ad-123">Sie können ein Benutzerkonto auch über andere IDs referenzieren, wie die SMTP-Adresse des Benutzers oder dessen Benutzerprinzipalnamen.</span><span class="sxs-lookup"><span data-stu-id="9a4ad-123">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="9a4ad-124">Weitere Informationen finden Sie in der Dokumentation für das Set-UserPhoto-Cmdlet unter. <A href="https://go.microsoft.com/fwlink/p/?linkid=268536">https://go.microsoft.com/fwlink/p/?LinkId=268536</A></span><span class="sxs-lookup"><span data-stu-id="9a4ad-124">See the documentation for the Set-UserPhoto cmdlet at <A href="https://go.microsoft.com/fwlink/p/?linkid=268536">https://go.microsoft.com/fwlink/p/?LinkId=268536</A> for more information</span></span>



</div>

<span data-ttu-id="9a4ad-p108">Das Hochladen des Fotos entspricht keiner Zuweisung des Fotos zu Ken Myers Benutzerkonto. Das Hochladen des Fotos führt einfach nur dazu, dass eine Vorschau des Fotos auf der Seite der Outlook Web App-Optionen angezeigt wird. Damit das Foto dem Benutzerkonto zugewiesen wird, muss der Benutzer auf der Seite mit den Optionen auf **Speichern** klicken oder der Administrator muss den dritten Befehl des Beispiels ausführen. Dieser dritte Befehl benutzt den Save-Parameter, um das Foto dem Benutzerkonto von Ken Myer zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="9a4ad-p108">Uploading the photo does not equate to assigning that photo to Ken Myer's user account. Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page. To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example. That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

<span data-ttu-id="9a4ad-129">Um zu überprüfen, ob das neue Foto dem Benutzerkonto zugewiesen wurde, kann Ken Myers sich bei lync 2013 anmelden, **Optionen**auswählen und dann **mein Bild**auswählen.</span><span class="sxs-lookup"><span data-stu-id="9a4ad-129">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Lync 2013, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="9a4ad-130">Das neu hochgeladene Foto sollte dann als Kens persönliches Foto angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9a4ad-130">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="9a4ad-131">Alternativ können Administratoren die Fotos aller Benutzer prüfen, indem sie den Internet Explorer starten und zu einer URL der folgenden Art navigieren:</span><span class="sxs-lookup"><span data-stu-id="9a4ad-131">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

<span data-ttu-id="9a4ad-132">Wenn der Administrator das Foto mit Internet Explorer anzeigen kann, der Benutzer aber sein Foto nicht in lync 2013 anzeigen kann, deutet dies normalerweise auf ein Verbindungsproblem mit Exchange Webdienste oder dem Exchange-AutoErmittlungsdienst hin.</span><span class="sxs-lookup"><span data-stu-id="9a4ad-132">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Lync 2013, that typically indicates a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>

<span data-ttu-id="9a4ad-133">Beachten Sie auch, dass keine zusätzliche Konfiguration erforderlich ist, um dieses Foto in lync 2013 zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="9a4ad-133">Note, too that no additional configuration is required in order to make this photo available in Lync 2013.</span></span> <span data-ttu-id="9a4ad-134">Stattdessen ist das Foto sofort verfügbar, nachdem es hochgeladen wurde und das Set-UserPhoto-Cmdlet ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="9a4ad-134">Instead, the photo will be instantly available after it has been uploaded and the Set-UserPhoto cmdlet has been run.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

