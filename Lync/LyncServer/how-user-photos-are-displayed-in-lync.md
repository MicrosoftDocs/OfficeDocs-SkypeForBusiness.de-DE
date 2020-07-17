---
title: Anzeigen von Benutzer Fotos in lync
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88d6f6f6f5578994831fd15329988d963a295832
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="how-user-photos-are-displayed-in-lync"></a><span data-ttu-id="eace2-102">Anzeigen von Benutzer Fotos in lync</span><span class="sxs-lookup"><span data-stu-id="eace2-102">How user photos are displayed in Lync</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eace2-103">_**Letztes Änderungsstand des Themas:** 2014-08-25_</span><span class="sxs-lookup"><span data-stu-id="eace2-103">_**Topic Last Modified:** 2014-08-25_</span></span>

<span data-ttu-id="eace2-104">**Zusammenfassung:** Benutzer Fotos, die in lync-Client angezeigt werden, können je nach verwendetem lync-Feature unterschiedlich sein, beispielsweise in einer Konferenz oder im Chat.</span><span class="sxs-lookup"><span data-stu-id="eace2-104">**Summary:** User photos displayed in Lync client can be different depending on which Lync feature you are using, such as when in a conference or an IM chat.</span></span>

<span data-ttu-id="eace2-105">Lync 2010 wurde die Möglichkeit eingeführt, ein Foto mit Ihrem lync-Profil einzuschließen, das anderen lync-Benutzern angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="eace2-105">Lync 2010 introduced the ability to include a photo with your Lync profile that is displayed to other Lync users.</span></span> <span data-ttu-id="eace2-106">Sie können auch auswählen, ob Fotos für Ihre Kontakte in lync-Client angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="eace2-106">You can also choose whether or not to display photos for your contacts in Lync client.</span></span> <span data-ttu-id="eace2-107">In lync 2013 Unterstützung für hochauflösende Fotos für Benutzer.</span><span class="sxs-lookup"><span data-stu-id="eace2-107">In Lync 2013, support for high-resolution photos for users.</span></span> <span data-ttu-id="eace2-108">In diesem Thema wird beschrieben, wie Benutzer Fotos von lync-Client abgerufen und angezeigt werden, wo die Bilder gespeichert werden, welche Einschränkungen für welche Bildquellen gelten und wie Benutzer Fotos von verschiedenen lync-Diensten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="eace2-108">This topic describes how Lync client gets and displays user photos, where the images are stored, the limitations for each image source, and how user photos are used by different Lync services.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="eace2-109">Überlegungen zur Planung</span><span class="sxs-lookup"><span data-stu-id="eace2-109">Planning considerations</span></span>

<span data-ttu-id="eace2-110">Bei der Planung der Implementierung von Unterstützung für Benutzer Fotos sollten Sie Folgendes berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="eace2-110">You should consider the following when planning to implement support for user photos.</span></span>

  - <span data-ttu-id="eace2-111">Für die Unterstützung von hochauflösenden Benutzern ist es erforderlich, dass sich das Postfach des Benutzers auf Exchange 2013 und das lync-Benutzerkonto in lync 2013 Pool befinden.</span><span class="sxs-lookup"><span data-stu-id="eace2-111">High-definition user photo support requires that the user’s mailbox be located on Exchange 2013 and the Lync user account to be in Lync 2013 pool.</span></span>

  - <span data-ttu-id="eace2-112">Hochauflösende Benutzer Fotos werden nur in einer Umgebung unterstützt, in der sowohl lync Server 2013 als auch Exchange 2013 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="eace2-112">High-definition user photos are supported only in an environment where both Lync Server 2013 and Exchange 2013 are used.</span></span>

  - <span data-ttu-id="eace2-113">Benutzer mit Postfächern in Exchange 2010 verwenden immer das **thumbnailPhoto** -Attribut aus AD DS als Quelle für das Benutzer Foto.</span><span class="sxs-lookup"><span data-stu-id="eace2-113">Users with Mailboxes on Exchange 2010 will always use the **thumbnailPhoto** attribute from AD DS as the source for their user photo.</span></span>

  - <span data-ttu-id="eace2-114">Ein Benutzer Foto, das als **thumbnailPhoto** -Attribut aus AD DS gespeichert wird, wird nicht für externe/Verbund Kontakte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eace2-114">A user photo stored as the **thumbnailPhoto** attribute from AD DS will not be displayed to external / federated contacts.</span></span>

  - <span data-ttu-id="eace2-115">Wenn die Fotos für Benutzer Kontakte in AD DS gespeichert werden, ist die verwendete Bilddatei auf 96 × 96 Pixel und eine Dateigröße von mehr als 100 KB begrenzt.</span><span class="sxs-lookup"><span data-stu-id="eace2-115">If the photos for user contacts are stored in AD DS, the image file used is limited to 96×96 pixels and no more than 100 KB file size.</span></span>

  - <span data-ttu-id="eace2-116">Wenn die Konnektivität zwischen lync Server und Exchange Server verloren geht, wird die **thumbnailPhoto** der Benutzer mit niedriger Auflösung von AD DS und nur für interne Benutzer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eace2-116">If connectivity between Lync Server and Exchange Server is lost, the user’s low resolution **thumbnailPhoto** from AD DS will be displayed, and to internal users only.</span></span>

  - <span data-ttu-id="eace2-117">Hochauflösende Benutzer Fotos werden in lync 2013 Besprechungen angezeigt, wenn für einen aktiven Lautsprecher kein Video aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="eace2-117">High-resolution user photos are displayed in Lync 2013 meetings when an active speaker does not have video enabled.</span></span> <span data-ttu-id="eace2-118">Wenn Sie die Maus über ein Vorschaubild in der Galerie bewegen, wird auch das Foto mit hoher Auflösung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eace2-118">Also, moving the mouse over thumbnail photo in the gallery will display the high-resolution photo.</span></span>

</div>

<div>

## <a name="user-photos-in-lync-2010"></a><span data-ttu-id="eace2-119">Benutzer Fotos in lync 2010</span><span class="sxs-lookup"><span data-stu-id="eace2-119">User Photos in Lync 2010</span></span>

<span data-ttu-id="eace2-120">Im lync 2010-Client können Sie zwischen zwei Optionen auswählen, um ein Foto für Ihr Profil, ein **standardmäßiges Unternehmensbild** und **ein Bild von einer Webadresse**anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="eace2-120">In the Lync 2010 client, you can choose from two options to display a photo for your profile, **Default corporate picture** and **Show picture from a web address**.</span></span>

<div>

## <a name="default-corporate-picture"></a><span data-ttu-id="eace2-121">Standardbild für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="eace2-121">Default corporate picture</span></span>

<span data-ttu-id="eace2-122">Wenn Sie die Standardoption " **Unternehmensbild** " auswählen, erhält lync das für Sie angezeigte Foto aus Active Directory-Domänendienste.</span><span class="sxs-lookup"><span data-stu-id="eace2-122">When you choose the **Default corporate picture** option, Lync gets the photo displayed for you from Active Directory Domain Services.</span></span> <span data-ttu-id="eace2-123">Das verwendete Bild ist das Bild, das als Wert für das **thumbnailPhoto** -Attribut in Active Directory-Domänendienste definiert ist.</span><span class="sxs-lookup"><span data-stu-id="eace2-123">The image used is the image defined as the value for the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span> <span data-ttu-id="eace2-124">Dies ist die gleiche Datei, die von Exchange zum Anzeigen von Bildern in Outlook verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="eace2-124">This is the same file that is used by Exchange to display images in Outlook.</span></span>

<span data-ttu-id="eace2-125">Überlegungen zur Verwendung von Bildern aus Active Directory-Domänendienste umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="eace2-125">Considerations for using images from Active Directory Domain Services include the following:</span></span>

  - <span data-ttu-id="eace2-126">Es werden nur Bilder mit einer Größe von bis zu 96 Pixeln von 96 Pixel unterstützt.</span><span class="sxs-lookup"><span data-stu-id="eace2-126">Only images with dimensions up to 96 pixels by 96 pixels are supported.</span></span> <span data-ttu-id="eace2-127">Die Dateigröße für das Bild ist auf 100 KB limitiert.</span><span class="sxs-lookup"><span data-stu-id="eace2-127">The file size for the image is limited to 100 KB.</span></span>

  - <span data-ttu-id="eace2-128">Standardmäßig können Benutzer das für das **thumbnailPhoto** -Attribut verwendete Bild ändern, jedoch nicht direkt über den lync-Client.</span><span class="sxs-lookup"><span data-stu-id="eace2-128">By default, users are able to change the image used for the **thumbnailPhoto** attribute, though not directly through Lync client.</span></span> <span data-ttu-id="eace2-129">Sie können dies über Active Directory-Domänendienste deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="eace2-129">You can disable this through Active Directory Domain Services.</span></span>

  - <span data-ttu-id="eace2-130">In Active Directory-Domänendienste gespeicherte Bilder werden nicht für Kontakte außerhalb Ihrer Organisation angezeigt, auch wenn es sich um Verbund Kontakte handelt.</span><span class="sxs-lookup"><span data-stu-id="eace2-130">Images stored in Active Directory Domain Services are not displayed to contacts external to your organization, even if they are federated contacts.</span></span>

  - <span data-ttu-id="eace2-131">In großen Organisationen kann das Speichern und Abrufen der Bilder für eine große Anzahl von Benutzern Auswirkungen auf die Größe und Leistung der Active Directory-Domänendienste Datenbank haben.</span><span class="sxs-lookup"><span data-stu-id="eace2-131">In large organizations, storing and retrieving the images for large numbers of users may impact the Active Directory Domain Services database size and performance.</span></span>

  - <span data-ttu-id="eace2-132">Die begrenzten Bildabmessungen und die Dateigröße bedeuten, dass nur Bilder mit niedriger Auflösung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="eace2-132">The limited image dimensions and file size mean that only low resolution images can be used.</span></span>

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a><span data-ttu-id="eace2-133">So verwalten Benutzer Ihre Benutzer Fotos in Active Directory-Domänendienste</span><span class="sxs-lookup"><span data-stu-id="eace2-133">How users manage their user photos in Active Directory Domain Services</span></span>

<span data-ttu-id="eace2-134">Der Benutzer kann das im Active Directory-Domänendienste Profil verwendete Bild nicht direkt über lync 2010-Client ändern.</span><span class="sxs-lookup"><span data-stu-id="eace2-134">User cannot change the image used in their Active Directory Domain Services profile directly through Lync 2010 client.</span></span> <span data-ttu-id="eace2-135">Sie können eine der folgenden Optionen verwenden, falls verfügbar:</span><span class="sxs-lookup"><span data-stu-id="eace2-135">They can use one of the following options to do so, if available:</span></span>

  - <span data-ttu-id="eace2-136">**SharePoint Server**     Benutzer können ein Foto auf einem SharePoint Server in "Meine Website" hochladen und dann die [Profilsynchronisierung in SharePoint konfigurieren](https://go.microsoft.com/fwlink/p/?linkid=507466) , um das Foto mit dem **thumbnailPhoto** -Attribut in Active Directory-Domänendienste zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="eace2-136">**SharePoint Server**   Users can upload a photo to ‘My Site’ on a SharePoint Server and then [configure profile synchronization in SharePoint](https://go.microsoft.com/fwlink/p/?linkid=507466) to synchronize the photo to the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="eace2-137">**Auf öffentlich zugänglicher URL**     gespeichertes Foto Benutzer können Ihr Benutzer Foto so konfigurieren, dass eine öffentlich zugängliche URL für das Bild angegeben wird, das Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="eace2-137">**Photo stored on publicly accessible URL**   Users can configure their user photo specifying a publicly accessible URL for the image that they want to use.</span></span> <span data-ttu-id="eace2-138">Das Bild muss ohne Kennwort öffentlich zugänglich sein.</span><span class="sxs-lookup"><span data-stu-id="eace2-138">The image must be publicly accessible without a password.</span></span> <span data-ttu-id="eace2-139">Das Bild, das in der angegebenen Webadresse gespeichert ist, wird über die Visitenkarten Kategorie in den Anwesenheitsinformationen an andere Benutzer übertragen.</span><span class="sxs-lookup"><span data-stu-id="eace2-139">The image stored at the specified web address is transferred to other users through the contact card category in the presence information.</span></span> <span data-ttu-id="eace2-140">Wenn der lync-Client ein Benutzer Foto anzeigen muss, ruft es das Bild aus der angegebenen Webadresse ab.</span><span class="sxs-lookup"><span data-stu-id="eace2-140">When Lync client needs to display a user photo, it retrieves the image from the specified web address.</span></span>

  - <span data-ttu-id="eace2-141">**Exchange 2010-Cmdlets für Windows PowerShell**     Administratoren können das Cmdlet [Import-RecipientDataProperty](https://go.microsoft.com/fwlink/p/?linkid=507468) in der Exchange 2010 Management Shell in ausführen, um das **thumbnailPhoto** -Attribut zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="eace2-141">**Exchange 2010 cmdlets for Windows PowerShell**   Administrators can run the [Import-RecipientDataProperty](https://go.microsoft.com/fwlink/p/?linkid=507468) cmdlet in the Exchange 2010 Management Shell in to manage the **thumbnailPhoto** attribute.</span></span> <span data-ttu-id="eace2-142">Wenn Bilder mit Exchange 2010-Cmdlets importiert werden, ist die Dateigröße auf 10 KB limitiert.</span><span class="sxs-lookup"><span data-stu-id="eace2-142">When images are imported with Exchange 2010 cmdlets, the file size is limited to 10 KB.</span></span>

  - <span data-ttu-id="eace2-143">Tools von Dritt **Anbietern**     Benutzer können nur Ihr eigenes Foto für das **thumbnailPhoto** -Attribut hochladen.</span><span class="sxs-lookup"><span data-stu-id="eace2-143">**Third Party tools**   Users can upload only their own photo to for the **thumbnailPhoto** attribute.</span></span>

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a><span data-ttu-id="eace2-144">Anzeigen eines Bilds aus einer Webadresse</span><span class="sxs-lookup"><span data-stu-id="eace2-144">Show a picture from a web address</span></span>

<span data-ttu-id="eace2-145">Wenn Sie die Option **Bild aus einer Webadresse anzeigen** auswählen, ruft lync das Bild an der von Ihnen eingegebenen Adresse ab und zeigt es für Ihr Benutzer Foto in lync an.</span><span class="sxs-lookup"><span data-stu-id="eace2-145">When you choose the **Show a picture from a web address** option, Lync gets the image at the address you enter and displays it for your user photo in Lync.</span></span>

<span data-ttu-id="eace2-146">Überlegungen zur Verwendung von Bildern aus einer Webadresse umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="eace2-146">Considerations for using images from a web address include the following:</span></span>

  - <span data-ttu-id="eace2-147">Die Dateigrößenbeschränkungen werden durch das **MaxPhotoSizeKB** -Attribut in der Clientrichtlinie bestimmt, das mit dem Cmdlet [New-CsClientPolicy](https://go.microsoft.com/fwlink/p/?linkid=507463) definiert ist.</span><span class="sxs-lookup"><span data-stu-id="eace2-147">File size limits are determined by the **MaxPhotoSizeKB** attribute in the client policy, defined with the [New-CsClientPolicy](https://go.microsoft.com/fwlink/p/?linkid=507463) cmdlet.</span></span> <span data-ttu-id="eace2-148">Die Standardgrößenbeschränkung beträgt 30 KB.</span><span class="sxs-lookup"><span data-stu-id="eace2-148">The default size limit is 30 KB.</span></span> <span data-ttu-id="eace2-149">Der Höchstwert ist 100 KB.</span><span class="sxs-lookup"><span data-stu-id="eace2-149">The maximum value is 100 KB.</span></span> <span data-ttu-id="eace2-150">Es gibt keine Einschränkung für die Auflösung des Bilds, aber wenn Sie versuchen, eine Image-Datei zu verwenden, die die Größenbeschränkung überschreitet, wird Sie nicht auf lync-Clients heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="eace2-150">There is no restriction on the resolution of the image, but if you try to use an image file that exceeds the size limit it will not be downloaded to Lync clients.</span></span> <span data-ttu-id="eace2-151">Sie können den Wert auf 0 festlegen, um zu verhindern, dass alle Benutzer Fotos in lync verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="eace2-151">You can set the value to 0 to disable all user photos from being used in Lync.</span></span>

  - <span data-ttu-id="eace2-152">Benutzer Fotos aus einer Webadresse können von externen verbundkontakten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="eace2-152">User photos from a web address can be seen by external federated contacts.</span></span>

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a><span data-ttu-id="eace2-153">Verwalten des Fotos eines Benutzers mit Client Richtlinien-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="eace2-153">Managing user’s photo with Client Policy cmdlets</span></span>

<span data-ttu-id="eace2-154">In lync Server 2010 werden die Clientrichtlinien Einstellungen mit den CsClientPolicy-Cmdlets konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="eace2-154">In Lync Server 2010, client policy settings are configured with the CsClientPolicy cmdlets.</span></span> <span data-ttu-id="eace2-155">Die konfigurierten Richtlinieneinstellungen werden über die in-Band-Konfiguration an Clients gesendet.</span><span class="sxs-lookup"><span data-stu-id="eace2-155">The configured policy settings are sent to clients through in-band provisioning.</span></span> <span data-ttu-id="eace2-156">Die beiden Parameter der CsClientPolicy-Cmdlets, die die Benutzer Fotodarstellung bestimmen, sind **DisplayPhoto** und **MaxPhotoSizeKB**.</span><span class="sxs-lookup"><span data-stu-id="eace2-156">The two parameters of the CsClientPolicy cmdlets that determine the user photo experience are **DisplayPhoto** and **MaxPhotoSizeKB**.</span></span> <span data-ttu-id="eace2-157">Der entsprechende Parameter für die in-Band-Provision für **DisplayPhoto** und **MaxPhotoSizeKB** hat den Namen " **fotousage**".</span><span class="sxs-lookup"><span data-stu-id="eace2-157">The corresponding in-band provisioning parameter for **DisplayPhoto** and **MaxPhotoSizeKB** is named **PhotoUsage**.</span></span> <span data-ttu-id="eace2-158">Werte für den Parameter " **fotousage** " werden über die **endpointConfiguration** **provisionarygroup**an Clients gesendet.</span><span class="sxs-lookup"><span data-stu-id="eace2-158">Values for the **PhotoUsage** parameter are send to clients through the **endpointConfiguration** **provisionGroup**.</span></span> <span data-ttu-id="eace2-159">Weitere Informationen finden Sie unter [Übersicht über Client Richtlinien und-Einstellungen](https://go.microsoft.com/fwlink/?linkid=507470) .</span><span class="sxs-lookup"><span data-stu-id="eace2-159">See [Overview of Client Policies and Settings](https://go.microsoft.com/fwlink/?linkid=507470) for more information.</span></span>

<span data-ttu-id="eace2-160">Der Wert des **DisplayPhoto** -Parameters bestimmt die Quelle des Foto Bilds des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="eace2-160">The **DisplayPhoto** parameter value determines the source of the user's photo image.</span></span> <span data-ttu-id="eace2-161">Die unterstützten Werte sind in der folgenden Tabelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="eace2-161">The supported values are included in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eace2-162">DisplayPhoto-Parameterwert</span><span class="sxs-lookup"><span data-stu-id="eace2-162">DisplayPhoto parameter value</span></span></th>
<th><span data-ttu-id="eace2-163">Bildquelle</span><span class="sxs-lookup"><span data-stu-id="eace2-163">Image source</span></span></th>
<th><span data-ttu-id="eace2-164">Lync 2010 Clienteinstellungen</span><span class="sxs-lookup"><span data-stu-id="eace2-164">Lync 2010 client settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eace2-165">NoPhoto</span><span class="sxs-lookup"><span data-stu-id="eace2-165">NoPhoto</span></span></p></td>
<td><p><span data-ttu-id="eace2-166">keine</span><span class="sxs-lookup"><span data-stu-id="eace2-166">none</span></span></p></td>
<td><p><span data-ttu-id="eace2-167"><strong>Mein Bild nicht anzeigen</strong></span><span class="sxs-lookup"><span data-stu-id="eace2-167"><strong>Do not show my picture</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eace2-168">PhotoFromADOnly</span><span class="sxs-lookup"><span data-stu-id="eace2-168">PhotoFromADOnly</span></span></p></td>
<td><p><span data-ttu-id="eace2-169">Active Directory</span><span class="sxs-lookup"><span data-stu-id="eace2-169">Active Directory</span></span></p></td>
<td><p><span data-ttu-id="eace2-170"><strong>Standardbild für Unternehmen</strong></span><span class="sxs-lookup"><span data-stu-id="eace2-170"><strong>Default corporate picture</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eace2-171">AllPhotos</span><span class="sxs-lookup"><span data-stu-id="eace2-171">AllPhotos</span></span></p></td>
<td><p><span data-ttu-id="eace2-172">Webadresse</span><span class="sxs-lookup"><span data-stu-id="eace2-172">Web address</span></span></p></td>
<td><p><span data-ttu-id="eace2-173"><strong>Anzeigen eines Bilds aus einer Webadresse</strong></span><span class="sxs-lookup"><span data-stu-id="eace2-173"><strong>Show a picture from a web address</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a><span data-ttu-id="eace2-174">So erhält lync 2010 Client Fotos</span><span class="sxs-lookup"><span data-stu-id="eace2-174">How Lync 2010 client gets photos</span></span>

<span data-ttu-id="eace2-175">In lync 2010 werden Benutzer Fotos vom Adressbuchdienst auf dem Server verwaltet.</span><span class="sxs-lookup"><span data-stu-id="eace2-175">In Lync 2010, user photos are managed on the server by the Address Book Service.</span></span> <span data-ttu-id="eace2-176">Der lync-Client ruft Benutzer Fotos ab, indem er zuerst den Adressbuch-Webabfrage Dienst (ABWQ) auf dem Server abfragt, der über den Webdienst für die Verteilerlistenerweiterung verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="eace2-176">Lync client gets user photos by first querying the Address Book Web Query (ABWQ) service on the server, which is exposed through the Distribution List Expansion web service.</span></span> <span data-ttu-id="eace2-177">Der Client empfängt die Bilddatei und kopiert Sie dann in den Cache des Benutzers, um zu vermeiden, dass das Bild jedes mal heruntergeladen wird, wenn es angezeigt werden muss.</span><span class="sxs-lookup"><span data-stu-id="eace2-177">The client receives the image file and then copies it to the user's cache to avoid downloading the image each time it needs to be displayed.</span></span> <span data-ttu-id="eace2-178">Die von der Abfrage zurückgegebenen Attributwerte werden auch im zwischengespeicherten Adressbuchdienst Eintrag für den Benutzer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="eace2-178">The attribute values returned from the query are also stored in the cached Address Book Service entry for the user.</span></span> <span data-ttu-id="eace2-179">Der Adressbuchdienst löscht alle zwischengespeicherten Bilder alle 24 Stunden, was bedeutet, dass es bis zu 24 Stunden dauern kann, bis neue Benutzer Bilder im Cache auf dem Server aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="eace2-179">The Address Book Service deletes all cached images every 24 hours, which means that it can take up to 24 hours for new user images to be updated in the cache on the server.</span></span> <span data-ttu-id="eace2-180">Sie können eine Aktualisierung des Caches mit dem Cmdlet [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) erzwingen.</span><span class="sxs-lookup"><span data-stu-id="eace2-180">You can force an update to the cache by using the [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) cmdlet.</span></span>

<span data-ttu-id="eace2-181">Im Anwesenheitsstatus enthaltene Benutzer Fotos weisen ebenfalls einen Hashwert auf, mit dem der lync-Client ermittelt, ob ein neueres Bild verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="eace2-181">User photos included in Presence status also have an associated hash value that Lync client uses to determine whether there is a newer image available.</span></span> <span data-ttu-id="eace2-182">Der Client wird automatisch über Änderungen an der Bild Datei benachrichtigt, die im Anwesenheitsstatus verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="eace2-182">The client is automatically notified of changes to the image file used in Presence status.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="eace2-183">Da Fotos nicht in der GalContacts. DB-Datenbank gespeichert sind, hängt das Herunterladen von Benutzer Fotos nicht von der <STRONG>AddressBookAvailability</STRONG> -Einstellung in der Clientrichtlinie ("<A href="https://go.microsoft.com/fwlink/p/?linkid=507508">CsClientPolicy</A>") ab.</span><span class="sxs-lookup"><span data-stu-id="eace2-183">Because photos are not stored in the GalContacts.db database, downloading user photos is not dependent on the <STRONG>AddressBookAvailability</STRONG> setting in the client policy (<A href="https://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>).</span></span>



</div>

<span data-ttu-id="eace2-184">Die Abfrage an den ABWQ-Dienst umfasst die folgenden Attribute:</span><span class="sxs-lookup"><span data-stu-id="eace2-184">The query to the ABWQ service includes the following attributes:</span></span>

  - <span data-ttu-id="eace2-185">**Fotohash**     Der Hashwert der binären Foto Daten und wird verwendet, um zu bestimmen, ob das aktuelle Foto geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="eace2-185">**PhotoHash**   The hash value of the binary photo data, and is used to determine whether the current photo has changed.</span></span>

  - <span data-ttu-id="eace2-186">**PhotoRelPath**     Der relative Pfad zu der auf dem Server gespeicherten Abbilddatei.</span><span class="sxs-lookup"><span data-stu-id="eace2-186">**PhotoRelPath**   The relative path to the image file stored on the server.</span></span>

  - <span data-ttu-id="eace2-187">**Photos**     Die Größe der Bilddatei in Byte.</span><span class="sxs-lookup"><span data-stu-id="eace2-187">**PhotoSize**   The size of the image file, in bytes.</span></span>

  - <span data-ttu-id="eace2-188">**Zeitstempel**     Das Datum und die Uhrzeit, zu der die Abbilddatei zuletzt vom Server heruntergeladen und in den Clientcache kopiert wurde.</span><span class="sxs-lookup"><span data-stu-id="eace2-188">**TimeStamp**   The date and time at which the image file was last downloaded from the server and copied to the client cache.</span></span>

<span data-ttu-id="eace2-189">Als nächstes vergleicht lync 2010-Client die von der Abfrage zurückgegebenen Attributwerte mit den vom Client von der in-Band-Bereitstellung empfangenen Attributwerten, um zu sehen, ob Sie unterschiedlich sind, nachdem die Abbilddatei abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="eace2-189">Next, after retrieving the image file, Lync 2010 client compares the attribute values returned from the query against the attribute values received by the client from in-band provisioning to see if they are different.</span></span> <span data-ttu-id="eace2-190">Wenn die Werte unterschiedlich sind, ruft der Client die Bilddatei des angemeldeten Benutzers mit einer HTTP GET-Anforderung ab.</span><span class="sxs-lookup"><span data-stu-id="eace2-190">If the values are different, the client retrieves the image file of the signed-in user with an HTTP GET request.</span></span>

<span data-ttu-id="eace2-191">Darüber hinaus prüft der Client alle 24 Stunden ab dem Zeitpunkt, zu dem die zwischengespeicherte Version der Bilddatei erstellt wurde, den Server, um den Wert des Foto **Hash** Attributs auf dem Server mit dem Wert auf dem Client zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="eace2-191">Additionally, the client checks with the server every 24 hours from the time at which the cached version of the image file was created to compare the value of the **PhotoHash** attribute on the server with the value on the client.</span></span> <span data-ttu-id="eace2-192">Wenn die Werte unterschiedlich sind, weiß der Client, dass die Bilddatei geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="eace2-192">If the values are different, the client knows that the image file has changed.</span></span> <span data-ttu-id="eace2-193">Um die aktualisierte Bilddatei zu erhalten, fragt der Client den ABWQ-Dienst erneut ab, um die Bilddatei im Clientcache mit der Abbilddatei auf dem Server zu aktualisieren, wodurch auch der **Zeitstempel** für die Datei im Clientcache zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="eace2-193">To obtain the updated image file, the client again queries the ABWQ service to update the image file in the client cache with the image file on the server, which also resets the **TimeStamp** on the file in the client cache.</span></span>

<span data-ttu-id="eace2-194">Im folgenden finden Sie eine Beispielantwort auf eine Abfrage an den ABWQ-Dienst:</span><span class="sxs-lookup"><span data-stu-id="eace2-194">The following is an example response to a query to the ABWQ service:</span></span>
```xml
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
```

</div>

</div>

<div>

## <a name="user-photos-in-lync-2013"></a><span data-ttu-id="eace2-195">Benutzer Fotos in lync 2013</span><span class="sxs-lookup"><span data-stu-id="eace2-195">User photos in Lync 2013</span></span>

<span data-ttu-id="eace2-196">Lync 2013 wurde die Unterstützung für hochauflösende Bilder für Benutzer Fotos eingeführt.</span><span class="sxs-lookup"><span data-stu-id="eace2-196">Lync 2013 introduced support for high-resolution images for user photos.</span></span> <span data-ttu-id="eace2-197">Lync 2013 enthält auch Unterstützung für das Speichern von Benutzer Fotos im Postfach des Benutzers auf Exchange 2013, wodurch die in lync 2010 vorhandenen Bildauflösungen und Größenbeschränkungen entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="eace2-197">Lync 2013 also includes support for storing user photos in the user's mailbox on Exchange 2013, which removes the image resolution and size limitations present in Lync 2010.</span></span> <span data-ttu-id="eace2-198">Benutzer Fotos in lync 2013 können bis zu 648 Pixel von 648 Pixel mit einer Dateigröße von bis zu 20 MB sein.</span><span class="sxs-lookup"><span data-stu-id="eace2-198">User photos in Lync 2013 can be up to 648 pixels by 648 pixels with a file size of up to 20 MB.</span></span> <span data-ttu-id="eace2-199">Hochauflösende Fotos in lync 2013 müssen sich im Postfach des Benutzers auf Exchange 2013 befinden und nur mit lync 2013-Client unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="eace2-199">High-resolution photos in Lync 2013 must be located in the user's mailbox on Exchange 2013, and are supported only with Lync 2013 client.</span></span> <span data-ttu-id="eace2-200">Diese Integration in Exchange nutzt das neue Autorisierungsframework, das in den 2013-Versionen von lync, Exchange und SharePoint mit dem Namen OAuth enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="eace2-200">This integration with Exchange takes advantage of the new authorization framework included in the 2013 versions of Lync, Exchange, and SharePoint called Oauth.</span></span>

<span data-ttu-id="eace2-201">Wenn Exchange 2013 nicht in Ihrer Bereitstellung verwendet wird, ist die Unterstützung für Benutzer Fotos identisch mit lync 2010.</span><span class="sxs-lookup"><span data-stu-id="eace2-201">If Exchange 2013 is not used in your deployment, support for user photos is the same as with Lync 2010.</span></span> <span data-ttu-id="eace2-202">Die Benutzeroptionen zum Auswählen des zu verwendenden Fotos unterscheiden sich jedoch in lync 2013-Client.</span><span class="sxs-lookup"><span data-stu-id="eace2-202">However, the user options to choose the photo to use are different in Lync 2013 client.</span></span> <span data-ttu-id="eace2-203">In lync 2013-Client können Benutzer entweder " **mein Bild verbergen** " oder " **eigenes Bild anzeigen**" auswählen.</span><span class="sxs-lookup"><span data-stu-id="eace2-203">In Lync 2013 client, users can select either **Hide my picture** or **Show my picture**.</span></span> <span data-ttu-id="eace2-204">Die Option **Bild von einer Website anzeigen** ist standardmäßig nicht verfügbar, kann jedoch durch Zuweisen einer Clientrichtlinie aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="eace2-204">The option **Show a picture from a website** is not available by default, but can be enabled by assigning a client policy.</span></span>

<div>

## <a name="hide-my-picture"></a><span data-ttu-id="eace2-205">Mein Bild ausblenden</span><span class="sxs-lookup"><span data-stu-id="eace2-205">Hide my picture</span></span>

<span data-ttu-id="eace2-206">Einstellungen für Benutzer Fotos befinden sich im Dialogfeld **Optionen** in lync 2013.</span><span class="sxs-lookup"><span data-stu-id="eace2-206">Settings for user photos are on the **Options** dialog in Lync 2013.</span></span> <span data-ttu-id="eace2-207">Wenn Sie " **mein Bild ausblenden**" auswählen, wird im lync-Client kein Benutzer Foto angezeigt, das Foto wird jedoch weiterhin auf Ihrer Visitenkarte und außerhalb von lync angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eace2-207">When you choose **Hide my picture**, no user photo is displayed for you in Lync client, but your photo is still displayed on your contact card and outside of Lync.</span></span>

</div>

<div>

## <a name="show-my-picture"></a><span data-ttu-id="eace2-208">Mein Bild anzeigen</span><span class="sxs-lookup"><span data-stu-id="eace2-208">Show my picture</span></span>

<span data-ttu-id="eace2-209">Wenn Sie die Option " **eigenes Bild anzeigen** " auswählen, wird das Benutzer Foto in Ihrem lync-Client und anderen Benutzern in lync-Unterhaltungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eace2-209">When you choose the **Show my picture** option, your user photo is displayed in your Lync client and to other users in Lync conversations.</span></span> <span data-ttu-id="eace2-210">Das verwendete Bild ist diejenige, die in AD DS gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="eace2-210">The image used is the one stored in AD DS.</span></span>

</div>

<div>

## <a name="show-a-picture-from-a-website"></a><span data-ttu-id="eace2-211">Anzeigen eines Bilds von einer Website</span><span class="sxs-lookup"><span data-stu-id="eace2-211">Show a picture from a website</span></span>

<span data-ttu-id="eace2-212">Die Option **Bild aus einer Website anzeigen** wird in lync 2013 verfügbar, nachdem eine Clientrichtlinie festgelegt wurde, um Sie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="eace2-212">The **Show picture from a website** option becomes available in Lync 2013 after a client policy is set to enable it.</span></span> <span data-ttu-id="eace2-213">Die Client Version muss neuer sein als 15.0.4535.1002, die mit den lync- [kumulativen Updates installiert wird: November 2013](https://go.microsoft.com/fwlink/p/?linkid=509908).</span><span class="sxs-lookup"><span data-stu-id="eace2-213">The client version must be newer than 15.0.4535.1002, which is installed with the [Lync Cumulative Updates: November 2013](https://go.microsoft.com/fwlink/p/?linkid=509908).</span></span> <span data-ttu-id="eace2-214">Benutzer müssen sich möglicherweise abmelden und wieder einloggen, um die Änderungen im Client anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="eace2-214">Users may need to log out and then back in again to see the changes in the client.</span></span>

<span data-ttu-id="eace2-215">Sie können festlegen, dass für die Clientrichtlinie das **Anzeigen von Bildern aus einer Website** Einstellung aktiviert wird, indem Sie die Richtlinie " [CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) " im lync Server-Verwaltungsshell festlegen.</span><span class="sxs-lookup"><span data-stu-id="eace2-215">You can set the client policy to enable to **Show picture from a website** setting by running the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) policy in the Lync Server Management Shell.</span></span> <span data-ttu-id="eace2-216">Die folgenden Beispiel-Cmdlets veranschaulichen, wie die Richtlinie für alle Benutzer in Ihrer Bereitstellung global festgelegt wird:</span><span class="sxs-lookup"><span data-stu-id="eace2-216">The following example cmdlets demonstrate how to set the policy globally for all users in your deployment:</span></span>

   ```powershell
    $pe=New-CsClientPolicyEntry -Name EnablePresencePhotoOptions -Value True
   ```

   ```powershell
    $po=Get-CsClientPolicy -Identity Global
   ```

   ```powershell
    $po.PolicyEntry.Add($pe)
   ```

   ```powershell
    Set-CsClientPolicy -Instance $po
   ```


<span data-ttu-id="eace2-217">Wenn ein Bild in das Postfach des Benutzers hochgeladen wird, erstellt Exchange automatisch eine Version mit niedrigerer Auflösung des Bilds, die in Clientanwendungen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="eace2-217">When an image is uploaded to the user’s mailbox, Exchange automatically creates a lower resolution version of the image which can be used in client applications.</span></span> <span data-ttu-id="eace2-218">Das Benutzer Foto wird auch in AD DS aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="eace2-218">The user photo is also updated in AD DS.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="eace2-219">Wenn eine Bilddatei in AD DS aktualisiert wird, wird ein 48 x 48 Pixel Bild erstellt und für die thumbnailPhoto in AD DS verwendet.</span><span class="sxs-lookup"><span data-stu-id="eace2-219">When an image file is updated in AD DS, a 48 x 48 pixel image is created and used for the thumbnailPhoto in AD DS.</span></span> <span data-ttu-id="eace2-220">Jedes vorhandene Bild wird ersetzt.</span><span class="sxs-lookup"><span data-stu-id="eace2-220">Any existing image is replaced.</span></span> <span data-ttu-id="eace2-221">Wenn Sie also AD DS ein 96 x 96-Bild hinzugefügt haben, wird es mit dem neuen 48 x 48-Bild überschrieben.</span><span class="sxs-lookup"><span data-stu-id="eace2-221">So if you added a 96 x 96 image to AD DS, it will be overwritten with the new 48 x 48 image.</span></span> <span data-ttu-id="eace2-222">Dies ist nur wichtig, wenn Sie über Benutzer in Ihrer Umgebung verfügen, die lync 2010-Clients verwenden, da diese Clients Benutzer Fotos von AD DS erhalten.</span><span class="sxs-lookup"><span data-stu-id="eace2-222">This is only important is you have users in your environment using Lync 2010 clients, as those clients will obtain user photos from AD DS.</span></span> <span data-ttu-id="eace2-223">Sie können 96 x 96 Pixelbilder importieren, um diejenigen zu ersetzen, die von AD DS erstellt wurden, wenn Sie lync 2010-Clients in Ihrer Organisation haben.</span><span class="sxs-lookup"><span data-stu-id="eace2-223">You can import 96 x 96 pixel images to replace the ones created by AD DS if you have Lync 2010 clients in your organization.</span></span>



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a><span data-ttu-id="eace2-224">Unterstützung für Benutzer Fotos in lync 2013</span><span class="sxs-lookup"><span data-stu-id="eace2-224">User photo support in Lync 2013</span></span>

<span data-ttu-id="eace2-225">In lync 2013 werden drei Bildauflösungen für Benutzer Fotos unterstützt, wie in der folgenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="eace2-225">In Lync 2013, three image resolutions are supported for user photos as described in the following table.</span></span> <span data-ttu-id="eace2-226">Das verwendete Bild wird durch die Clientrichtlinien Einstellung bestimmt, die lync-Benutzern zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="eace2-226">The image that is used is determined by the client policy setting assigned to Lync users.</span></span> <span data-ttu-id="eace2-227">Weitere Informationen finden Sie unter "Verwalten von Benutzer Fotos mit Client Richtlinien-Cmdlets" in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="eace2-227">See “Managing user’s photo with Client Policy cmdlets” in this topic for more information.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eace2-228">Bildauflösung (Pixel)</span><span class="sxs-lookup"><span data-stu-id="eace2-228">Image resolution (pixels)</span></span></th>
<th><span data-ttu-id="eace2-229">Anwendung</span><span class="sxs-lookup"><span data-stu-id="eace2-229">Application</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eace2-230">48 x 48</span><span class="sxs-lookup"><span data-stu-id="eace2-230">48 x 48</span></span></p></td>
<td><p><span data-ttu-id="eace2-231">Wird verwendet, wenn kein Bild mit höherer Auflösung ausgewählt ist</span><span class="sxs-lookup"><span data-stu-id="eace2-231">Used if no higher resolution image is selected</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eace2-232">96 x 96</span><span class="sxs-lookup"><span data-stu-id="eace2-232">96 x 96</span></span></p></td>
<td><p><span data-ttu-id="eace2-233">Wird in Outlook Web App und Outlook 2013 verwendet</span><span class="sxs-lookup"><span data-stu-id="eace2-233">Used in Outlook Web App and Outlook 2013</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eace2-234">648 x 648</span><span class="sxs-lookup"><span data-stu-id="eace2-234">648 x 648</span></span></p></td>
<td><p><span data-ttu-id="eace2-235">Wird in lync 2013-Desktop Client und lync 2013-Webanwendung verwendet</span><span class="sxs-lookup"><span data-stu-id="eace2-235">Used in Lync 2013 desktop client and Lync 2013 Web App</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="eace2-236">Jeder Benutzer mit einem in Exchange 2013 aktivierten Postfach kann ein anderes Bild, einschließlich hochauflösender Fotos, über Outlook Web Access oder lync 2013 Clientoptionen hochladen.</span><span class="sxs-lookup"><span data-stu-id="eace2-236">Any user with a mailbox enabled in Exchange 2013 can upload a different image, including high-resolution photos, through Outlook Web Access or Lync 2013 client options.</span></span> <span data-ttu-id="eace2-237">Die empfohlenen Einstellungen für verwendete Bilder umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="eace2-237">The recommended settings for images used include:</span></span>

  - <span data-ttu-id="eace2-238">**Bildauflösung**     648 von 648 Pixel</span><span class="sxs-lookup"><span data-stu-id="eace2-238">**Image Resolution**   648 by 648 pixels</span></span>

  - <span data-ttu-id="eace2-239">**Farbtiefe**     24-Bit-Version</span><span class="sxs-lookup"><span data-stu-id="eace2-239">**Color Depth**   24-bit</span></span>

  - <span data-ttu-id="eace2-240">**Bilddateigröße**     bis zu 20 MB</span><span class="sxs-lookup"><span data-stu-id="eace2-240">**Image file size**   up to 20 MB</span></span>

  - <span data-ttu-id="eace2-241">**Dateiformat**     JPEG</span><span class="sxs-lookup"><span data-stu-id="eace2-241">**File format**   JPEG</span></span>

<span data-ttu-id="eace2-242">Ein typisches 24-Bit-JPEG-Bild mit 648 Pixeln von 648 Pixel weist eine Dateigröße von etwa 240 KB auf, daher sind 1 MB Speicherplatz für alle 4 Benutzer Fotos erforderlich.</span><span class="sxs-lookup"><span data-stu-id="eace2-242">A typical 24-bit JPEG image that is 648 pixels by 648 pixels has a file size of about 240 KB, so 1 MB of storage space is needed for every 4 user photos.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

