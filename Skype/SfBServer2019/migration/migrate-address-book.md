---
title: Migrieren des Adressbuchs
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Im Allgemeinen wird das Adressbuch zusammen mit der restlichen Topologie migriert. Möglicherweise müssen Sie jedoch einige Schritte nach der Migration durchführen, wenn Sie Folgendes in ihrer Vorgänger Umgebung angepasst haben:'
ms.openlocfilehash: 6d2ccf0d38814d149495518a71f888f0c2999d24
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752837"
---
# <a name="migrate-address-book"></a><span data-ttu-id="f087f-104">Migrieren des Adressbuchs</span><span class="sxs-lookup"><span data-stu-id="f087f-104">Migrate Address Book</span></span>

<span data-ttu-id="f087f-105">Im Allgemeinen wird das Adressbuch zusammen mit der restlichen Topologie migriert.</span><span class="sxs-lookup"><span data-stu-id="f087f-105">In general, the Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="f087f-106">Möglicherweise müssen Sie jedoch einige Schritte nach der Migration durchführen, wenn Sie Folgendes in ihrer Vorgänger Umgebung angepasst haben:</span><span class="sxs-lookup"><span data-stu-id="f087f-106">However, you might need to perform some post-migration steps if you customized the following in your legacy environment:</span></span> 

- <span data-ttu-id="f087f-107">Sie haben die Normalisierungsregeln für das Adressbuch angepasst.</span><span class="sxs-lookup"><span data-stu-id="f087f-107">Customized the Address Book normalization rules.</span></span>

- <span data-ttu-id="f087f-108">Sie haben den Standardwert für den **UseNormalizationRules**-Parameter in "False" geändert.</span><span class="sxs-lookup"><span data-stu-id="f087f-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span> 


 <span data-ttu-id="f087f-109">**Adressbuch-Normalisierungsregeln**</span><span class="sxs-lookup"><span data-stu-id="f087f-109">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="f087f-110">Wenn Sie die Regeln für die Adressbuch Normalisierung in ihrer Vorgänger Umgebung angepasst haben, müssen Sie die benutzerdefinierten Regeln in Ihren Pilot Pool migrieren.</span><span class="sxs-lookup"><span data-stu-id="f087f-110">If you customized Address Book normalization rules in your legacy environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="f087f-111">Haben Sie die Adressbuch-Normalisierungsregeln nicht angepasst, ist für den Adressbuchdienst nichts zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="f087f-111">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="f087f-112">Die Standard Normalisierungsregeln für Skype for Business Server 2019 sind identisch mit den Standardregeln für die Legacy Installation.</span><span class="sxs-lookup"><span data-stu-id="f087f-112">The default normalization rules for Skype for Business Server 2019 are the same as the default rules for the legacy install.</span></span> <span data-ttu-id="f087f-113">Führen Sie das später in diesem Abschnitt beschriebene Verfahren aus, um angepasste Normalisierungsregeln zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="f087f-113">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

> [!NOTE]
> <span data-ttu-id="f087f-p104">Wenn in Ihrer Organisation Remoteanrufsteuerung verwendet wird und Sie Normalisierungsregeln für Adressbücher angepasst haben, müssen Sie das Verfahren in diesem Thema ausführen, bevor Sie die Remoteanrufsteuerung nutzen können. Dazu müssen Sie Mitglied der Gruppe "RTCUniversalServerAdmins" sein oder gleichwertige Rechte innehaben.</span><span class="sxs-lookup"><span data-stu-id="f087f-p104">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control. The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span> 

 <span data-ttu-id="f087f-116">**Festlegen von "UseNormalizationRules" auf "False"**</span><span class="sxs-lookup"><span data-stu-id="f087f-116">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="f087f-117">Wenn Sie den Wert für **UseNormalizationRules** auf false festlegen, damit Benutzer Telefonnummern so verwenden können, wie Sie in Active Directory-Domänendienste definiert sind, ohne Skype for Business Server 2019 Normalisierungsregeln anzuwenden, müssen Sie die Parameter **UseNormalizationRules** und **IgnoreGenericRules** auf true festlegen.</span><span class="sxs-lookup"><span data-stu-id="f087f-117">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Skype for Business Server 2019 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="f087f-118">Führen Sie das später in diesem Abschnitt beschriebene Verfahren aus, um diese Parameter auf "True" festzulegen.</span><span class="sxs-lookup"><span data-stu-id="f087f-118">Follow the procedure later in this section to set these parameters to True.</span></span> 

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="f087f-119">So migrieren Sie angepasste Normalisierungsregeln für Adressbücher</span><span class="sxs-lookup"><span data-stu-id="f087f-119">To migrate Address Book customized normalization rules</span></span>

1. <span data-ttu-id="f087f-120">Suchen Sie die Company_Phone_Number_Normalization_Rules.txt Datei im Stammverzeichnis des freigegebenen Adressbuch Ordners, und kopieren Sie Sie in den Stamm des freigegebenen Adressbuch Ordners in Ihrem Skype for Business Server 2019-Pilot Pool.</span><span class="sxs-lookup"><span data-stu-id="f087f-120">Find the Company_Phone_Number_Normalization_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Skype for Business Server 2019 pilot pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f087f-121">Die Beispiele für die Normalisierungsregeln für Adressbücher wurden in Ihrem ABS Web-Komponentendateiverzeichnis installiert.</span><span class="sxs-lookup"><span data-stu-id="f087f-121">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="f087f-122">Der Pfad ist **$installedDriveLetter: \Programme\Microsoft Skype for Business Server 2019 \ Components\Address Adress Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span><span class="sxs-lookup"><span data-stu-id="f087f-122">The path is **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span></span> <span data-ttu-id="f087f-123">Diese Datei kann kopiert und als **Company_Phone_Number_Normalization_Rules.txt** in das Stammverzeichnis des freigegebenen Adressbuch Ordners umbenannt werden.</span><span class="sxs-lookup"><span data-stu-id="f087f-123">This file can be copied and renamed as **Company_Phone_Number_Normalization_Rules.txt** to the address book shared folder's root directory.</span></span> <span data-ttu-id="f087f-124">Beispielsweise ist das in **$serverX**freigegebene Adressbuch der Pfad ähnlich wie: \*\* \\ $serverX \SkypeForBusiness-FileShare\2-Webservices-1\ABFiles\*\*.</span><span class="sxs-lookup"><span data-stu-id="f087f-124">For example, the address book shared in **$serverX**, the path will be similar to: **\\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**.</span></span> 

2. <span data-ttu-id="f087f-125">Öffnen Sie die Datei "Company_Phone_Number_Normalization_Rules.txt" in einem Text-Editor, z. B. Editor.</span><span class="sxs-lookup"><span data-stu-id="f087f-125">Use a text editor, such as Notepad, to open the Company_Phone_Number_Normalization_Rules.txt file.</span></span>

3. <span data-ttu-id="f087f-126">Bestimmte Arten von Einträgen funktionieren in Skype for Business Server 2019 nicht ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="f087f-126">Certain types of entries will not work correctly in Skype for Business Server 2019.</span></span> <span data-ttu-id="f087f-127">Durchsuchen Sie die Datei nach den hier beschriebenen Typen von Einträgen, bearbeiten Sie die Einträge entsprechend, und speichern Sie die Änderungen im freigegebenen Adressbuchordner im Pilotpool.</span><span class="sxs-lookup"><span data-stu-id="f087f-127">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>

    <span data-ttu-id="f087f-p108">Zeichenfolgen, die erforderliche Leerzeichen oder Satzzeichen enthalten, können Fehler bei der Ausführung der Normalisierungsregeln verursachen, weil diese Zeichen aus den Zeichenfolgen, die in die Normalisierungsregeln eingelesen werden, entfernt werden. Wenn Sie Zeichenfolgen mit erforderlichen Leerzeichen oder Satzzeichen haben, müssen Sie diese Zeichenfolgen bearbeiten. Beispielsweise würde die folgende Zeichenfolge einen Fehler bei der Normalisierungsregel verursachen:</span><span class="sxs-lookup"><span data-stu-id="f087f-p108">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules. If you have strings that include required whitespace or punctuation, you need to modify the strings. For example, the following string would cause the normalization rule to fail:</span></span>

   ```console
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    <span data-ttu-id="f087f-131">Mit der folgenden Zeichenfolge würde die Normalisierungsregel fehlerfrei ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="f087f-131">The following string would not cause the normalization rule to fail:</span></span>

   ```console
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="f087f-132">So legen Sie "UseNormalizationRules" und "IgnoreGenericRules" auf "True" fest</span><span class="sxs-lookup"><span data-stu-id="f087f-132">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1. <span data-ttu-id="f087f-133">Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype for Business Server 2019**, und klicken Sie dann auf **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f087f-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="f087f-134">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f087f-134">Do one of the following:</span></span>

   - <span data-ttu-id="f087f-135">Wenn Ihre Bereitstellung nur Skype for Business Server 2019 enthält, führen Sie das folgende Cmdlet auf globaler Ebene aus, um die Werte für **UseNormalizationRules** und **IgnoreGenericRules** in true zu ändern:</span><span class="sxs-lookup"><span data-stu-id="f087f-135">If your deployment includes only Skype for Business Server 2019, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span> 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - <span data-ttu-id="f087f-136">Wenn Ihre Bereitstellung eine Kombination aus Skype for Business Server 2019 und einer Legacy Installation enthält, führen Sie das folgende Cmdlet aus, und weisen Sie es jedem Pool Skype for Business Server 2019 in der Topologie zu:</span><span class="sxs-lookup"><span data-stu-id="f087f-136">If your deployment includes a combination of Skype for Business Server 2019 and a legacy install, run the following cmdlet and assign it to each Skype for Business Server 2019 pool in the topology:</span></span>

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. <span data-ttu-id="f087f-137">Warten Sie, bis die Replikation des zentralen Verwaltungsspeichers in allen Pools ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f087f-137">Wait for Central Management store replication to occur on all pools.</span></span>

4. <span data-ttu-id="f087f-138">Ändern Sie die Datei mit den Telefonnormalisierungsregeln ("Company_Phone_Number_Normalization_Rules.txt") für die Bereitstellung, sodass die Inhalte gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="f087f-138">Modify the phone normalization rules file, "Company_Phone_Number_Normalization_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="f087f-139">Die Datei befindet sich in der Dateifreigabe jedes Skype for Business Server 2019-Pools.</span><span class="sxs-lookup"><span data-stu-id="f087f-139">The file is on the file share of each Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="f087f-140">Wenn die Datei nicht vorhanden ist, erstellen Sie eine leere Datei mit der Bezeichnung "Company_Phone_Number_Normalization_Rules.txt".</span><span class="sxs-lookup"><span data-stu-id="f087f-140">If the file is not present, then create an empty file named "Company_Phone_Number_Normalization_Rules.txt".</span></span>

5. <span data-ttu-id="f087f-141">Warten Sie einige Minuten, bis alle Front-End-Pools die neuen Dateien gelesen haben.</span><span class="sxs-lookup"><span data-stu-id="f087f-141">Wait several minutes for all Front End pools to read the new files.</span></span>

6. <span data-ttu-id="f087f-142">Führen Sie das folgende Cmdlet für jeden Skype for Business Server 2019-Pool in der Bereitstellung aus:</span><span class="sxs-lookup"><span data-stu-id="f087f-142">Run the following cmdlet on each Skype for Business Server 2019 pool in your deployment:</span></span>

   ```PowerShell
   Update-CsAddressBook
   ```


