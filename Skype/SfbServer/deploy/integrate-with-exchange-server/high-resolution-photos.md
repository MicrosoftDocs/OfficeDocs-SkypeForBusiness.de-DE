---
title: Konfigurieren Sie die Verwendung von hoch auflösenden Fotos in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: 'Zusammenfassung: Konfigurieren Sie die Verwendung von hoch auflösenden Fotos in Exchange Server 2016 oder Exchange Server 2013 und Skype für Business Server.'
ms.openlocfilehash: 1d631fb8ec8f17bb883f59936bb6e4adbeb02395
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894323"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a><span data-ttu-id="eb248-103">Konfigurieren Sie die Verwendung von hoch auflösenden Fotos in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="eb248-103">Configure the use of high-resolution photos in Skype for Business Server</span></span>
 
<span data-ttu-id="eb248-104">**Zusammenfassung:** Konfigurieren Sie die Verwendung von hoch auflösenden Fotos in Exchange Server 2016 oder Exchange Server 2013 und Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="eb248-104">**Summary:** Configure the use of high-resolution photos in Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>
  
<span data-ttu-id="eb248-105">In Skype für Business Server können Fotos in Exchange Server 2016 oder Exchange Server 2013 Postfach eines Benutzers, die bis zu 648 x 648 Pixel Foto Größen ermöglicht gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="eb248-105">In Skype for Business Server photos can be stored in a user's Exchange Server 2016 or Exchange Server 2013 mailbox, which allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="eb248-106">Exchange Server darüber hinaus können diese Fotos in anderen Produkten automatisch angepasst, je nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="eb248-106">In addition, Exchange Server can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="eb248-107">In der Regel bedeutet, dass drei verschiedenen Foto Größen und Lösungen:</span><span class="sxs-lookup"><span data-stu-id="eb248-107">Typically that means three different photo sizes and resolutions:</span></span>
  
- <span data-ttu-id="eb248-108">64 x 64 Pixel: die für das „thumbnailPhoto“-Attribut in Active Directory verwendete Größe.</span><span class="sxs-lookup"><span data-stu-id="eb248-108">64 pixels by 64 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="eb248-109">Wenn Sie ein Foto in Exchange Server hochladen, Exchange automatisch ein 64 Pixel von 64 Pixel-Version dieses Foto erstellen und aktualisieren ThumbnailPhoto-Attribut des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="eb248-109">If you upload a photo to Exchange Server, Exchange will automatically create a 64 pixel by 64 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="eb248-110">Beachten Sie jedoch, dass die Umkehrung nicht true ist: Wenn Sie das Attribut ThumbnailPhoto in Active Directory manuell aktualisieren das Foto im Exchange-Postfach des Benutzers wird nicht automatisch aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="eb248-110">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange mailbox will not automatically be updated.</span></span>
    
- <span data-ttu-id="eb248-111">96 x 96 Pixel, für die Verwendung in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype für Business Web App und Skype für Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="eb248-111">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App, and Skype for Business.</span></span>
    
- <span data-ttu-id="eb248-112">648 x 648 Pixel für verwenden in Skype für Unternehmen und Skype für Business Web App Skype für Web-Geschäfts-App.</span><span class="sxs-lookup"><span data-stu-id="eb248-112">648 pixels by 648 pixels for use in Skype for Business and Skype for Business Web App Skype for Business Web App.</span></span>
    
> [!NOTE]
> <span data-ttu-id="eb248-p103">Sofern Sie ausreichende Ressourcen besitzen, wird empfohlen, Fotos im Format 648 x 648 Pixel hochzuladen. Dies sorgt für eine maximale Auflösung und optimale Bildqualität in allen Office 2013-Anwendungen. Ein JPEG-Foto mit 648 x 648 Pixel und einer Tiefe von 24 Bit ergibt eine Datei mit einer Größe von rund 240 KB. Dies bedeutet, dass Sie für je vier Benutzerfotos rund 1 MB Speicherplatz benötigen.</span><span class="sxs-lookup"><span data-stu-id="eb248-p103">If you have the resources, it is recommended that you upload 648 x 648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications. Each JPEG photo with a size of 648 x 648 and a depth of 24 bits results in a file size of approximately 240 kilobytes. That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span> 
  
<span data-ttu-id="eb248-116">Fotos mit hoher Auflösung, die mithilfe der Exchange-Webdienste zugegriffen werden, können von Benutzern hochgeladen werden, die Outlook 2013 Web App ausführen; Benutzer dürfen nur eigene Foto zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="eb248-116">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="eb248-117">Administratoren können das Foto für jeden Benutzer jedoch mithilfe der Exchange-Verwaltungsshell und eine Reihe von Windows PowerShell-Befehle wie folgt aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="eb248-117">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>
  
```
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="eb248-118">Der erste Befehl im vorstehenden Beispiel verwendet die `Get-Content` -Cmdlet zum Lesen Sie den Inhalt der Datei C:\Photos\Kenmyer.jpg, und speichern diese Daten in einer Variablen mit dem Namen $photo.</span><span class="sxs-lookup"><span data-stu-id="eb248-118">The first command in the preceding example uses the `Get-Content` cmdlet to read the contents of the file C:\Photos\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="eb248-119">Im zweiten Befehl, mit dem Exchange-Cmdlet `Set-UserPhoto` wird verwendet, um das Foto hochladen, und fügen Sie dieses Foto Ken Myers Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="eb248-119">In the second command, the Exchange cmdlet `Set-UserPhoto` is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="eb248-120">In diesem Beispiel wird der Active Directory-Anzeigename von Ken Myer als Benutzerkontoidentität verwendet.</span><span class="sxs-lookup"><span data-stu-id="eb248-120">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="eb248-121">Sie können ein Benutzerkonto auch über andere IDs wie die SMTP-Adresse des Benutzers oder dessen Benutzerprinzipalnamen referenzieren.</span><span class="sxs-lookup"><span data-stu-id="eb248-121">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="eb248-122">Finden Sie in der Dokumentation für das Cmdlet Set-UserPhoto bei [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eb248-122">See the documentation for the Set-UserPhoto cmdlet at [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) for more information</span></span>
  
<span data-ttu-id="eb248-p107">Das Hochladen des Fotos entspricht keiner Zuweisung des Fotos zu Ken Myers Benutzerkonto. Durch das Hochladen wird einfach eine Vorschau dieses Fotos auf der Seite der Outlook Web App-Optionen angezeigt. Damit dieses Foto dem Benutzerkonto zugewiesen wird, muss der Benutzer auf der Seite mit den Optionen auf **Speichern** klicken oder der Administrator muss den dritten Befehl des Beispiels ausführen. Dieser dritte Befehl weist das Foto mithilfe des Parameters „Save“ dem Benutzerkonto von Ken Myer zu:</span><span class="sxs-lookup"><span data-stu-id="eb248-p107">Uploading the photo does not equate to assigning that photo to Ken Myer's user account. Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page. To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example. That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>
  
```
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="eb248-127">Um sicherzustellen, dass das Benutzerkonto ein neue Foto zugewiesen wurde, kann Ken Myer Skype für Unternehmen, wählen Sie **Optionen**, und wählen Sie **Mein Bild**anmelden.</span><span class="sxs-lookup"><span data-stu-id="eb248-127">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Skype for Business, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="eb248-128">Das neu hochgeladene Foto sollte dann als Kens persönliches Foto angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="eb248-128">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="eb248-129">Alternativ können Administratoren die Fotos aller Benutzer prüfen, indem sie den Internet Explorer starten und zu einer URL der folgenden Art navigieren:</span><span class="sxs-lookup"><span data-stu-id="eb248-129">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>
  
```
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&amp;size=HR648x648
```

<span data-ttu-id="eb248-130">Wenn der Administrator kann das Foto mit Internet Explorer anzeigen, aber der Benutzer nicht sein eigenes Foto, in Skype für Unternehmen anzeigen kann kann ein Verbindungsproblem mit Exchange-Webdienste oder mit der Exchange-AutoErmittlungsdienst vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="eb248-130">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Skype for Business there may be a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>
  
<span data-ttu-id="eb248-131">Beachten Sie außerdem, dass keine zusätzliche Konfiguration erforderlich ist, um dieses Foto in Skype für Unternehmen verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="eb248-131">Note, too that no additional configuration is required in order to make this photo available in Skype for Business.</span></span> <span data-ttu-id="eb248-132">Stattdessen das Foto werden sofort zur Verfügung stehen, nachdem er hochgeladen wurde und die `Set-UserPhoto` Cmdlet ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="eb248-132">Instead, the photo will be instantly available after it has been uploaded and the `Set-UserPhoto` cmdlet has been run.</span></span>
