---
title: 'Lync Server 2013: Konfigurieren der Verwendung von Fotos mit hoher Auflösung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the use of high-resolution photos in Lync Server 2013
ms:assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688150(v=OCS.15)
ms:contentKeyID: 49733753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efa45f6a7e3f561e56e5563b5024c84bb5731fd7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a><span data-ttu-id="11499-102">Konfigurieren der Verwendung von Fotos mit hoher Auflösung in Microsoft lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11499-102">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11499-103">_**Letztes Änderungsdatum des Themas:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="11499-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="11499-104">Microsoft lync Server 2010 bot Benutzern die Möglichkeit, Fotos Ihrer Kontakte anzuzeigen (und ihre eigenen Fotos anderen Personen zur Verfügung zu stellen).</span><span class="sxs-lookup"><span data-stu-id="11499-104">Microsoft Lync Server 2010 provided the ability for users to view photos of their contacts (and to make their own photos available to others).</span></span> <span data-ttu-id="11499-105">Diese Fotos wurden in der Regel als Teil des thumbnailPhoto-Attributs des Benutzers in Active Directory gespeichert.</span><span class="sxs-lookup"><span data-stu-id="11499-105">Typically these photos were stored as part of the user's thumbnailPhoto attribute in Active Directory.</span></span> <span data-ttu-id="11499-106">Dadurch wurde die Größe und Auflösung der Fotos schwerwiegend eingeschränkt: das thumbnailPhoto-Attribut kann nur ein Foto mit einer maximalen Größe von 48 Pixeln von 48 Pixeln enthalten.</span><span class="sxs-lookup"><span data-stu-id="11499-106">That placed a serious limitation on the size and resolution of the photos: the thumbnailPhoto attribute can only hold a photograph with a maximum size of 48 pixels by 48 pixels.</span></span>

<span data-ttu-id="11499-107">In Microsoft lync Server 2013 können Fotos jedoch im Microsoft Exchange Server 2013-Postfach eines Benutzers gespeichert werden. Damit können Foto Größen von bis zu 648 Pixeln von 648 Pixeln verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="11499-107">In Microsoft Lync Server 2013, however, photos can be stored in a user's Microsoft Exchange Server 2013 mailbox; that allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="11499-108">Darüber hinaus kann Exchange 2013 die Größe dieser Fotos für die Verwendung in unterschiedlichen Produkten nach Bedarf automatisch ändern.</span><span class="sxs-lookup"><span data-stu-id="11499-108">In addition to that, Exchange 2013 can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="11499-109">Das bedeutet in der Regel drei verschiedene Foto Größen und-Auflösungen:</span><span class="sxs-lookup"><span data-stu-id="11499-109">Typically that means three different photo sizes and resolutions:</span></span>

  - <span data-ttu-id="11499-110">48 Pixel um 48 Pixel, die für das Active Directory-thumbnailPhoto-Attribut verwendete Größe.</span><span class="sxs-lookup"><span data-stu-id="11499-110">48 pixels by 48 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="11499-111">Wenn Sie ein Foto in Exchange 2013 hochladen, erstellt Exchange automatisch eine 48 Pixel-Version des Fotos mit 48 Pixeln und aktualisiert das thumbnailPhoto-Attribut des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="11499-111">If you upload a photo to Exchange 2013 Exchange will automatically create a 48 pixel by 48 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="11499-112">Beachten Sie jedoch, dass umgekehrt nicht wahr ist: Wenn Sie das thumbnailPhoto-Attribut in Active Directory manuell aktualisieren, wird das Foto im Exchange 2013-Postfach des Benutzers nicht automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="11499-112">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange 2013 mailbox will not automatically be updated.</span></span>

  - <span data-ttu-id="11499-113">96 Pixel von 96 Pixeln für die Verwendung in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft lync Web App und lync 2013.</span><span class="sxs-lookup"><span data-stu-id="11499-113">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App, and Lync 2013.</span></span>

  - <span data-ttu-id="11499-114">648 Pixel von 648 Pixeln für die Verwendung in lync 2013 und Microsoft lync Web App.</span><span class="sxs-lookup"><span data-stu-id="11499-114">648 pixels by 648 pixels for use in Lync 2013 and Microsoft Lync Web App.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="11499-115">Wenn Sie über die Ressourcen verfügen, sollten Sie 648x648-Fotos hochladen. Dies bietet die maximale Auflösung und optimale Bildqualität in den Office 2013-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="11499-115">If you have the resources, it is recommended that you upload 648x648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications.</span></span> <span data-ttu-id="11499-116">Jedes JPEG-Foto mit einer Größe von 648x648 und einer Tiefe von 24 Bits führt zu einer Dateigröße von ungefähr 240 KB.</span><span class="sxs-lookup"><span data-stu-id="11499-116">Each JPEG photo with a size of 648x648 and a depth of 24 bits results in a file size of approximately 240 kilobytes.</span></span> <span data-ttu-id="11499-117">Das bedeutet, dass Sie für alle 4 Benutzer Fotos ungefähr 1 Megabyte Speicherplatz benötigen.</span><span class="sxs-lookup"><span data-stu-id="11499-117">That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span>



</div>

<span data-ttu-id="11499-118">Fotos mit hoher Auflösung, auf die über Exchange-Webdienste zugegriffen wird, können von Benutzern hochgeladen werden, die Outlook 2013 Web App ausführen. Benutzer dürfen nur Ihr eigenes Foto aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="11499-118">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="11499-119">Administratoren können das Foto allerdings mit der Exchange-Verwaltungsshell und einer Reihe von Windows PowerShell-Befehlen aktualisieren, die dem folgenden ähneln:</span><span class="sxs-lookup"><span data-stu-id="11499-119">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

<span data-ttu-id="11499-120">Der erste Befehl im vorherigen Beispiel verwendet das Cmdlet "Get-Content", um den Inhalt der Datei C:\\Fotos\\kenmyer. jpg zu lesen und diese Daten in einer Variablen mit dem Namen $Photo zu speichern.</span><span class="sxs-lookup"><span data-stu-id="11499-120">The first command in the preceding example uses the Get-Content cmdlet to read the contents of the file C:\\Photos\\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="11499-121">Im zweiten Befehl wird das Exchange-Cmdlet Satz-UserPhoto verwendet, um das Foto hochzuladen und dieses Foto an das Benutzerkonto von Ken Myers anzufügen.</span><span class="sxs-lookup"><span data-stu-id="11499-121">In the second command, the Exchange cmdlet Set-UserPhoto is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="11499-122">In diesem Beispiel wird der Active Directory-Anzeigename von Ken Myer als Benutzerkontoidentität verwendet.</span><span class="sxs-lookup"><span data-stu-id="11499-122">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="11499-123">Sie können ein Benutzerkonto auch über andere IDs wie die SMTP-Adresse des Benutzers oder dessen Benutzerprinzipalnamen referenzieren.</span><span class="sxs-lookup"><span data-stu-id="11499-123">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="11499-124">Weitere Informationen finden Sie in <A href="http://go.microsoft.com/fwlink/p/?linkid=268536">http://go.microsoft.com/fwlink/p/?LinkId=268536</A> der Dokumentation für das Cmdlet "Satz-UserPhoto".</span><span class="sxs-lookup"><span data-stu-id="11499-124">See the documentation for the Set-UserPhoto cmdlet at <A href="http://go.microsoft.com/fwlink/p/?linkid=268536">http://go.microsoft.com/fwlink/p/?LinkId=268536</A> for more information</span></span>



</div>

<span data-ttu-id="11499-p108">Das Hochladen des Fotos entspricht keiner Zuweisung des Fotos zu Ken Myers Benutzerkonto. Durch das Hochladen wird einfach eine Vorschau dieses Fotos auf der Seite der Outlook Web App-Optionen angezeigt. Damit dieses Foto dem Benutzerkonto zugewiesen wird, muss der Benutzer auf der Seite mit den Optionen auf **Speichern** klicken oder der Administrator muss den dritten Befehl des Beispiels ausführen. Dieser dritte Befehl weist das Foto mithilfe des Parameters „Save“ dem Benutzerkonto von Ken Myer zu:</span><span class="sxs-lookup"><span data-stu-id="11499-p108">Uploading the photo does not equate to assigning that photo to Ken Myer's user account. Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page. To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example. That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

<span data-ttu-id="11499-129">Um zu überprüfen, ob das neue Foto dem Benutzerkonto zugewiesen wurde, kann Ken Myers sich bei lync 2013 anmelden, **Optionen**auswählen und dann **mein Bild**auswählen.</span><span class="sxs-lookup"><span data-stu-id="11499-129">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Lync 2013, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="11499-130">Das neu hochgeladene Foto sollte dann als Kens persönliches Foto angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="11499-130">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="11499-131">Alternativ können Administratoren die Fotos aller Benutzer prüfen, indem sie den Internet Explorer starten und zu einer URL der folgenden Art navigieren:</span><span class="sxs-lookup"><span data-stu-id="11499-131">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

<span data-ttu-id="11499-132">Wenn der Administrator das Foto mit Internet Explorer anzeigen kann, der Benutzer aber sein Foto in lync 2013 nicht anzeigen kann, weist dies in der Regel auf ein Verbindungsproblem mit Exchange-Webdiensten oder dem Exchange-AutoErmittlungsdienst hin.</span><span class="sxs-lookup"><span data-stu-id="11499-132">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Lync 2013, that typically indicates a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>

<span data-ttu-id="11499-133">Beachten Sie auch, dass keine zusätzliche Konfiguration erforderlich ist, um dieses Foto in lync 2013 zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="11499-133">Note, too that no additional configuration is required in order to make this photo available in Lync 2013.</span></span> <span data-ttu-id="11499-134">Stattdessen ist das Foto unmittelbar verfügbar, nachdem es hochgeladen und das Cmdlet „Set-UserPhoto“ ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="11499-134">Instead, the photo will be instantly available after it has been uploaded and the Set-UserPhoto cmdlet has been run.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

