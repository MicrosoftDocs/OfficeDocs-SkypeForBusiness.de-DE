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
ms.openlocfilehash: e2c904a122f781da08c92c6b1123cfeb1944dd2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765273"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a><span data-ttu-id="7e10e-102">Migrieren des Adressbuchs</span><span class="sxs-lookup"><span data-stu-id="7e10e-102">Migrate Address Book</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e10e-103">_**Letztes Änderungsdatum des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="7e10e-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="7e10e-104">**So migrieren Sie Adressbuch angepasste Normalisierungsregeln**</span><span class="sxs-lookup"><span data-stu-id="7e10e-104">**To migrate Address Book customized normalization rules**</span></span>

1.  <span data-ttu-id="7e10e-105">Suchen Sie die\_Datei\_"\_\_Rules. txt" der Firmentelefonnummer im Stammverzeichnis des freigegebenen Adressbuch Ordners, und kopieren Sie Sie in den Stammordner des freigegebenen Adressbuch Ordners in Ihrem lync Server 2013-Pilot Pool.</span><span class="sxs-lookup"><span data-stu-id="7e10e-105">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7e10e-106">Das Beispiel für die Normalisierungsregeln für das Adressbuch wurde im Dateiverzeichnis der ABS-Webkomponente installiert.</span><span class="sxs-lookup"><span data-stu-id="7e10e-106">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="7e10e-107">Der Pfad ist <STRONG>$installedDriveLetter: \Programme\Microsoft lync Server 2013 \ Web Components\Address Adress Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules. txt</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="7e10e-107">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="7e10e-108">Diese Datei kann als &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules. txt</STRONG> &nbsp;in das Stammverzeichnis des freigegebenen Ordners des Adressbuchs kopiert und umbenannt werden.</span><span class="sxs-lookup"><span data-stu-id="7e10e-108">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="7e10e-109">Beispielsweise ist das in <STRONG>$serverX</STRONG>freigegebene&nbsp;Adressbuch der Pfad ähnlich wie: <STRONG> \\$serverX \LyncFileShare\2-Webservices-1\ABFiles</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="7e10e-109">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="7e10e-110">Verwenden Sie einen Text-Editor wie Editor, um die Datei für\_die\_\_normalisierungs\_Regeln für Firmentelefone zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7e10e-110">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="7e10e-111">Bestimmte Typen von Einträgen funktionieren in lync Server 2013 nicht ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="7e10e-111">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="7e10e-112">Durchsuchen Sie die Datei nach den in diesem Schritt beschriebenen Arten von Einträgen, bearbeiten Sie Sie nach Bedarf, und speichern Sie die Änderungen im freigegebenen Ordner des Adressbuchs in Ihrem Pilot Pool.</span><span class="sxs-lookup"><span data-stu-id="7e10e-112">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="7e10e-113">Zeichenfolgen, die erforderliche leer-oder Interpunktionszeichen enthalten, führen zu Normalisierungsregeln, da diese Zeichen aus der Zeichenfolge entfernt werden, die für die Normalisierungsregeln eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="7e10e-113">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="7e10e-114">Wenn Zeichenfolgen vorhanden sind, die die erforderlichen Leerzeichen oder Interpunktionszeichen enthalten, müssen Sie die Zeichenfolgen ändern.</span><span class="sxs-lookup"><span data-stu-id="7e10e-114">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="7e10e-115">Die folgende Zeichenfolge würde beispielsweise dazu führen, dass die Normalisierungsregel fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="7e10e-115">For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="7e10e-116">Die folgende Zeichenfolge würde nicht dazu führen, dass die Normalisierungsregel fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="7e10e-116">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

