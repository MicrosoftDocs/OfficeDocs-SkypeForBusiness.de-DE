---
title: Migrieren des Adressbuchs
description: Migrieren des Adressbuchs
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205160(v=OCS.15)
ms:contentKeyID: 48185064
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad6acd8cca58aa4e09e21b9b45cbdddec527b5f8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579391"
---
# <a name="migrate-address-book"></a><span data-ttu-id="f2bd7-103">Migrieren des Adressbuchs</span><span class="sxs-lookup"><span data-stu-id="f2bd7-103">Migrate Address Book</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2bd7-104">_**Letztes Änderungsstand des Themas:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="f2bd7-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="f2bd7-105">Im Allgemeinen wird das lync Server 2010 Adressbuch zusammen mit der restlichen Topologie migriert.</span><span class="sxs-lookup"><span data-stu-id="f2bd7-105">In general, the Lync Server 2010 Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="f2bd7-106">Möglicherweise müssen Sie jedoch einige Schritte nach der Migration durchführen, wenn Sie Folgendes in ihrer lync Server 2010 Umgebung angepasst haben:</span><span class="sxs-lookup"><span data-stu-id="f2bd7-106">However, you might need to perform some post-migration steps if you customized the following in your Lync Server 2010 environment:</span></span>

  - <span data-ttu-id="f2bd7-107">Sie haben die WMI-Eigenschaft **PartitionbyOU** so festgelegt, dass Adressbucheinträge nach Organisationseinheit (Organizational Unit, OU) zusammengefasst werden.</span><span class="sxs-lookup"><span data-stu-id="f2bd7-107">Set the **PartitionbyOU** WMI property to group Address Book entries by organizational unit (OU).</span></span>

  - <span data-ttu-id="f2bd7-108">Sie haben die Normalisierungsregeln für das Adressbuch angepasst.</span><span class="sxs-lookup"><span data-stu-id="f2bd7-108">Customized the Address Book normalization rules.</span></span>

  - <span data-ttu-id="f2bd7-109">Sie haben den Standardwert für den **UseNormalizationRules**-Parameter in "False" geändert.</span><span class="sxs-lookup"><span data-stu-id="f2bd7-109">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span>

<span data-ttu-id="f2bd7-110">**Gruppierte Adressbucheinträge**</span><span class="sxs-lookup"><span data-stu-id="f2bd7-110">**Grouped Address Book Entries**</span></span>

<span data-ttu-id="f2bd7-p102">Wenn Sie die WMI-Eigenschaft **PartitionbyOU** auf "True" festgelegt haben, sodass für jede Organisationseinheit Adressbücher erstellt werden, müssen Sie das Active Directory-Attribut **msRTCSIP-GroupingId** für Benutzer und Kontakte festlegen, wenn Adressbucheinträge weiterhin gruppiert werden sollen. Das Gruppieren von Adressbucheinträgen ist vorteilhaft, um den Umfang von Adressbuchsuchen einzugrenzen. Zur Verwendung des **msRTCSIP-GroupingId**-Attributs schreiben Sie ein Skript zum Auffüllen des Attributs, wobei Sie allen Benutzern, die in einer Gruppe zusammengefasst werden sollen, den gleichen Wert zuweisen. Beispiel: Weisen Sie allen Benutzern in einer Organisationseinheit einen einzigen Wert zu.</span><span class="sxs-lookup"><span data-stu-id="f2bd7-p102">If you set the **PartitionbyOU** WMI property to True to create address books for each OU, you need to set the **msRTCSIP-GroupingId** Active Directory attribute on users and contacts if you want to continue grouping address book entries. You might want to group address book entries to limit the scope of Address Book searches. To use the **msRTCSIP-GroupingId** attribute, write a script to populate the attribute, assigning the same value for all of the users that you want to group together. For example, assign a single value for all the users in an OU.</span></span>

<span data-ttu-id="f2bd7-115">**Adressbuch-Normalisierungsregeln**</span><span class="sxs-lookup"><span data-stu-id="f2bd7-115">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="f2bd7-116">Wenn Sie die Regeln für die Adressbuch Normalisierung in ihrer lync Server 2010 Umgebung angepasst haben, müssen Sie die benutzerdefinierten Regeln in Ihren Pilot Pool migrieren.</span><span class="sxs-lookup"><span data-stu-id="f2bd7-116">If you customized Address Book normalization rules in your Lync Server 2010 environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="f2bd7-117">Haben Sie die Adressbuch-Normalisierungsregeln nicht angepasst, ist für den Adressbuchdienst nichts zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="f2bd7-117">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="f2bd7-118">Die Standard Normalisierungsregeln für lync Server 2013 entsprechen den Standardregeln für lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f2bd7-118">The default normalization rules for Lync Server 2013 are the same as the default rules for Lync Server 2010.</span></span> <span data-ttu-id="f2bd7-119">Führen Sie das später in diesem Abschnitt beschriebene Verfahren aus, um angepasste Normalisierungsregeln zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="f2bd7-119">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f2bd7-p104">Wenn in Ihrer Organisation Remoteanrufsteuerung verwendet wird und Sie Normalisierungsregeln für Adressbücher angepasst haben, müssen Sie das Verfahren in diesem Thema ausführen, bevor Sie die Remoteanrufsteuerung nutzen können. Dazu müssen Sie Mitglied der Gruppe "RTCUniversalServerAdmins" sein oder gleichwertige Rechte innehaben.</span><span class="sxs-lookup"><span data-stu-id="f2bd7-p104">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control. The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span>



</div>

<span data-ttu-id="f2bd7-122">**Festlegen von "UseNormalizationRules" auf "False"**</span><span class="sxs-lookup"><span data-stu-id="f2bd7-122">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="f2bd7-123">Wenn Sie den Wert für **UseNormalizationRules** auf false festlegen, damit Benutzer Telefonnummern so verwenden können, wie Sie in Active Directory-Domänendienste definiert sind, ohne Normalisierungsregeln lync Server 2013 anzuwenden, müssen Sie die Parameter **UseNormalizationRules** und **IgnoreGenericRules** auf true festlegen.</span><span class="sxs-lookup"><span data-stu-id="f2bd7-123">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Lync Server 2013 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="f2bd7-124">Führen Sie das später in diesem Abschnitt beschriebene Verfahren aus, um diese Parameter auf "True" festzulegen.</span><span class="sxs-lookup"><span data-stu-id="f2bd7-124">Follow the procedure later in this section to set these parameters to True.</span></span>

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="f2bd7-125">So migrieren Sie angepasste Normalisierungsregeln für Adressbücher</span><span class="sxs-lookup"><span data-stu-id="f2bd7-125">To migrate Address Book customized normalization rules</span></span>

1.  <span data-ttu-id="f2bd7-126">Suchen Sie die \_ Normalisierung der Firmentelefonnummer \_ \_ \_Rules.txt Datei im Stammverzeichnis des freigegebenen Adressbuch Ordners, und kopieren Sie Sie in den Stamm des freigegebenen Adressbuch Ordners in Ihrem lync Server 2013-Pilot Pool.</span><span class="sxs-lookup"><span data-stu-id="f2bd7-126">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f2bd7-127">Die Beispiele für die Normalisierungsregeln für Adressbücher wurden in Ihrem ABS Web-Komponentendateiverzeichnis installiert.</span><span class="sxs-lookup"><span data-stu-id="f2bd7-127">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="f2bd7-128">Der Pfad lautet <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f2bd7-128">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="f2bd7-129">Diese Datei kann kopiert und als &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp; in das Stammverzeichnis des freigegebenen Adressbuch Ordners umbenannt werden.</span><span class="sxs-lookup"><span data-stu-id="f2bd7-129">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="f2bd7-130">Beispielsweise ist das in <STRONG>$serverX</STRONG>freigegebene Adressbuch &nbsp; der Pfad ähnlich wie: <STRONG> \\ $serverX \LyncFileShare\2-Webservices-1\ABFiles</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f2bd7-130">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="f2bd7-131">Verwenden Sie einen Text-Editor wie Editor, um die \_ \_ \_ Normalisierung \_Rules.txt Datei für Firmennummern zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f2bd7-131">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="f2bd7-132">Bestimmte Typen von Einträgen funktionieren in lync Server 2013 nicht ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="f2bd7-132">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="f2bd7-133">Durchsuchen Sie die Datei nach den hier beschriebenen Typen von Einträgen, bearbeiten Sie die Einträge entsprechend, und speichern Sie die Änderungen im freigegebenen Adressbuchordner im Pilotpool.</span><span class="sxs-lookup"><span data-stu-id="f2bd7-133">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="f2bd7-p108">Zeichenfolgen, die erforderliche Leerzeichen oder Satzzeichen enthalten, können Fehler bei der Ausführung der Normalisierungsregeln verursachen, weil diese Zeichen aus den Zeichenfolgen, die in die Normalisierungsregeln eingelesen werden, entfernt werden. Wenn Sie Zeichenfolgen mit erforderlichen Leerzeichen oder Satzzeichen haben, müssen Sie diese Zeichenfolgen bearbeiten. Beispielsweise würde die folgende Zeichenfolge einen Fehler bei der Normalisierungsregel verursachen:</span><span class="sxs-lookup"><span data-stu-id="f2bd7-p108">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules. If you have strings that include required whitespace or punctuation, you need to modify the strings. For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="f2bd7-137">Mit der folgenden Zeichenfolge würde die Normalisierungsregel fehlerfrei ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="f2bd7-137">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="f2bd7-138">So legen Sie "UseNormalizationRules" und "IgnoreGenericRules" auf "True" fest</span><span class="sxs-lookup"><span data-stu-id="f2bd7-138">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1.  <span data-ttu-id="f2bd7-139">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="f2bd7-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f2bd7-140">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f2bd7-140">Do one of the following:</span></span>
    
      - <span data-ttu-id="f2bd7-141">Wenn Ihre Bereitstellung nur lync Server 2013 enthält, führen Sie das folgende Cmdlet auf globaler Ebene aus, um die Werte für **UseNormalizationRules** und **IgnoreGenericRules** in true zu ändern:</span><span class="sxs-lookup"><span data-stu-id="f2bd7-141">If your deployment includes only Lync Server 2013, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="f2bd7-142">Wenn Ihre Bereitstellung eine Kombination aus lync Server 2013 und lync Server 2010 oder Office Communications Server 2007 R2 enthält, führen Sie das folgende Cmdlet aus, und weisen Sie es jedem lync Server 2013 Pool in der Topologie zu:</span><span class="sxs-lookup"><span data-stu-id="f2bd7-142">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="f2bd7-143">Warten Sie, bis die Replikation des zentralen Verwaltungsspeichers in allen Pools ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f2bd7-143">Wait for Central Management store replication to occur on all pools.</span></span>

4.  <span data-ttu-id="f2bd7-144">Ändern Sie die Regeldatei für die Telefon Normalisierung, "NormalisierungRules.txt für Unternehmens- \_ Telefon \_ Nummern \_ \_ ", damit Ihre Bereitstellung den Inhalt löscht.</span><span class="sxs-lookup"><span data-stu-id="f2bd7-144">Modify the phone normalization rules file, "Company\_Phone\_Number\_Normalization\_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="f2bd7-145">Die Datei befindet sich in der Dateifreigabe der einzelnen lync Server 2013 Pools.</span><span class="sxs-lookup"><span data-stu-id="f2bd7-145">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="f2bd7-146">Wenn die Datei nicht vorhanden ist, erstellen Sie eine leere Datei mit dem Namen "Unternehmens- \_ Telefon \_ Nummer \_ Normalisierung \_Rules.txt".</span><span class="sxs-lookup"><span data-stu-id="f2bd7-146">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt".</span></span>

5.  <span data-ttu-id="f2bd7-147">Warten Sie einige Minuten, bis alle Front-End-Pools die neuen Dateien gelesen haben.</span><span class="sxs-lookup"><span data-stu-id="f2bd7-147">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="f2bd7-148">Führen Sie das folgende Cmdlet für jeden lync Server 2013 Pool in der Bereitstellung aus:</span><span class="sxs-lookup"><span data-stu-id="f2bd7-148">Run the following cmdlet on each Lync Server 2013 pool in your deployment:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

