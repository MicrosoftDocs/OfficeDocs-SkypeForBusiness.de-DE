---
title: Konfigurieren der Verwendung von Fotos mit hoher Auflösung in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: 'Zusammenfassung: Konfigurieren Sie die Verwendung von Fotos mit hoher Auflösung in Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 oder Exchange Online und Skype for Business Server.'
ms.openlocfilehash: 08db547dc9ead9d79a50cd17b4496826aa735369
ms.sourcegitcommit: de7e0afbd40bbe52994ab99d85cf9e95ecbc4a6c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2019
ms.locfileid: "37434910"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a><span data-ttu-id="a3a38-103">Konfigurieren der Verwendung von Fotos mit hoher Auflösung in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a3a38-103">Configure the use of high-resolution photos in Skype for Business Server</span></span>
 
<span data-ttu-id="a3a38-104">**Zusammenfassung:** Konfigurieren Sie die Verwendung von Fotos mit hoher Auflösung in Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 oder Exchange Online und Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a3a38-104">**Summary:** Configure the use of high-resolution photos in Exchange Server 2019, Exchange Server 2016, Exchange Server 2013, or Exchange Online and Skype for Business Server.</span></span>
  
<span data-ttu-id="a3a38-105">In Skype for Business Server können Fotos in Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 oder Exchange Online-Postfach gespeichert werden, wodurch Foto Größen von bis zu 648 Pixeln um 648 Pixel möglich sind.</span><span class="sxs-lookup"><span data-stu-id="a3a38-105">In Skype for Business Server, photos can be stored in a user's Exchange Server 2019, Exchange Server 2016, Exchange Server 2013, or Exchange Online mailbox, which allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="a3a38-106">Darüber hinaus kann Exchange Server die Größe dieser Fotos für die Verwendung in verschiedenen Produkten nach Bedarf automatisch ändern.</span><span class="sxs-lookup"><span data-stu-id="a3a38-106">In addition, Exchange Server can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="a3a38-107">Das bedeutet in der Regel drei verschiedene Foto Größen und-Auflösungen:</span><span class="sxs-lookup"><span data-stu-id="a3a38-107">Typically that means three different photo sizes and resolutions:</span></span>
  
- <span data-ttu-id="a3a38-108">64 x 64 Pixel: die für das „thumbnailPhoto“-Attribut in Active Directory verwendete Größe.</span><span class="sxs-lookup"><span data-stu-id="a3a38-108">64 pixels by 64 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="a3a38-109">Wenn Sie ein Foto auf Exchange Server hochladen, erstellt Exchange automatisch eine 64 Pixel-Version von 64 Pixeln dieses Fotos und aktualisiert das thumbnailPhoto-Attribut des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="a3a38-109">If you upload a photo to Exchange Server, Exchange will automatically create a 64 pixel by 64 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="a3a38-110">Beachten Sie jedoch, dass umgekehrt nicht wahr ist: Wenn Sie das thumbnailPhoto-Attribut in Active Directory manuell aktualisieren, wird das Foto im Exchange-Postfach des Benutzers nicht automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="a3a38-110">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange mailbox will not automatically be updated.</span></span>
    
- <span data-ttu-id="a3a38-111">96 Pixel von 96 Pixeln für die Verwendung in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App und Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="a3a38-111">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App, and Skype for Business.</span></span>
    
- <span data-ttu-id="a3a38-112">648 Pixel von 648 Pixeln für die Verwendung in Skype for Business und Skype for Business Web App Skype for Business Web App.</span><span class="sxs-lookup"><span data-stu-id="a3a38-112">648 pixels by 648 pixels for use in Skype for Business and Skype for Business Web App Skype for Business Web App.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a3a38-p103">Sofern Sie ausreichende Ressourcen besitzen, wird empfohlen, Fotos im Format 648 x 648 Pixel hochzuladen. Dies sorgt für eine maximale Auflösung und optimale Bildqualität in allen Office 2013-Anwendungen. Ein JPEG-Foto mit 648 x 648 Pixel und einer Tiefe von 24 Bit ergibt eine Datei mit einer Größe von rund 240 KB. Dies bedeutet, dass Sie für je vier Benutzerfotos rund 1 MB Speicherplatz benötigen.</span><span class="sxs-lookup"><span data-stu-id="a3a38-p103">If you have the resources, it is recommended that you upload 648 x 648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications. Each JPEG photo with a size of 648 x 648 and a depth of 24 bits results in a file size of approximately 240 kilobytes. That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span> 
  
<span data-ttu-id="a3a38-116">Fotos mit hoher Auflösung, auf die über Exchange-Webdienste zugegriffen wird, können von Benutzern hochgeladen werden, die Outlook 2013 Web App ausführen. Benutzer dürfen nur Ihr eigenes Foto aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a3a38-116">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="a3a38-117">Administratoren können das Foto allerdings mit der Exchange-Verwaltungsshell und einer Reihe von Windows PowerShell-Befehlen aktualisieren, die dem folgenden ähneln:</span><span class="sxs-lookup"><span data-stu-id="a3a38-117">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>
  
```
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="a3a38-118">Mit dem ersten Befehl im vorherigen Beispiel wird das `Get-Content` Cmdlet verwendet, um den Inhalt der Datei C:\Photos\Kenmyer.jpg zu lesen und diese Daten in einer Variablen mit dem Namen $Photo zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a3a38-118">The first command in the preceding example uses the `Get-Content` cmdlet to read the contents of the file C:\Photos\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="a3a38-119">Im zweiten Befehl wird das Exchange-Cmdlet `Set-UserPhoto` verwendet, um das Foto hochzuladen und dieses Foto an das Benutzerkonto von Ken Myers anzufügen.</span><span class="sxs-lookup"><span data-stu-id="a3a38-119">In the second command, the Exchange cmdlet `Set-UserPhoto` is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a3a38-120">In diesem Beispiel wird der Active Directory-Anzeigename von Ken Myer als Benutzerkontoidentität verwendet.</span><span class="sxs-lookup"><span data-stu-id="a3a38-120">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="a3a38-121">Sie können ein Benutzerkonto auch über andere IDs wie die SMTP-Adresse des Benutzers oder dessen Benutzerprinzipalnamen referenzieren.</span><span class="sxs-lookup"><span data-stu-id="a3a38-121">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="a3a38-122">Weitere Informationen finden Sie in [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) der Dokumentation für das Cmdlet "Satz-UserPhoto".</span><span class="sxs-lookup"><span data-stu-id="a3a38-122">See the documentation for the Set-UserPhoto cmdlet at [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) for more information</span></span>
  
<span data-ttu-id="a3a38-p107">Das Hochladen des Fotos entspricht keiner Zuweisung des Fotos zu Ken Myers Benutzerkonto. Durch das Hochladen wird einfach eine Vorschau dieses Fotos auf der Seite der Outlook Web App-Optionen angezeigt. Damit dieses Foto dem Benutzerkonto zugewiesen wird, muss der Benutzer auf der Seite mit den Optionen auf **Speichern** klicken oder der Administrator muss den dritten Befehl des Beispiels ausführen. Dieser dritte Befehl weist das Foto mithilfe des Parameters „Save“ dem Benutzerkonto von Ken Myer zu:</span><span class="sxs-lookup"><span data-stu-id="a3a38-p107">Uploading the photo does not equate to assigning that photo to Ken Myer's user account. Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page. To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example. That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>
  
```
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="a3a38-127">Um zu überprüfen, ob das neue Foto dem Benutzerkonto zugewiesen wurde, kann Ken Myers sich bei Skype for Business anmelden, **Optionen**auswählen und dann **mein Bild**auswählen.</span><span class="sxs-lookup"><span data-stu-id="a3a38-127">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Skype for Business, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="a3a38-128">Das neu hochgeladene Foto sollte dann als Kens persönliches Foto angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a3a38-128">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="a3a38-129">Alternativ können Administratoren die Fotos aller Benutzer prüfen, indem sie den Internet Explorer starten und zu einer URL der folgenden Art navigieren:</span><span class="sxs-lookup"><span data-stu-id="a3a38-129">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>
  
```
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648
```

<span data-ttu-id="a3a38-130">Wenn der Administrator das Foto über Internet Explorer anzeigen kann, der Benutzer aber sein Foto in Skype for Business nicht anzeigen kann, liegt möglicherweise ein Verbindungsproblem mit Exchange-Webdiensten oder mit dem AutoErmittlungsdienst von Exchange vor.</span><span class="sxs-lookup"><span data-stu-id="a3a38-130">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Skype for Business there may be a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>
  
<span data-ttu-id="a3a38-131">Beachten Sie auch, dass keine zusätzliche Konfiguration erforderlich ist, um dieses Foto in Skype for Business zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="a3a38-131">Note, too that no additional configuration is required in order to make this photo available in Skype for Business.</span></span> <span data-ttu-id="a3a38-132">Stattdessen ist das Foto sofort verfügbar, nachdem es hochgeladen wurde und das `Set-UserPhoto` Cmdlet ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="a3a38-132">Instead, the photo will be instantly available after it has been uploaded and the `Set-UserPhoto` cmdlet has been run.</span></span>
