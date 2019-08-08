---
title: Migrieren des Adressbuchs
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Im Allgemeinen wird das Adressbuch zusammen mit der restlichen Topologie migriert. Möglicherweise müssen Sie jedoch einige Schritte nach der Migration durchführen, wenn Sie die folgenden Schritte in ihrer Legacyumgebung angepasst haben:'
ms.openlocfilehash: 4a3a85715b73c3a6b5996ba677b0647c87a8db1e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238053"
---
# <a name="migrate-address-book"></a><span data-ttu-id="bca38-104">Migrieren des Adressbuchs</span><span class="sxs-lookup"><span data-stu-id="bca38-104">Migrate Address Book</span></span>

<span data-ttu-id="bca38-105">Im Allgemeinen wird das Adressbuch zusammen mit der restlichen Topologie migriert.</span><span class="sxs-lookup"><span data-stu-id="bca38-105">In general, the Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="bca38-106">Möglicherweise müssen Sie jedoch einige Schritte nach der Migration durchführen, wenn Sie die folgenden Schritte in ihrer Legacyumgebung angepasst haben:</span><span class="sxs-lookup"><span data-stu-id="bca38-106">However, you might need to perform some post-migration steps if you customized the following in your legacy environment:</span></span> 

- <span data-ttu-id="bca38-107">Benutzerdefinierte Adressbuch-Normalisierungsregeln.</span><span class="sxs-lookup"><span data-stu-id="bca38-107">Customized the Address Book normalization rules.</span></span>

- <span data-ttu-id="bca38-108">Der Standardwert für den **UseNormalizationRules** -Parameter wurde auf "false" geändert.</span><span class="sxs-lookup"><span data-stu-id="bca38-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span> 


 <span data-ttu-id="bca38-109">**Regeln für die Normalisierung des Adressbuchs**</span><span class="sxs-lookup"><span data-stu-id="bca38-109">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="bca38-110">Wenn Sie in ihrer Legacyumgebung Adressbuch-Normalisierungsregeln angepasst haben, müssen Sie die angepassten Regeln in Ihren Pilot Pool migrieren.</span><span class="sxs-lookup"><span data-stu-id="bca38-110">If you customized Address Book normalization rules in your legacy environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="bca38-111">Wenn Sie die Regeln für die Adressbuch Normalisierung nicht angepasst haben, müssen Sie für den Adressbuchdienst nichts migrieren.</span><span class="sxs-lookup"><span data-stu-id="bca38-111">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="bca38-112">Die standardmäßigen Normalisierungsregeln für Skype for Business Server 2019 sind mit den Standardregeln für die Legacy Installation identisch.</span><span class="sxs-lookup"><span data-stu-id="bca38-112">The default normalization rules for Skype for Business Server 2019 are the same as the default rules for the legacy install.</span></span> <span data-ttu-id="bca38-113">Führen Sie die Schritte weiter unten in diesem Abschnitt aus, um angepasste Normalisierungsregeln zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="bca38-113">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

> [!NOTE]
> <span data-ttu-id="bca38-114">Wenn in Ihrer Organisation die Remoteanrufsteuerung verwendet wird und Sie die Regeln für die Adressbuch Normalisierung angepasst haben, müssen Sie das in diesem Thema beschriebene Verfahren ausführen, bevor Sie die Remoteanrufsteuerung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="bca38-114">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span></span> <span data-ttu-id="bca38-115">Für das Verfahren ist die Mitgliedschaft in der RTCUniversalServerAdmins-Gruppe oder entsprechende Rechte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bca38-115">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span> 

 <span data-ttu-id="bca38-116">**UseNormalizationRules auf "false" festgelegt**</span><span class="sxs-lookup"><span data-stu-id="bca38-116">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="bca38-117">Wenn Sie den Wert für **UseNormalizationRules** auf "false" festlegen, damit Benutzer Telefonnummern verwenden können, wie Sie in den Active Directory-Domänendiensten definiert sind, ohne dass Skype for Business Server 2019 die Normalisierungsregeln anwenden, müssen Sie die \*\* UseNormalizationRules\*\* -und **IgnoreGenericRules** -Parameter auf true fest.</span><span class="sxs-lookup"><span data-stu-id="bca38-117">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Skype for Business Server 2019 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="bca38-118">Führen Sie die Schritte weiter unten in diesem Abschnitt aus, um diese Parameter auf "true" festzulegen.</span><span class="sxs-lookup"><span data-stu-id="bca38-118">Follow the procedure later in this section to set these parameters to True.</span></span> 

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="bca38-119">So migrieren Sie Adressbuch angepasste Normalisierungsregeln</span><span class="sxs-lookup"><span data-stu-id="bca38-119">To migrate Address Book customized normalization rules</span></span>

1. <span data-ttu-id="bca38-120">Suchen Sie die Datei "Company_Phone_Number_Normalization_Rules. txt" im Stammverzeichnis des freigegebenen Ordners "Adressbuch", und kopieren Sie Sie in den Stammordner des freigegebenen Adressbuch Ordners in Ihrem Skype for Business Server 2019-Pilot Pool.</span><span class="sxs-lookup"><span data-stu-id="bca38-120">Find the Company_Phone_Number_Normalization_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Skype for Business Server 2019 pilot pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bca38-121">Das Beispiel für die Normalisierungsregeln für das Adressbuch wurde im Dateiverzeichnis der ABS-Webkomponente installiert.</span><span class="sxs-lookup"><span data-stu-id="bca38-121">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="bca38-122">Der Pfad ist **$installedDriveLetter: \Programme\Microsoft Skype for Business Server 2019 \ Web Components\Address Adress Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules. txt**.</span><span class="sxs-lookup"><span data-stu-id="bca38-122">The path is **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span></span> <span data-ttu-id="bca38-123">Diese Datei kann als **Company_Phone_Number_Normalization_Rules. txt** in das Stammverzeichnis des freigegebenen Ordners des Adressbuchs kopiert und umbenannt werden.</span><span class="sxs-lookup"><span data-stu-id="bca38-123">This file can be copied and renamed as **Company_Phone_Number_Normalization_Rules.txt** to the address book shared folder's root directory.</span></span> <span data-ttu-id="bca38-124">Beispielsweise ist das in **$serverX**freigegebene Adressbuch der Pfad ähnlich wie: \*\* \\$serverX \SkypeForBusiness-FileShare\2-Webservices-1\ABFiles\*\*.</span><span class="sxs-lookup"><span data-stu-id="bca38-124">For example, the address book shared in **$serverX**, the path will be similar to: **\\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**.</span></span> 

2. <span data-ttu-id="bca38-125">Verwenden Sie einen Text-Editor wie Editor, um die Datei "Company_Phone_Number_Normalization_Rules. txt" zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="bca38-125">Use a text editor, such as Notepad, to open the Company_Phone_Number_Normalization_Rules.txt file.</span></span>

3. <span data-ttu-id="bca38-126">Bestimmte Arten von Einträgen funktionieren in Skype for Business Server 2019 nicht ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="bca38-126">Certain types of entries will not work correctly in Skype for Business Server 2019.</span></span> <span data-ttu-id="bca38-127">Durchsuchen Sie die Datei nach den in diesem Schritt beschriebenen Arten von Einträgen, bearbeiten Sie Sie nach Bedarf, und speichern Sie die Änderungen im freigegebenen Ordner des Adressbuchs in Ihrem Pilot Pool.</span><span class="sxs-lookup"><span data-stu-id="bca38-127">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>

    <span data-ttu-id="bca38-128">Zeichenfolgen, die erforderliche leer-oder Interpunktionszeichen enthalten, führen zu Normalisierungsregeln, da diese Zeichen aus der Zeichenfolge entfernt werden, die für die Normalisierungsregeln eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="bca38-128">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="bca38-129">Wenn Zeichenfolgen vorhanden sind, die die erforderlichen Leerzeichen oder Interpunktionszeichen enthalten, müssen Sie die Zeichenfolgen ändern.</span><span class="sxs-lookup"><span data-stu-id="bca38-129">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="bca38-130">Die folgende Zeichenfolge würde beispielsweise dazu führen, dass die Normalisierungsregel fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="bca38-130">For example, the following string would cause the normalization rule to fail:</span></span>

   ```
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    <span data-ttu-id="bca38-131">Die folgende Zeichenfolge würde nicht dazu führen, dass die Normalisierungsregel fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="bca38-131">The following string would not cause the normalization rule to fail:</span></span>

   ```
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="bca38-132">So setzen Sie UseNormalizationRules und IgnoreGenericRules auf "true"</span><span class="sxs-lookup"><span data-stu-id="bca38-132">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1. <span data-ttu-id="bca38-133">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype for Business Server 2019**, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="bca38-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="bca38-134">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="bca38-134">Do one of the following:</span></span>

   - <span data-ttu-id="bca38-135">Wenn Ihre Bereitstellung nur Skype for Business Server 2019 umfasst, führen Sie das folgende Cmdlet auf globaler Ebene aus, um die Werte für **UseNormalizationRules** und **IgnoreGenericRules** auf "true" zu ändern:</span><span class="sxs-lookup"><span data-stu-id="bca38-135">If your deployment includes only Skype for Business Server 2019, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span> 

   ```
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - <span data-ttu-id="bca38-136">Wenn Ihre Bereitstellung eine Kombination aus Skype for Business Server 2019 und einer Legacy Installation umfasst, führen Sie das folgende Cmdlet aus, und weisen Sie es jedem Skype for Business Server 2019-Pool in der Topologie zu:</span><span class="sxs-lookup"><span data-stu-id="bca38-136">If your deployment includes a combination of Skype for Business Server 2019 and a legacy install, run the following cmdlet and assign it to each Skype for Business Server 2019 pool in the topology:</span></span>

   ```
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. <span data-ttu-id="bca38-137">Warten Sie, bis die Replikation des zentralen Verwaltungsspeichers in allen Pools ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bca38-137">Wait for Central Management store replication to occur on all pools.</span></span>

4. <span data-ttu-id="bca38-138">Ändern Sie die Regeldatei für die Telefon Normalisierung, "Company_Phone_Number_Normalization_Rules. txt", für Ihre Bereitstellung, um den Inhalt zu löschen.</span><span class="sxs-lookup"><span data-stu-id="bca38-138">Modify the phone normalization rules file, "Company_Phone_Number_Normalization_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="bca38-139">Die Datei befindet sich auf der Dateifreigabe jedes Skype for Business Server 2019-Pools.</span><span class="sxs-lookup"><span data-stu-id="bca38-139">The file is on the file share of each Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="bca38-140">Wenn die Datei nicht vorhanden ist, erstellen Sie eine leere Datei mit dem Namen "Company_Phone_Number_Normalization_Rules. txt".</span><span class="sxs-lookup"><span data-stu-id="bca38-140">If the file is not present, then create an empty file named "Company_Phone_Number_Normalization_Rules.txt".</span></span>

5. <span data-ttu-id="bca38-141">Warten Sie einige Minuten, bis alle Front-End-Pools die neuen Dateien gelesen haben.</span><span class="sxs-lookup"><span data-stu-id="bca38-141">Wait several minutes for all Front End pools to read the new files.</span></span>

6. <span data-ttu-id="bca38-142">Führen Sie das folgende Cmdlet für jeden Skype for Business Server 2019-Pool in Ihrer Bereitstellung aus:</span><span class="sxs-lookup"><span data-stu-id="bca38-142">Run the following cmdlet on each Skype for Business Server 2019 pool in your deployment:</span></span>

   ```
   Update-CsAddressBook
   ```


