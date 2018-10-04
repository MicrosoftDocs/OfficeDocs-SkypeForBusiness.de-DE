---
title: Migrieren von Adressbüchern
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Im Allgemeinen wird zusammen mit dem Rest der Topologie im Adressbuch migriert. Sie müssen jedoch möglicherweise einige Schritte nach der Migration ausführen, wenn Sie die folgenden in der Vorversion Umgebung angepasst:'
ms.openlocfilehash: 01279284086499b112028644ea0e1ca2fc708dd0
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370769"
---
# <a name="migrate-address-book"></a><span data-ttu-id="a33ed-104">Migrieren von Adressbüchern</span><span class="sxs-lookup"><span data-stu-id="a33ed-104">Migrate Address Book</span></span>

<span data-ttu-id="a33ed-105">Im Allgemeinen wird zusammen mit dem Rest der Topologie im Adressbuch migriert.</span><span class="sxs-lookup"><span data-stu-id="a33ed-105">In general, the Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="a33ed-106">Sie müssen jedoch möglicherweise einige Schritte nach der Migration ausführen, wenn Sie die folgenden in der Vorversion Umgebung angepasst:</span><span class="sxs-lookup"><span data-stu-id="a33ed-106">However, you might need to perform some post-migration steps if you customized the following in your legacy environment:</span></span> 

- <span data-ttu-id="a33ed-107">Legen Sie die WMI-Eigenschaft **PartitionbyOU** auf Adressbucheinträge nach Organisationseinheit (OU).</span><span class="sxs-lookup"><span data-stu-id="a33ed-107">Set the **PartitionbyOU** WMI property to group Address Book entries by organizational unit (OU).</span></span> 

- <span data-ttu-id="a33ed-108">Die Adressbuch-Normalisierungsregeln angepasst.</span><span class="sxs-lookup"><span data-stu-id="a33ed-108">Customized the Address Book normalization rules.</span></span>

- <span data-ttu-id="a33ed-109">Der Standardwert für den **UseNormalizationRules** -Parameter auf "false" geändert.</span><span class="sxs-lookup"><span data-stu-id="a33ed-109">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span> 

  <span data-ttu-id="a33ed-110">**Gruppierte Adressbucheinträge**</span><span class="sxs-lookup"><span data-stu-id="a33ed-110">**Grouped Address Book Entries**</span></span>

<span data-ttu-id="a33ed-111">Wenn Sie die **"partitionbyou"** WMI-Eigenschaft auf True, um das Erstellen von Adressbüchern für jede Organisationseinheit festlegen, müssen Sie das **"MsRTCSIP-groupingid"** Active Directory-Attribut für Benutzer und Kontakte festgelegt, wenn Gruppieren von Adressbucheinträgen fortgesetzt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a33ed-111">If you set the **PartitionbyOU** WMI property to True to create address books for each OU, you need to set the **msRTCSIP-GroupingId** Active Directory attribute on users and contacts if you want to continue grouping address book entries.</span></span> <span data-ttu-id="a33ed-112">Zum Gruppe Adressbucheinträgen sollten zum Einschränken des Bereichs der Adressbuch-Suchvorgänge.</span><span class="sxs-lookup"><span data-stu-id="a33ed-112">You might want to group address book entries to limit the scope of Address Book searches.</span></span> <span data-ttu-id="a33ed-113">Schreiben Sie mithilfe des Attributs **"MsRTCSIP-groupingid"** , ein Skript zum Füllen Sie des Attributs, das Zuweisen von den gleichen Wert für alle Benutzer, die Sie gruppieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a33ed-113">To use the **msRTCSIP-GroupingId** attribute, write a script to populate the attribute, assigning the same value for all of the users that you want to group together.</span></span> <span data-ttu-id="a33ed-114">Weisen Sie beispielsweise einen single-Wert für alle Benutzer in einer Organisationseinheit.</span><span class="sxs-lookup"><span data-stu-id="a33ed-114">For example, assign a single value for all the users in an OU.</span></span> 

 <span data-ttu-id="a33ed-115">**Beheben von Adressbuch-Normalisierungsregeln**</span><span class="sxs-lookup"><span data-stu-id="a33ed-115">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="a33ed-116">Wenn Sie in Ihrer Umgebung legacy-Adressbuch-Normalisierungsregeln angepasst haben, müssen Sie die benutzerdefinierten Regeln zum pilotpool migrieren.</span><span class="sxs-lookup"><span data-stu-id="a33ed-116">If you customized Address Book normalization rules in your legacy environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="a33ed-117">Wenn Ihnen nicht Adressbuch-Normalisierungsregeln konfiguriert, müssen Sie nichts für Adressbuchdienst migrieren.</span><span class="sxs-lookup"><span data-stu-id="a33ed-117">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="a33ed-118">Die Standard-Normalisierungsregeln für Skype für Business Server 2019 stimmen die Regeln für die legacy-Installation.</span><span class="sxs-lookup"><span data-stu-id="a33ed-118">The default normalization rules for Skype for Business Server 2019 are the same as the default rules for the legacy install.</span></span> <span data-ttu-id="a33ed-119">Führen Sie die weiter unten in diesem Abschnitt, um angepasste Normalisierungsregeln migrieren.</span><span class="sxs-lookup"><span data-stu-id="a33ed-119">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

> [!NOTE]
> <span data-ttu-id="a33ed-120">Wenn Ihre Organisation Remoteanrufsteuerung verwendet wird und Sie Normalisierungsregeln Adressbuch angepasst, müssen Sie das Verfahren in diesem Thema ausführen, bevor Sie Remoteanrufsteuerung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a33ed-120">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span></span> <span data-ttu-id="a33ed-121">Das Verfahren ist die Mitgliedschaft in der Gruppe RTCUniversalServerAdmins oder über vergleichbare Rechte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a33ed-121">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span> 

 <span data-ttu-id="a33ed-122">**UseNormalizationRules "false" festgelegt**</span><span class="sxs-lookup"><span data-stu-id="a33ed-122">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="a33ed-123">Wenn den Wert für **UseNormalizationRules** auf False festgelegt werden, sodass Benutzer Rufnummern verwenden können, wie sie in definiert sind, Active Directory Domain Services, ohne dass Skype für Business Server 2019 anwenden Normalisierungsregeln, müssen Sie die **festlegen UseNormalizationRules** und **IgnoreGenericRules** -Parameter auf "true".</span><span class="sxs-lookup"><span data-stu-id="a33ed-123">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Skype for Business Server 2019 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="a33ed-124">Führen Sie die weiter unten in diesem Abschnitt können Sie diesen Parameter auf True festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a33ed-124">Follow the procedure later in this section to set these parameters to True.</span></span> 

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="a33ed-125">Informationen zum Adressbuch migrieren Sie angepasste Normalisierungsregeln für</span><span class="sxs-lookup"><span data-stu-id="a33ed-125">To migrate Address Book customized normalization rules</span></span>

1. <span data-ttu-id="a33ed-126">Suchen Sie die Datei Company_Phone_Number_Normalization_Rules.txt im Stamm des freigegebenen adressbuchordners, und kopieren Sie sie in den Stamm des freigegebenen adressbuchordners in Ihrer Skype für Business Server 2019 pilot Pool.</span><span class="sxs-lookup"><span data-stu-id="a33ed-126">Find the Company_Phone_Number_Normalization_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Skype for Business Server 2019 pilot pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a33ed-127">Die Beispiel-Adressbuch-Normalisierungsregeln wurden in Ihrem ABS Web Component Dateiverzeichnis installiert.</span><span class="sxs-lookup"><span data-stu-id="a33ed-127">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="a33ed-128">Der Pfad ist **$installedDriveLetter: \Programme\Microsoft Skype für Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span><span class="sxs-lookup"><span data-stu-id="a33ed-128">The path is **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span></span> <span data-ttu-id="a33ed-129">Diese Datei kann kopiert und als **Company_Phone_Number_Normalization_Rules.txt** in Address Book des freigegebenen Ordners Stammverzeichnis umbenannt werden.</span><span class="sxs-lookup"><span data-stu-id="a33ed-129">This file can be copied and renamed as **Company_Phone_Number_Normalization_Rules.txt** to the address book shared folder's root directory.</span></span> <span data-ttu-id="a33ed-130">Beispielsweise in **$serverX**freigegebenen Adressbuch der Pfad werden ähnelt: \*\* \\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles\*\*.</span><span class="sxs-lookup"><span data-stu-id="a33ed-130">For example, the address book shared in **$serverX**, the path will be similar to: **\\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**.</span></span> 

2. <span data-ttu-id="a33ed-131">Verwenden Sie einen Text-Editor wie Editor ein, um die Datei Company_Phone_Number_Normalization_Rules.txt zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a33ed-131">Use a text editor, such as Notepad, to open the Company_Phone_Number_Normalization_Rules.txt file.</span></span>

3. <span data-ttu-id="a33ed-132">Bestimmte Arten von Einträgen funktioniert ordnungsgemäß in Skype für Business Server 2019 nicht.</span><span class="sxs-lookup"><span data-stu-id="a33ed-132">Certain types of entries will not work correctly in Skype for Business Server 2019.</span></span> <span data-ttu-id="a33ed-133">Suchen Sie in der Datei für die Arten von Einträgen in diesem Schritt beschriebene, bearbeiten Sie diese nach Bedarf, und Speichern der Änderungen an der freigegebenen adressbuchordners im pilotpool.</span><span class="sxs-lookup"><span data-stu-id="a33ed-133">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>

    <span data-ttu-id="a33ed-134">Zeichenfolgen, die erforderliche Leerzeichen oder Satzzeichen Ursache Normalisierungsregeln ein Fehler auftritt, da diese Zeichen aus der Zeichenfolge entfernt werden, die Eingabe ist, die Normalisierungsregeln enthalten.</span><span class="sxs-lookup"><span data-stu-id="a33ed-134">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="a33ed-135">Wenn Sie Zeichenfolgen, die erforderlichen Leerzeichen oder Satzzeichen enthalten verfügen, müssen Sie die Zeichenfolgen ändern.</span><span class="sxs-lookup"><span data-stu-id="a33ed-135">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="a33ed-136">Beispielsweise würde die folgende Zeichenfolge die Normalisierungsregel fehlerfrei ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="a33ed-136">For example, the following string would cause the normalization rule to fail:</span></span>

   ```
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    <span data-ttu-id="a33ed-137">Mit der folgenden Zeichenfolge würde die Normalisierungsregel fehlerfrei ausgeführt nicht:</span><span class="sxs-lookup"><span data-stu-id="a33ed-137">The following string would not cause the normalization rule to fail:</span></span>

   ```
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="a33ed-138">UseNormalizationRules und IgnoreGenericRules auf "true" festlegen</span><span class="sxs-lookup"><span data-stu-id="a33ed-138">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1. <span data-ttu-id="a33ed-139">Starten Sie die Skype für Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype für Business Server 2019**, und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="a33ed-139">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="a33ed-140">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="a33ed-140">Do one of the following:</span></span>

   - <span data-ttu-id="a33ed-141">Wenn Ihre Bereitstellung nur Skype für Business Server 2019 umfasst, führen Sie das folgende Cmdlet auf globaler Ebene die Werte für **UseNormalizationRules** und **IgnoreGenericRules** auf "true" zu ändern:</span><span class="sxs-lookup"><span data-stu-id="a33ed-141">If your deployment includes only Skype for Business Server 2019, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span> 

   ```
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - <span data-ttu-id="a33ed-142">Wenn Ihre Bereitstellung eine Kombination von Skype für Business Server 2019 und eine legacy-Installation umfasst, führen Sie das folgende Cmdlet aus, und weisen Sie es jedem Skype für Business Server 2019 Pool in der Topologie:</span><span class="sxs-lookup"><span data-stu-id="a33ed-142">If your deployment includes a combination of Skype for Business Server 2019 and a legacy install, run the following cmdlet and assign it to each Skype for Business Server 2019 pool in the topology:</span></span>

   ```
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. <span data-ttu-id="a33ed-143">Warten Sie zentralen Speicher Replikation für alle Pools erfolgt.</span><span class="sxs-lookup"><span data-stu-id="a33ed-143">Wait for Central Management store replication to occur on all pools.</span></span>

4. <span data-ttu-id="a33ed-144">Ändern Sie die rufnummernnormalisierung Regeldatei "Company_Phone_Number_Normalization_Rules.txt" für die Bereitstellung den Inhalt gelöscht.</span><span class="sxs-lookup"><span data-stu-id="a33ed-144">Modify the phone normalization rules file, "Company_Phone_Number_Normalization_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="a33ed-145">Die Datei befindet sich auf die Dateifreigabe jedes Skype für Business Server 2019 Pool.</span><span class="sxs-lookup"><span data-stu-id="a33ed-145">The file is on the file share of each Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="a33ed-146">Wenn die Datei nicht vorhanden ist, klicken Sie dann erstellen Sie eine leere Datei mit dem Namen "Company_Phone_Number_Normalization_Rules.txt".</span><span class="sxs-lookup"><span data-stu-id="a33ed-146">If the file is not present, then create an empty file named "Company_Phone_Number_Normalization_Rules.txt".</span></span>

5. <span data-ttu-id="a33ed-147">Warten Sie einige Minuten für alle Front-End-Pools die neuen Dateien gelesen.</span><span class="sxs-lookup"><span data-stu-id="a33ed-147">Wait several minutes for all Front End pools to read the new files.</span></span>

6. <span data-ttu-id="a33ed-148">Führen Sie das folgende Cmdlet auf jede Skype für Business Server 2019 Pool in Ihrer Bereitstellung aus:</span><span class="sxs-lookup"><span data-stu-id="a33ed-148">Run the following cmdlet on each Skype for Business Server 2019 pool in your deployment:</span></span>

   ```
   Update-CsAddressBook
   ```


