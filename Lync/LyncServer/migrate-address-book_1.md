---
title: Migrieren des Adressbuchs
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: b6e000ce-8b2e-460c-8a8b-000254b9d778
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205198(v=OCS.15)
ms:contentKeyID: 48185218
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e68dbe4db6ee9ac6b9bd758b23a575089019f6c7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a><span data-ttu-id="63603-102">Migrieren des Adressbuchs</span><span class="sxs-lookup"><span data-stu-id="63603-102">Migrate Address Book</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63603-103">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="63603-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="63603-104">**So migrieren Sie angepasste Normalisierungsregeln für Adressbücher**</span><span class="sxs-lookup"><span data-stu-id="63603-104">**To migrate Address Book customized normalization rules**</span></span>

1.  <span data-ttu-id="63603-105">Suchen Sie die\_\_Datei "\_Normalisierung\_Rules. txt" im Stammverzeichnis des freigegebenen Adressbuch Ordners, und kopieren Sie Sie in den Stamm des freigegebenen Adressbuch Ordners in Ihrem lync Server 2013 Pilot-Pool.</span><span class="sxs-lookup"><span data-stu-id="63603-105">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="63603-106">Die Beispiele für die Normalisierungsregeln für Adressbücher wurden in Ihrem ABS Web-Komponentendateiverzeichnis installiert.</span><span class="sxs-lookup"><span data-stu-id="63603-106">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="63603-107">Der Pfad lautet <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="63603-107">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="63603-108">Diese Datei kann in das Stammverzeichnis des &nbsp;freigegebenen Adressbuch Ordners kopiert und in <STRONG>Company_Phone_Number_Normalization_Rules. txt</STRONG> &nbsp;umbenannt werden.</span><span class="sxs-lookup"><span data-stu-id="63603-108">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="63603-109">Beispielsweise ist das in <STRONG>$serverX</STRONG>freigegebene&nbsp;Adressbuch der Pfad ähnlich wie: <STRONG> \\$serverX \LyncFileShare\2-Webservices-1\ABFiles</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="63603-109">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="63603-110">Verwenden Sie einen Text-Editor wie Editor, um die Datei "\_Normalisierung\_\_\_Rules. txt" für Firmen Telefonnummern zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="63603-110">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="63603-111">Bestimmte Typen von Einträgen funktionieren in lync Server 2013 nicht ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="63603-111">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="63603-112">Durchsuchen Sie die Datei nach den hier beschriebenen Typen von Einträgen, bearbeiten Sie die Einträge entsprechend, und speichern Sie die Änderungen im freigegebenen Adressbuchordner im Pilotpool.</span><span class="sxs-lookup"><span data-stu-id="63603-112">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="63603-p103">Zeichenfolgen, die erforderliche Leerzeichen oder Satzzeichen enthalten, können Fehler bei der Ausführung der Normalisierungsregeln verursachen, weil diese Zeichen aus den Zeichenfolgen, die in die Normalisierungsregeln eingelesen werden, entfernt werden. Wenn Sie Zeichenfolgen mit erforderlichen Leerzeichen oder Satzzeichen haben, müssen Sie diese Zeichenfolgen bearbeiten. Beispielsweise würde die folgende Zeichenfolge einen Fehler bei der Normalisierungsregel verursachen:</span><span class="sxs-lookup"><span data-stu-id="63603-p103">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules. If you have strings that include required whitespace or punctuation, you need to modify the strings. For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="63603-116">Mit der folgenden Zeichenfolge würde die Normalisierungsregel fehlerfrei ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="63603-116">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

