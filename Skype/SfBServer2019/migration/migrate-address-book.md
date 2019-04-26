---
title: Migrieren des Adressbuchs
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Im Allgemeinen wird zusammen mit dem Rest der Topologie im Adressbuch migriert. Sie müssen jedoch möglicherweise einige Schritte nach der Migration ausführen, wenn Sie die folgenden in der Vorversion Umgebung angepasst:'
ms.openlocfilehash: 728ae97270cd8451178c6ef962f05e0351118119
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238424"
---
# <a name="migrate-address-book"></a><span data-ttu-id="fc974-104">Migrieren des Adressbuchs</span><span class="sxs-lookup"><span data-stu-id="fc974-104">Migrate Address Book</span></span>

<span data-ttu-id="fc974-105">Im Allgemeinen wird zusammen mit dem Rest der Topologie im Adressbuch migriert.</span><span class="sxs-lookup"><span data-stu-id="fc974-105">In general, the Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="fc974-106">Sie müssen jedoch möglicherweise einige Schritte nach der Migration ausführen, wenn Sie die folgenden in der Vorversion Umgebung angepasst:</span><span class="sxs-lookup"><span data-stu-id="fc974-106">However, you might need to perform some post-migration steps if you customized the following in your legacy environment:</span></span> 

- <span data-ttu-id="fc974-107">Die Adressbuch-Normalisierungsregeln angepasst.</span><span class="sxs-lookup"><span data-stu-id="fc974-107">Customized the Address Book normalization rules.</span></span>

- <span data-ttu-id="fc974-108">Der Standardwert für den **UseNormalizationRules** -Parameter auf "false" geändert.</span><span class="sxs-lookup"><span data-stu-id="fc974-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span> 


 <span data-ttu-id="fc974-109">**Beheben von Adressbuch-Normalisierungsregeln**</span><span class="sxs-lookup"><span data-stu-id="fc974-109">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="fc974-110">Wenn Sie in Ihrer Umgebung legacy-Adressbuch-Normalisierungsregeln angepasst haben, müssen Sie die benutzerdefinierten Regeln zum pilotpool migrieren.</span><span class="sxs-lookup"><span data-stu-id="fc974-110">If you customized Address Book normalization rules in your legacy environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="fc974-111">Wenn Ihnen nicht Adressbuch-Normalisierungsregeln konfiguriert, müssen Sie nichts für Adressbuchdienst migrieren.</span><span class="sxs-lookup"><span data-stu-id="fc974-111">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="fc974-112">Die Standard-Normalisierungsregeln für Skype für Business Server 2019 stimmen die Regeln für die legacy-Installation.</span><span class="sxs-lookup"><span data-stu-id="fc974-112">The default normalization rules for Skype for Business Server 2019 are the same as the default rules for the legacy install.</span></span> <span data-ttu-id="fc974-113">Führen Sie die weiter unten in diesem Abschnitt, um angepasste Normalisierungsregeln migrieren.</span><span class="sxs-lookup"><span data-stu-id="fc974-113">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

> [!NOTE]
> <span data-ttu-id="fc974-114">Wenn Ihre Organisation Remoteanrufsteuerung verwendet wird und Sie Normalisierungsregeln Adressbuch angepasst, müssen Sie das Verfahren in diesem Thema ausführen, bevor Sie Remoteanrufsteuerung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="fc974-114">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span></span> <span data-ttu-id="fc974-115">Das Verfahren ist die Mitgliedschaft in der Gruppe RTCUniversalServerAdmins oder über vergleichbare Rechte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fc974-115">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span> 

 <span data-ttu-id="fc974-116">**UseNormalizationRules "false" festgelegt**</span><span class="sxs-lookup"><span data-stu-id="fc974-116">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="fc974-117">Wenn den Wert für **UseNormalizationRules** auf False festgelegt werden, sodass Benutzer Rufnummern verwenden können, wie sie in definiert sind, Active Directory Domain Services, ohne dass Skype für Business Server 2019 anwenden Normalisierungsregeln, müssen Sie die **festlegen UseNormalizationRules** und **IgnoreGenericRules** -Parameter auf "true".</span><span class="sxs-lookup"><span data-stu-id="fc974-117">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Skype for Business Server 2019 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="fc974-118">Führen Sie die weiter unten in diesem Abschnitt können Sie diesen Parameter auf True festgelegt.</span><span class="sxs-lookup"><span data-stu-id="fc974-118">Follow the procedure later in this section to set these parameters to True.</span></span> 

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="fc974-119">Informationen zum Adressbuch migrieren Sie angepasste Normalisierungsregeln für</span><span class="sxs-lookup"><span data-stu-id="fc974-119">To migrate Address Book customized normalization rules</span></span>

1. <span data-ttu-id="fc974-120">Suchen Sie die Datei Company_Phone_Number_Normalization_Rules.txt im Stamm des freigegebenen adressbuchordners, und kopieren Sie sie in den Stamm des freigegebenen adressbuchordners in Ihrer Skype für Business Server 2019 pilot Pool.</span><span class="sxs-lookup"><span data-stu-id="fc974-120">Find the Company_Phone_Number_Normalization_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Skype for Business Server 2019 pilot pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fc974-121">Die Beispiel-Adressbuch-Normalisierungsregeln wurden in Ihrem ABS Web Component Dateiverzeichnis installiert.</span><span class="sxs-lookup"><span data-stu-id="fc974-121">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="fc974-122">Der Pfad ist **$installedDriveLetter: \Programme\Microsoft Skype für Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span><span class="sxs-lookup"><span data-stu-id="fc974-122">The path is **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span></span> <span data-ttu-id="fc974-123">Diese Datei kann kopiert und als **Company_Phone_Number_Normalization_Rules.txt** in Address Book des freigegebenen Ordners Stammverzeichnis umbenannt werden.</span><span class="sxs-lookup"><span data-stu-id="fc974-123">This file can be copied and renamed as **Company_Phone_Number_Normalization_Rules.txt** to the address book shared folder's root directory.</span></span> <span data-ttu-id="fc974-124">Beispielsweise in **$serverX**freigegebenen Adressbuch der Pfad werden ähnelt: \*\* \\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles\*\*.</span><span class="sxs-lookup"><span data-stu-id="fc974-124">For example, the address book shared in **$serverX**, the path will be similar to: **\\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**.</span></span> 

2. <span data-ttu-id="fc974-125">Verwenden Sie einen Text-Editor wie Editor ein, um die Datei Company_Phone_Number_Normalization_Rules.txt zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="fc974-125">Use a text editor, such as Notepad, to open the Company_Phone_Number_Normalization_Rules.txt file.</span></span>

3. <span data-ttu-id="fc974-126">Bestimmte Arten von Einträgen funktioniert ordnungsgemäß in Skype für Business Server 2019 nicht.</span><span class="sxs-lookup"><span data-stu-id="fc974-126">Certain types of entries will not work correctly in Skype for Business Server 2019.</span></span> <span data-ttu-id="fc974-127">Suchen Sie in der Datei für die Arten von Einträgen in diesem Schritt beschriebene, bearbeiten Sie diese nach Bedarf, und Speichern der Änderungen an der freigegebenen adressbuchordners im pilotpool.</span><span class="sxs-lookup"><span data-stu-id="fc974-127">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>

    <span data-ttu-id="fc974-128">Zeichenfolgen, die erforderliche Leerzeichen oder Satzzeichen Ursache Normalisierungsregeln ein Fehler auftritt, da diese Zeichen aus der Zeichenfolge entfernt werden, die Eingabe ist, die Normalisierungsregeln enthalten.</span><span class="sxs-lookup"><span data-stu-id="fc974-128">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="fc974-129">Wenn Sie Zeichenfolgen, die erforderlichen Leerzeichen oder Satzzeichen enthalten verfügen, müssen Sie die Zeichenfolgen ändern.</span><span class="sxs-lookup"><span data-stu-id="fc974-129">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="fc974-130">Beispielsweise würde die folgende Zeichenfolge die Normalisierungsregel fehlerfrei ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="fc974-130">For example, the following string would cause the normalization rule to fail:</span></span>

   ```
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    <span data-ttu-id="fc974-131">Mit der folgenden Zeichenfolge würde die Normalisierungsregel fehlerfrei ausgeführt nicht:</span><span class="sxs-lookup"><span data-stu-id="fc974-131">The following string would not cause the normalization rule to fail:</span></span>

   ```
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="fc974-132">UseNormalizationRules und IgnoreGenericRules auf "true" festlegen</span><span class="sxs-lookup"><span data-stu-id="fc974-132">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1. <span data-ttu-id="fc974-133">Starten Sie die Skype für Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype für Business Server 2019**, und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="fc974-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="fc974-134">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="fc974-134">Do one of the following:</span></span>

   - <span data-ttu-id="fc974-135">Wenn Ihre Bereitstellung nur Skype für Business Server 2019 umfasst, führen Sie das folgende Cmdlet auf globaler Ebene die Werte für **UseNormalizationRules** und **IgnoreGenericRules** auf "true" zu ändern:</span><span class="sxs-lookup"><span data-stu-id="fc974-135">If your deployment includes only Skype for Business Server 2019, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span> 

   ```
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - <span data-ttu-id="fc974-136">Wenn Ihre Bereitstellung eine Kombination von Skype für Business Server 2019 und eine legacy-Installation umfasst, führen Sie das folgende Cmdlet aus, und weisen Sie es jedem Skype für Business Server 2019 Pool in der Topologie:</span><span class="sxs-lookup"><span data-stu-id="fc974-136">If your deployment includes a combination of Skype for Business Server 2019 and a legacy install, run the following cmdlet and assign it to each Skype for Business Server 2019 pool in the topology:</span></span>

   ```
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. <span data-ttu-id="fc974-137">Warten Sie zentralen Speicher Replikation für alle Pools erfolgt.</span><span class="sxs-lookup"><span data-stu-id="fc974-137">Wait for Central Management store replication to occur on all pools.</span></span>

4. <span data-ttu-id="fc974-138">Ändern Sie die rufnummernnormalisierung Regeldatei "Company_Phone_Number_Normalization_Rules.txt" für die Bereitstellung den Inhalt gelöscht.</span><span class="sxs-lookup"><span data-stu-id="fc974-138">Modify the phone normalization rules file, "Company_Phone_Number_Normalization_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="fc974-139">Die Datei befindet sich auf die Dateifreigabe jedes Skype für Business Server 2019 Pool.</span><span class="sxs-lookup"><span data-stu-id="fc974-139">The file is on the file share of each Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="fc974-140">Wenn die Datei nicht vorhanden ist, klicken Sie dann erstellen Sie eine leere Datei mit dem Namen "Company_Phone_Number_Normalization_Rules.txt".</span><span class="sxs-lookup"><span data-stu-id="fc974-140">If the file is not present, then create an empty file named "Company_Phone_Number_Normalization_Rules.txt".</span></span>

5. <span data-ttu-id="fc974-141">Warten Sie einige Minuten für alle Front-End-Pools die neuen Dateien gelesen.</span><span class="sxs-lookup"><span data-stu-id="fc974-141">Wait several minutes for all Front End pools to read the new files.</span></span>

6. <span data-ttu-id="fc974-142">Führen Sie das folgende Cmdlet auf jede Skype für Business Server 2019 Pool in Ihrer Bereitstellung aus:</span><span class="sxs-lookup"><span data-stu-id="fc974-142">Run the following cmdlet on each Skype for Business Server 2019 pool in your deployment:</span></span>

   ```
   Update-CsAddressBook
   ```


