---
title: So werden Benutzerfotos in Lync angezeigt
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 941c1ab56feea557dfc792ea0af6415dd2a56851
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839872"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-user-photos-are-displayed-in-lync"></a><span data-ttu-id="b0a9e-102">So werden Benutzerfotos in Lync angezeigt</span><span class="sxs-lookup"><span data-stu-id="b0a9e-102">How user photos are displayed in Lync</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0a9e-103">_**Letztes Änderungsdatum des Themas:** 2014-08-25_</span><span class="sxs-lookup"><span data-stu-id="b0a9e-103">_**Topic Last Modified:** 2014-08-25_</span></span>

<span data-ttu-id="b0a9e-104">**Zusammenfassung:** Benutzer Fotos, die in lync-Client angezeigt werden, können je nach verwendetem lync-Feature unterschiedlich sein, beispielsweise in einer Konferenz oder im Chat.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-104">**Summary:** User photos displayed in Lync client can be different depending on which Lync feature you are using, such as when in a conference or an IM chat.</span></span>

<span data-ttu-id="b0a9e-105">Lync 2010 hat die Möglichkeit eingeführt, ein Foto in Ihr lync-Profil einzubeziehen, das für andere lync-Benutzer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-105">Lync 2010 introduced the ability to include a photo with your Lync profile that is displayed to other Lync users.</span></span> <span data-ttu-id="b0a9e-106">Sie können auch auswählen, ob Fotos für Ihre Kontakte in lync-Client angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-106">You can also choose whether or not to display photos for your contacts in Lync client.</span></span> <span data-ttu-id="b0a9e-107">In lync 2013: Unterstützung für Fotos mit hoher Auflösung für Benutzer.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-107">In Lync 2013, support for high-resolution photos for users.</span></span> <span data-ttu-id="b0a9e-108">In diesem Thema wird beschrieben, wie Benutzer Fotos vom lync-Client abgerufen und angezeigt werden, wo die Bilder gespeichert werden, welche Einschränkungen für die einzelnen Bildquellen gelten und wie Benutzer Fotos von verschiedenen lync-Diensten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-108">This topic describes how Lync client gets and displays user photos, where the images are stored, the limitations for each image source, and how user photos are used by different Lync services.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="b0a9e-109">Planungsüberlegungen</span><span class="sxs-lookup"><span data-stu-id="b0a9e-109">Planning considerations</span></span>

<span data-ttu-id="b0a9e-110">Bei der Planung der Implementierung der Unterstützung für Benutzer Fotos sollten Sie Folgendes berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="b0a9e-110">You should consider the following when planning to implement support for user photos.</span></span>

  - <span data-ttu-id="b0a9e-111">Für die Unterstützung von Benutzer Fotos mit hoher Auflösung muss das Postfach des Benutzers auf Exchange 2013 und das lync-Benutzerkonto im lync 2013-Pool gespeichert sein.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-111">High-definition user photo support requires that the user’s mailbox be located on Exchange 2013 and the Lync user account to be in Lync 2013 pool.</span></span>

  - <span data-ttu-id="b0a9e-112">Benutzer Fotos mit hoher Auflösung werden nur in einer Umgebung unterstützt, in der sowohl lync Server 2013 als auch Exchange 2013 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-112">High-definition user photos are supported only in an environment where both Lync Server 2013 and Exchange 2013 are used.</span></span>

  - <span data-ttu-id="b0a9e-113">Benutzer mit Postfächern in Exchange 2010 verwenden immer das **thumbnailPhoto** -Attribut aus AD DS als Quelle für das Benutzer Foto.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-113">Users with Mailboxes on Exchange 2010 will always use the **thumbnailPhoto** attribute from AD DS as the source for their user photo.</span></span>

  - <span data-ttu-id="b0a9e-114">Ein Benutzer Foto, das als **thumbnailPhoto** -Attribut in AD DS gespeichert ist, wird für externe/verbundene Kontakte nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-114">A user photo stored as the **thumbnailPhoto** attribute from AD DS will not be displayed to external / federated contacts.</span></span>

  - <span data-ttu-id="b0a9e-115">Wenn die Fotos für Benutzer Kontakte in AD DS gespeichert sind, ist die verwendete Bilddatei auf 96 × 96 Pixel und auf eine Dateigröße von 100 KB limitiert.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-115">If the photos for user contacts are stored in AD DS, the image file used is limited to 96×96 pixels and no more than 100 KB file size.</span></span>

  - <span data-ttu-id="b0a9e-116">Wenn die Konnektivität zwischen lync Server und Exchange Server verloren geht, werden die **thumbnailPhoto** der Benutzer mit niedriger Auflösung von AD DS und nur internen Benutzern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-116">If connectivity between Lync Server and Exchange Server is lost, the user’s low resolution **thumbnailPhoto** from AD DS will be displayed, and to internal users only.</span></span>

  - <span data-ttu-id="b0a9e-117">Benutzer Fotos mit hoher Auflösung werden in lync 2013-Besprechungen angezeigt, wenn für einen aktiven Lautsprecher kein Video aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-117">High-resolution user photos are displayed in Lync 2013 meetings when an active speaker does not have video enabled.</span></span> <span data-ttu-id="b0a9e-118">Wenn Sie den Mauszeiger über ein Miniaturbild im Katalog bewegen, wird auch das Foto mit hoher Auflösung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-118">Also, moving the mouse over thumbnail photo in the gallery will display the high-resolution photo.</span></span>

</div>

<div>

## <a name="user-photos-in-lync-2010"></a><span data-ttu-id="b0a9e-119">Benutzer Fotos in lync 2010</span><span class="sxs-lookup"><span data-stu-id="b0a9e-119">User Photos in Lync 2010</span></span>

<span data-ttu-id="b0a9e-120">Im lync 2010-Client können Sie aus zwei Optionen auswählen, um ein Foto für Ihr Profil, das **standardmäßige Unternehmensbild** und das **Bild von einer Webadresse**anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-120">In the Lync 2010 client, you can choose from two options to display a photo for your profile, **Default corporate picture** and **Show picture from a web address**.</span></span>

<div>

## <a name="default-corporate-picture"></a><span data-ttu-id="b0a9e-121">Standardbild für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="b0a9e-121">Default corporate picture</span></span>

<span data-ttu-id="b0a9e-122">Wenn Sie die Standardoption für das **Unternehmensbild** auswählen, ruft lync das für Sie angezeigte Foto in den Active Directory-Domänendiensten ab.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-122">When you choose the **Default corporate picture** option, Lync gets the photo displayed for you from Active Directory Domain Services.</span></span> <span data-ttu-id="b0a9e-123">Das verwendete Bild ist das Bild, das als Wert für das **thumbnailPhoto** -Attribut in den Active Directory-Domänendiensten definiert ist.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-123">The image used is the image defined as the value for the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span> <span data-ttu-id="b0a9e-124">Hierbei handelt es sich um die gleiche Datei, die von Exchange zum Anzeigen von Bildern in Outlook verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-124">This is the same file that is used by Exchange to display images in Outlook.</span></span>

<span data-ttu-id="b0a9e-125">Überlegungen zur Verwendung von Bildern aus Active Directory-Domänendiensten umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b0a9e-125">Considerations for using images from Active Directory Domain Services include the following:</span></span>

  - <span data-ttu-id="b0a9e-126">Es werden nur Bilder mit einer Größe von bis zu 96 Pixeln von 96 Pixeln unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-126">Only images with dimensions up to 96 pixels by 96 pixels are supported.</span></span> <span data-ttu-id="b0a9e-127">Die Dateigröße für das Bild ist auf 100 KB limitiert.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-127">The file size for the image is limited to 100 KB.</span></span>

  - <span data-ttu-id="b0a9e-128">Standardmäßig können Benutzer das für das **thumbnailPhoto** -Attribut verwendete Bild ändern, allerdings nicht direkt über den lync-Client.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-128">By default, users are able to change the image used for the **thumbnailPhoto** attribute, though not directly through Lync client.</span></span> <span data-ttu-id="b0a9e-129">Sie können dies über die Active Directory-Domänendienste deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-129">You can disable this through Active Directory Domain Services.</span></span>

  - <span data-ttu-id="b0a9e-130">Bilder, die in den Active Directory-Domänendiensten gespeichert sind, werden nicht für Kontakte außerhalb Ihrer Organisation angezeigt, auch wenn es sich um Verbund Kontakte handelt.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-130">Images stored in Active Directory Domain Services are not displayed to contacts external to your organization, even if they are federated contacts.</span></span>

  - <span data-ttu-id="b0a9e-131">In großen Organisationen kann das Speichern und Abrufen der Bilder für eine große Anzahl von Benutzern Auswirkungen auf die Größe und Leistung der Datenbank für die Active Directory-Domänendienste haben.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-131">In large organizations, storing and retrieving the images for large numbers of users may impact the Active Directory Domain Services database size and performance.</span></span>

  - <span data-ttu-id="b0a9e-132">Die geringen Bildabmessungen und die Dateigröße bedeuten, dass nur Bilder mit niedriger Auflösung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-132">The limited image dimensions and file size mean that only low resolution images can be used.</span></span>

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a><span data-ttu-id="b0a9e-133">Verwalten von Benutzer Fotos in Active Directory-Domänendiensten durch Benutzer</span><span class="sxs-lookup"><span data-stu-id="b0a9e-133">How users manage their user photos in Active Directory Domain Services</span></span>

<span data-ttu-id="b0a9e-134">Der Benutzer kann das Bild, das in seinem Active Directory-Domänendienst Profil verwendet wird, nicht direkt über den lync 2010-Client ändern.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-134">User cannot change the image used in their Active Directory Domain Services profile directly through Lync 2010 client.</span></span> <span data-ttu-id="b0a9e-135">Sie können eine der folgenden Optionen verwenden, falls verfügbar:</span><span class="sxs-lookup"><span data-stu-id="b0a9e-135">They can use one of the following options to do so, if available:</span></span>

  - <span data-ttu-id="b0a9e-136">**SharePoint Server**   -Benutzer können ein Foto auf "Meine Website" auf einem SharePoint-Server hochladen und dann die [Profilsynchronisierung in SharePoint konfigurieren](http://go.microsoft.com/fwlink/p/?linkid=507466) , um das Foto mit dem **thumbnailPhoto** -Attribut in der Active Directory-Domäne zu synchronisieren. Services.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-136">**SharePoint Server**   Users can upload a photo to ‘My Site’ on a SharePoint Server and then [configure profile synchronization in SharePoint](http://go.microsoft.com/fwlink/p/?linkid=507466) to synchronize the photo to the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="b0a9e-137">**Foto, das auf öffentlich zugänglichen URL**   -Benutzern gespeichert ist, kann das Benutzer Foto konfigurieren, das eine öffentlich zugängliche URL für das Bild angibt, das Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-137">**Photo stored on publicly accessible URL**   Users can configure their user photo specifying a publicly accessible URL for the image that they want to use.</span></span> <span data-ttu-id="b0a9e-138">Das Bild muss ohne Kennwort öffentlich zugänglich sein.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-138">The image must be publicly accessible without a password.</span></span> <span data-ttu-id="b0a9e-139">Das Bild, das bei der angegebenen Webadresse gespeichert ist, wird über die Kategorie Visitenkarte in den Anwesenheitsinformationen an andere Benutzer übertragen.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-139">The image stored at the specified web address is transferred to other users through the contact card category in the presence information.</span></span> <span data-ttu-id="b0a9e-140">Wenn der lync-Client ein Benutzer Foto anzeigen muss, wird das Bild von der angegebenen Webadresse abgerufen.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-140">When Lync client needs to display a user photo, it retrieves the image from the specified web address.</span></span>

  - <span data-ttu-id="b0a9e-141">**Exchange 2010-Cmdlets für Windows PowerShell**   -Administratoren können das Cmdlet " [Import-RecipientDataProperty](http://go.microsoft.com/fwlink/p/?linkid=507468) " in der Exchange 2010-Verwaltungsshell ausführen, um das **thumbnailPhoto** -Attribut zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-141">**Exchange 2010 cmdlets for Windows PowerShell**   Administrators can run the [Import-RecipientDataProperty](http://go.microsoft.com/fwlink/p/?linkid=507468) cmdlet in the Exchange 2010 Management Shell in to manage the **thumbnailPhoto** attribute.</span></span> <span data-ttu-id="b0a9e-142">Wenn Bilder mit Exchange 2010-Cmdlets importiert werden, ist die Dateigröße auf 10 KB limitiert.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-142">When images are imported with Exchange 2010 cmdlets, the file size is limited to 10 KB.</span></span>

  - <span data-ttu-id="b0a9e-143">**Tools von Drittanbietern**   Benutzer können nur Ihr eigenes Foto für das **thumbnailPhoto** -Attribut hochladen.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-143">**Third Party tools**   Users can upload only their own photo to for the **thumbnailPhoto** attribute.</span></span>

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a><span data-ttu-id="b0a9e-144">Anzeigen eines Bilds aus einer Internetadresse</span><span class="sxs-lookup"><span data-stu-id="b0a9e-144">Show a picture from a web address</span></span>

<span data-ttu-id="b0a9e-145">Wenn Sie die Option **Bild aus einer Webadresse anzeigen** auswählen, ruft lync das Bild an der von Ihnen eingegebenen Adresse ab und zeigt es für Ihr Benutzer Foto in lync an.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-145">When you choose the **Show a picture from a web address** option, Lync gets the image at the address you enter and displays it for your user photo in Lync.</span></span>

<span data-ttu-id="b0a9e-146">Überlegungen zur Verwendung von Bildern aus einer Webadresse sind die folgenden:</span><span class="sxs-lookup"><span data-stu-id="b0a9e-146">Considerations for using images from a web address include the following:</span></span>

  - <span data-ttu-id="b0a9e-147">Die Dateigrößenbeschränkungen werden durch das **MaxPhotoSizeKB** -Attribut in der Clientrichtlinie bestimmt, das mit dem Cmdlet [New-CsClientPolicy](http://go.microsoft.com/fwlink/p/?linkid=507463) definiert ist.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-147">File size limits are determined by the **MaxPhotoSizeKB** attribute in the client policy, defined with the [New-CsClientPolicy](http://go.microsoft.com/fwlink/p/?linkid=507463) cmdlet.</span></span> <span data-ttu-id="b0a9e-148">Die Standardgrößenbeschränkung beträgt 30 KB.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-148">The default size limit is 30 KB.</span></span> <span data-ttu-id="b0a9e-149">Der Höchstwert ist 100 KB.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-149">The maximum value is 100 KB.</span></span> <span data-ttu-id="b0a9e-150">Es gibt keine Einschränkung für die Auflösung des Bilds, aber wenn Sie versuchen, eine Bilddatei zu verwenden, die die Größenbeschränkung überschreitet, wird Sie nicht auf lync-Clients heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-150">There is no restriction on the resolution of the image, but if you try to use an image file that exceeds the size limit it will not be downloaded to Lync clients.</span></span> <span data-ttu-id="b0a9e-151">Sie können den Wert auf 0 setzen, um zu verhindern, dass alle Benutzer Fotos in lync verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-151">You can set the value to 0 to disable all user photos from being used in Lync.</span></span>

  - <span data-ttu-id="b0a9e-152">Benutzer Fotos von einer Webadresse können von externen Föderationskontakten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-152">User photos from a web address can be seen by external federated contacts.</span></span>

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a><span data-ttu-id="b0a9e-153">Verwalten des Fotos eines Benutzers mit Client Richtlinien-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="b0a9e-153">Managing user’s photo with Client Policy cmdlets</span></span>

<span data-ttu-id="b0a9e-154">In lync Server 2010 werden Clientrichtlinien Einstellungen mit den CsClientPolicy-Cmdlets konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-154">In Lync Server 2010, client policy settings are configured with the CsClientPolicy cmdlets.</span></span> <span data-ttu-id="b0a9e-155">Die konfigurierten Richtlinieneinstellungen werden über die in-Band-Bereitstellung an Clients gesendet.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-155">The configured policy settings are sent to clients through in-band provisioning.</span></span> <span data-ttu-id="b0a9e-156">Die beiden Parameter der CsClientPolicy-Cmdlets, die die Benutzer Fotoerfahrung bestimmen, sind **DisplayPhoto** und **MaxPhotoSizeKB**.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-156">The two parameters of the CsClientPolicy cmdlets that determine the user photo experience are **DisplayPhoto** and **MaxPhotoSizeKB**.</span></span> <span data-ttu-id="b0a9e-157">Der entsprechende in-Band-Bereitstellungsparameter für **DisplayPhoto** und **MaxPhotoSizeKB** hat den \*\*\*\* Namen "fotousage".</span><span class="sxs-lookup"><span data-stu-id="b0a9e-157">The corresponding in-band provisioning parameter for **DisplayPhoto** and **MaxPhotoSizeKB** is named **PhotoUsage**.</span></span> <span data-ttu-id="b0a9e-158">Werte für den \*\*\*\* Parameter "fotousage" werden über die **endpointConfiguration** \*\*\*\* provisiongroup an Clients gesendet.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-158">Values for the **PhotoUsage** parameter are send to clients through the **endpointConfiguration** **provisionGroup**.</span></span> <span data-ttu-id="b0a9e-159">Weitere Informationen finden Sie unter [Übersicht über Client Richtlinien und-Einstellungen](http://go.microsoft.com/fwlink/?linkid=507470) .</span><span class="sxs-lookup"><span data-stu-id="b0a9e-159">See [Overview of Client Policies and Settings](http://go.microsoft.com/fwlink/?linkid=507470) for more information.</span></span>

<span data-ttu-id="b0a9e-160">Der **DisplayPhoto** -Parameterwert bestimmt die Quelle des Foto Bilds des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-160">The **DisplayPhoto** parameter value determines the source of the user's photo image.</span></span> <span data-ttu-id="b0a9e-161">Die unterstützten Werte sind in der folgenden Tabelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-161">The supported values are included in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0a9e-162">DisplayPhoto-Parameterwert</span><span class="sxs-lookup"><span data-stu-id="b0a9e-162">DisplayPhoto parameter value</span></span></th>
<th><span data-ttu-id="b0a9e-163">Bildquelle</span><span class="sxs-lookup"><span data-stu-id="b0a9e-163">Image source</span></span></th>
<th><span data-ttu-id="b0a9e-164">Lync 2010-Clienteinstellungen</span><span class="sxs-lookup"><span data-stu-id="b0a9e-164">Lync 2010 client settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0a9e-165">Nophoto</span><span class="sxs-lookup"><span data-stu-id="b0a9e-165">NoPhoto</span></span></p></td>
<td><p><span data-ttu-id="b0a9e-166">Keine</span><span class="sxs-lookup"><span data-stu-id="b0a9e-166">none</span></span></p></td>
<td><p><span data-ttu-id="b0a9e-167"><strong>Mein Bild nicht anzeigen</strong></span><span class="sxs-lookup"><span data-stu-id="b0a9e-167"><strong>Do not show my picture</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0a9e-168">PhotoFromADOnly</span><span class="sxs-lookup"><span data-stu-id="b0a9e-168">PhotoFromADOnly</span></span></p></td>
<td><p><span data-ttu-id="b0a9e-169">Active Directory</span><span class="sxs-lookup"><span data-stu-id="b0a9e-169">Active Directory</span></span></p></td>
<td><p><span data-ttu-id="b0a9e-170"><strong>Standardbild für Unternehmen</strong></span><span class="sxs-lookup"><span data-stu-id="b0a9e-170"><strong>Default corporate picture</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0a9e-171">Allphotos</span><span class="sxs-lookup"><span data-stu-id="b0a9e-171">AllPhotos</span></span></p></td>
<td><p><span data-ttu-id="b0a9e-172">Internetadresse</span><span class="sxs-lookup"><span data-stu-id="b0a9e-172">Web address</span></span></p></td>
<td><p><span data-ttu-id="b0a9e-173"><strong>Anzeigen eines Bilds aus einer Internetadresse</strong></span><span class="sxs-lookup"><span data-stu-id="b0a9e-173"><strong>Show a picture from a web address</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a><span data-ttu-id="b0a9e-174">So erhält lync 2010-Client Fotos</span><span class="sxs-lookup"><span data-stu-id="b0a9e-174">How Lync 2010 client gets photos</span></span>

<span data-ttu-id="b0a9e-175">In lync 2010 werden Benutzer Fotos vom Adressbuchdienst auf dem Server verwaltet.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-175">In Lync 2010, user photos are managed on the server by the Address Book Service.</span></span> <span data-ttu-id="b0a9e-176">Der lync-Client ruft Benutzer Fotos ab, indem er zuerst den Adressbuch-Webabfrage Dienst (ABWQ) auf dem Server abfragt, der über den Webdienst für die Verteilerlistenerweiterung verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-176">Lync client gets user photos by first querying the Address Book Web Query (ABWQ) service on the server, which is exposed through the Distribution List Expansion web service.</span></span> <span data-ttu-id="b0a9e-177">Der Client empfängt die Bilddatei und kopiert Sie dann in den Cache des Benutzers, um zu vermeiden, dass das Bild jedes mal heruntergeladen wird, wenn es angezeigt werden muss.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-177">The client receives the image file and then copies it to the user's cache to avoid downloading the image each time it needs to be displayed.</span></span> <span data-ttu-id="b0a9e-178">Die von der Abfrage zurückgegebenen Attributwerte werden auch im zwischengespeicherten Adressbuchdienst Eintrag für den Benutzer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-178">The attribute values returned from the query are also stored in the cached Address Book Service entry for the user.</span></span> <span data-ttu-id="b0a9e-179">Der Adressbuchdienst löscht alle zwischengespeicherten Bilder alle 24 Stunden, was bedeutet, dass es bis zu 24 Stunden dauern kann, bis neue Benutzer Bilder im Cache auf dem Server aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-179">The Address Book Service deletes all cached images every 24 hours, which means that it can take up to 24 hours for new user images to be updated in the cache on the server.</span></span> <span data-ttu-id="b0a9e-180">Sie können eine Aktualisierung des Caches erzwingen, indem Sie das Cmdlet [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-180">You can force an update to the cache by using the [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) cmdlet.</span></span>

<span data-ttu-id="b0a9e-181">Benutzer Fotos, die im Anwesenheitsstatus enthalten sind, weisen auch einen zugehörigen Hashwert auf, mit dem lync-Client ermittelt, ob ein neueres Bild verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-181">User photos included in Presence status also have an associated hash value that Lync client uses to determine whether there is a newer image available.</span></span> <span data-ttu-id="b0a9e-182">Der Client wird automatisch über Änderungen an der im Anwesenheitsstatus verwendeten Bilddatei benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-182">The client is automatically notified of changes to the image file used in Presence status.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="b0a9e-183">Da Fotos nicht in der GalContacts. DB-Datenbank gespeichert sind, hängt das Herunterladen von Benutzer Fotos nicht von der <STRONG>AddressBookAvailability</STRONG> -Einstellung in der Clientrichtlinie ab (<A href="http://go.microsoft.com/fwlink/p/?linkid=507508">Satz-CsClientPolicy</A>).</span><span class="sxs-lookup"><span data-stu-id="b0a9e-183">Because photos are not stored in the GalContacts.db database, downloading user photos is not dependent on the <STRONG>AddressBookAvailability</STRONG> setting in the client policy (<A href="http://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>).</span></span>



</div>

<span data-ttu-id="b0a9e-184">Die Abfrage des ABWQ-Diensts umfasst die folgenden Attribute:</span><span class="sxs-lookup"><span data-stu-id="b0a9e-184">The query to the ABWQ service includes the following attributes:</span></span>

  - <span data-ttu-id="b0a9e-185">**Photo Hash**   den Hashwert der binären Fotodaten und wird verwendet, um zu bestimmen, ob sich das aktuelle Foto geändert hat.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-185">**PhotoHash**   The hash value of the binary photo data, and is used to determine whether the current photo has changed.</span></span>

  - <span data-ttu-id="b0a9e-186">**PhotoRelPath**   der relative Pfad zu der auf dem Server gespeicherten Bilddatei.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-186">**PhotoRelPath**   The relative path to the image file stored on the server.</span></span>

  - <span data-ttu-id="b0a9e-187">**Fotografieren**   Sie die Größe der Bilddatei in Bytes.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-187">**PhotoSize**   The size of the image file, in bytes.</span></span>

  - <span data-ttu-id="b0a9e-188">**Timestamp**   das Datum und die Uhrzeit, zu dem die Bilddatei zuletzt vom Server heruntergeladen und in den Clientcache kopiert wurde.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-188">**TimeStamp**   The date and time at which the image file was last downloaded from the server and copied to the client cache.</span></span>

<span data-ttu-id="b0a9e-189">Als nächstes vergleicht der lync 2010-Client nach dem Abrufen der Bilddatei die von der Abfrage zurückgegebenen Attributwerte mit den vom Client empfangenen Attributwerten aus der in-Band-Bereitstellung, um festzustellen, ob Sie sich unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-189">Next, after retrieving the image file, Lync 2010 client compares the attribute values returned from the query against the attribute values received by the client from in-band provisioning to see if they are different.</span></span> <span data-ttu-id="b0a9e-190">Wenn sich die Werte unterscheiden, ruft der Client die Bilddatei des angemeldeten Benutzers mit einer HTTP GET-Anforderung ab.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-190">If the values are different, the client retrieves the image file of the signed-in user with an HTTP GET request.</span></span>

<span data-ttu-id="b0a9e-191">Darüber hinaus überprüft der Client den Server alle 24 Stunden ab dem Zeitpunkt, zu dem die zwischengespeicherte Version der Bilddatei erstellt wurde, um den Wert des Foto **Hash** Attributs auf dem Server mit dem Wert auf dem Client zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-191">Additionally, the client checks with the server every 24 hours from the time at which the cached version of the image file was created to compare the value of the **PhotoHash** attribute on the server with the value on the client.</span></span> <span data-ttu-id="b0a9e-192">Wenn sich die Werte unterscheiden, weiß der Client, dass sich die Bilddatei geändert hat.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-192">If the values are different, the client knows that the image file has changed.</span></span> <span data-ttu-id="b0a9e-193">Um die aktualisierte Image-Datei abzurufen, fragt der Client erneut den ABWQ-Dienst ab, um die Bilddatei im Clientcache mit der Bilddatei auf dem Server zu aktualisieren, wodurch auch der **Zeitstempel** für die Datei im Clientcache zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-193">To obtain the updated image file, the client again queries the ABWQ service to update the image file in the client cache with the image file on the server, which also resets the **TimeStamp** on the file in the client cache.</span></span>

<span data-ttu-id="b0a9e-194">Im folgenden wird eine Beispielantwort auf eine Abfrage des ABWQ-Diensts veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="b0a9e-194">The following is an example response to a query to the ABWQ service:</span></span>

    <Attribute>
              <Name>PhotoRelPath</Name>
              <Value>efa6096aed2746cb9ab2037f7dbdde9d.f2eeeb5946db54a7aa607ecd3ae09d
              95.photo</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
              <Name>PhotoHash</Name>
              <Value>f2eeeb5946db54a7aa607ecd3ae09d95</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
         <Name>PhotoSize</Name>
         <Value>4620</Value>
         <Valuesxmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
    i:nil="true" />
    </Attribute>

</div>

</div>

<div>

## <a name="user-photos-in-lync-2013"></a><span data-ttu-id="b0a9e-195">Benutzer Fotos in lync 2013</span><span class="sxs-lookup"><span data-stu-id="b0a9e-195">User photos in Lync 2013</span></span>

<span data-ttu-id="b0a9e-196">Lync 2013 hat Unterstützung für Bilder mit hoher Auflösung für Benutzer Fotos eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-196">Lync 2013 introduced support for high-resolution images for user photos.</span></span> <span data-ttu-id="b0a9e-197">Lync 2013 umfasst auch die Unterstützung für das Speichern von Benutzer Fotos im Postfach des Benutzers in Exchange 2013, wodurch die in lync 2010 vorhandenen Bildauflösungen und Größenbeschränkungen entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-197">Lync 2013 also includes support for storing user photos in the user's mailbox on Exchange 2013, which removes the image resolution and size limitations present in Lync 2010.</span></span> <span data-ttu-id="b0a9e-198">Benutzer Fotos in lync 2013 können bis zu 648 Pixel von 648 Pixeln mit einer Dateigröße von bis zu 20 MB sein.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-198">User photos in Lync 2013 can be up to 648 pixels by 648 pixels with a file size of up to 20 MB.</span></span> <span data-ttu-id="b0a9e-199">Fotos mit hoher Auflösung in lync 2013 müssen sich im Postfach des Benutzers in Exchange 2013 befinden und nur mit dem lync 2013-Client unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-199">High-resolution photos in Lync 2013 must be located in the user's mailbox on Exchange 2013, and are supported only with Lync 2013 client.</span></span> <span data-ttu-id="b0a9e-200">Diese Integration in Exchange nutzt das neue Autorisierungsframework, das in den 2013-Versionen von lync, Exchange und SharePoint namens OAuth enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-200">This integration with Exchange takes advantage of the new authorization framework included in the 2013 versions of Lync, Exchange, and SharePoint called Oauth.</span></span>

<span data-ttu-id="b0a9e-201">Wenn Exchange 2013 in Ihrer Bereitstellung nicht verwendet wird, ist die Unterstützung für Benutzer Fotos identisch mit lync 2010.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-201">If Exchange 2013 is not used in your deployment, support for user photos is the same as with Lync 2010.</span></span> <span data-ttu-id="b0a9e-202">Die Benutzeroptionen zur Auswahl des zu verwendenden Fotos unterscheiden sich jedoch in lync 2013-Client.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-202">However, the user options to choose the photo to use are different in Lync 2013 client.</span></span> <span data-ttu-id="b0a9e-203">In lync 2013-Client können Benutzer entweder " **mein Bild verbergen** " oder " **mein Bild anzeigen**" auswählen.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-203">In Lync 2013 client, users can select either **Hide my picture** or **Show my picture**.</span></span> <span data-ttu-id="b0a9e-204">Die Option " **Bild von einer Website anzeigen** " ist standardmäßig nicht verfügbar, kann aber durch Zuweisen einer Clientrichtlinie aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-204">The option **Show a picture from a website** is not available by default, but can be enabled by assigning a client policy.</span></span>

<div>

## <a name="hide-my-picture"></a><span data-ttu-id="b0a9e-205">Mein Bild ausblenden</span><span class="sxs-lookup"><span data-stu-id="b0a9e-205">Hide my picture</span></span>

<span data-ttu-id="b0a9e-206">Einstellungen für Benutzer Fotos finden Sie im Dialogfeld " **Optionen** " in lync 2013.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-206">Settings for user photos are on the **Options** dialog in Lync 2013.</span></span> <span data-ttu-id="b0a9e-207">Wenn Sie **mein Bild ausblenden**auswählen, wird im lync-Client kein Benutzer Foto angezeigt, aber Ihr Foto wird weiterhin auf Ihrer Visitenkarte und außerhalb von lync angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-207">When you choose **Hide my picture**, no user photo is displayed for you in Lync client, but your photo is still displayed on your contact card and outside of Lync.</span></span>

</div>

<div>

## <a name="show-my-picture"></a><span data-ttu-id="b0a9e-208">Mein Bild anzeigen</span><span class="sxs-lookup"><span data-stu-id="b0a9e-208">Show my picture</span></span>

<span data-ttu-id="b0a9e-209">Wenn Sie die Option " **mein Bild anzeigen** " auswählen, wird das Benutzer Foto in einem lync-Client und anderen Benutzern in lync-Unterhaltungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-209">When you choose the **Show my picture** option, your user photo is displayed in your Lync client and to other users in Lync conversations.</span></span> <span data-ttu-id="b0a9e-210">Das verwendete Bild wird in AD DS gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-210">The image used is the one stored in AD DS.</span></span>

</div>

<div>

## <a name="show-a-picture-from-a-website"></a><span data-ttu-id="b0a9e-211">Anzeigen eines Bilds von einer Website</span><span class="sxs-lookup"><span data-stu-id="b0a9e-211">Show a picture from a website</span></span>

<span data-ttu-id="b0a9e-212">Die Option **Bild von einer Website anzeigen** steht in lync 2013 nach dem Festlegen einer Clientrichtlinie zum Aktivieren zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-212">The **Show picture from a website** option becomes available in Lync 2013 after a client policy is set to enable it.</span></span> <span data-ttu-id="b0a9e-213">Die Client Version muss neuer als 15.0.4535.1002 sein, die mit den kumulierten [Updates für lync installiert wird: November 2013](http://go.microsoft.com/fwlink/p/?linkid=509908).</span><span class="sxs-lookup"><span data-stu-id="b0a9e-213">The client version must be newer than 15.0.4535.1002, which is installed with the [Lync Cumulative Updates: November 2013](http://go.microsoft.com/fwlink/p/?linkid=509908).</span></span> <span data-ttu-id="b0a9e-214">Benutzer müssen sich möglicherweise abmelden und dann wieder zurück, um die Änderungen im Client anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-214">Users may need to log out and then back in again to see the changes in the client.</span></span>

<span data-ttu-id="b0a9e-215">Sie können festlegen, dass die Clientrichtlinie für die **Anzeige von Bildern aus einer Website** Einstellung aktiviert ist, indem Sie die Richtlinie für die CsClientPolicy in der lync Server [-](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) Verwaltungsshell ausführen.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-215">You can set the client policy to enable to **Show picture from a website** setting by running the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) policy in the Lync Server Management Shell.</span></span> <span data-ttu-id="b0a9e-216">Die folgenden Beispiel-Cmdlets veranschaulichen, wie Sie die Richtlinie für alle Benutzer in Ihrer Bereitstellung global festlegen:</span><span class="sxs-lookup"><span data-stu-id="b0a9e-216">The following example cmdlets demonstrate how to set the policy globally for all users in your deployment:</span></span>

   ```
    $pe=New-CsClientPolicyEntry -Name EnablePresencePhotoOptions -Value True
   ```

   ```
    $po=Get-CsClientPolicy -Identity Global
   ```

   ```
    $po.PolicyEntry.Add($pe)
   ```

   ```
    Set-CsClientPolicy -Instance $po
   ```


<span data-ttu-id="b0a9e-217">Wenn ein Bild in das Postfach des Benutzers hochgeladen wird, erstellt Exchange automatisch eine Version der niedrigeren Auflösung des Bilds, die in Clientanwendungen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-217">When an image is uploaded to the user’s mailbox, Exchange automatically creates a lower resolution version of the image which can be used in client applications.</span></span> <span data-ttu-id="b0a9e-218">Das Benutzer Foto wird in AD DS ebenfalls aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-218">The user photo is also updated in AD DS.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="b0a9e-219">Wenn eine Bilddatei in AD DS aktualisiert wird, wird ein Bild von 48 x 48 Pixel erstellt und für die thumbnailPhoto in AD DS verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-219">When an image file is updated in AD DS, a 48 x 48 pixel image is created and used for the thumbnailPhoto in AD DS.</span></span> <span data-ttu-id="b0a9e-220">Jedes vorhandene Bild wird ersetzt.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-220">Any existing image is replaced.</span></span> <span data-ttu-id="b0a9e-221">Wenn Sie AD DS also ein 96 x 96-Bild hinzugefügt haben, wird es mit dem neuen 48 x 48-Bild überschrieben.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-221">So if you added a 96 x 96 image to AD DS, it will be overwritten with the new 48 x 48 image.</span></span> <span data-ttu-id="b0a9e-222">Dies ist nur wichtig, wenn Sie Benutzer in Ihrer Umgebung mit lync 2010-Clients verwenden, da diese Clients Benutzer Fotos von AD DS erhalten.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-222">This is only important is you have users in your environment using Lync 2010 clients, as those clients will obtain user photos from AD DS.</span></span> <span data-ttu-id="b0a9e-223">Sie können 96 x 96 Pixelbilder importieren, um diejenigen zu ersetzen, die von AD DS erstellt wurden, wenn Sie über lync 2010-Clients in Ihrer Organisation verfügen.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-223">You can import 96 x 96 pixel images to replace the ones created by AD DS if you have Lync 2010 clients in your organization.</span></span>



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a><span data-ttu-id="b0a9e-224">Unterstützung für Benutzer Fotos in lync 2013</span><span class="sxs-lookup"><span data-stu-id="b0a9e-224">User photo support in Lync 2013</span></span>

<span data-ttu-id="b0a9e-225">In lync 2013 werden für Benutzer Fotos drei Bildauflösungen unterstützt, wie in der folgenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-225">In Lync 2013, three image resolutions are supported for user photos as described in the following table.</span></span> <span data-ttu-id="b0a9e-226">Das verwendete Bild wird von der Clientrichtlinien Einstellung bestimmt, die lync-Benutzern zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-226">The image that is used is determined by the client policy setting assigned to Lync users.</span></span> <span data-ttu-id="b0a9e-227">Weitere Informationen finden Sie unter "Verwalten des Fotos des Benutzers mit Client Richtlinien-Cmdlets" in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-227">See “Managing user’s photo with Client Policy cmdlets” in this topic for more information.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0a9e-228">Bildauflösung (Pixel)</span><span class="sxs-lookup"><span data-stu-id="b0a9e-228">Image resolution (pixels)</span></span></th>
<th><span data-ttu-id="b0a9e-229">Anwendung</span><span class="sxs-lookup"><span data-stu-id="b0a9e-229">Application</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0a9e-230">48 x 48</span><span class="sxs-lookup"><span data-stu-id="b0a9e-230">48 x 48</span></span></p></td>
<td><p><span data-ttu-id="b0a9e-231">Wird verwendet, wenn kein Bild höherer Auflösung ausgewählt ist</span><span class="sxs-lookup"><span data-stu-id="b0a9e-231">Used if no higher resolution image is selected</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0a9e-232">96 x 96</span><span class="sxs-lookup"><span data-stu-id="b0a9e-232">96 x 96</span></span></p></td>
<td><p><span data-ttu-id="b0a9e-233">Verwendung in Outlook Web App und Outlook 2013</span><span class="sxs-lookup"><span data-stu-id="b0a9e-233">Used in Outlook Web App and Outlook 2013</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0a9e-234">648 x 648</span><span class="sxs-lookup"><span data-stu-id="b0a9e-234">648 x 648</span></span></p></td>
<td><p><span data-ttu-id="b0a9e-235">Wird in lync 2013-Desktop Client und lync 2013 Web App verwendet</span><span class="sxs-lookup"><span data-stu-id="b0a9e-235">Used in Lync 2013 desktop client and Lync 2013 Web App</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b0a9e-236">Jeder Benutzer mit einem in Exchange 2013 aktivierten Postfach kann ein anderes Bild, einschließlich Fotos mit hoher Auflösung, über die Outlook Web Access-oder lync 2013-Clientoptionen hochladen.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-236">Any user with a mailbox enabled in Exchange 2013 can upload a different image, including high-resolution photos, through Outlook Web Access or Lync 2013 client options.</span></span> <span data-ttu-id="b0a9e-237">Die empfohlenen Einstellungen für verwendete Bilder sind:</span><span class="sxs-lookup"><span data-stu-id="b0a9e-237">The recommended settings for images used include:</span></span>

  - <span data-ttu-id="b0a9e-238">**Bildauflösung**   648 x 648 Pixel</span><span class="sxs-lookup"><span data-stu-id="b0a9e-238">**Image Resolution**   648 by 648 pixels</span></span>

  - <span data-ttu-id="b0a9e-239">**Farbtiefe**   24-Bit</span><span class="sxs-lookup"><span data-stu-id="b0a9e-239">**Color Depth**   24-bit</span></span>

  - <span data-ttu-id="b0a9e-240">**Bilddateigröße**   bis zu 20 MB</span><span class="sxs-lookup"><span data-stu-id="b0a9e-240">**Image file size**   up to 20 MB</span></span>

  - <span data-ttu-id="b0a9e-241">**Dateiformat**   JPEG</span><span class="sxs-lookup"><span data-stu-id="b0a9e-241">**File format**   JPEG</span></span>

<span data-ttu-id="b0a9e-242">Ein typisches 24-Bit-JPEG-Bild mit einer Größe von 648 Pixeln von 648 Pixeln hat eine Dateigröße von etwa 240 KB, sodass für alle 4 Benutzer Fotos 1 MB Speicherplatz benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="b0a9e-242">A typical 24-bit JPEG image that is 648 pixels by 648 pixels has a file size of about 240 KB, so 1 MB of storage space is needed for every 4 user photos.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

