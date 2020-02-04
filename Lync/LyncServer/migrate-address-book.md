---
title: Migrieren des Adressbuchs
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205160(v=OCS.15)
ms:contentKeyID: 48185064
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b678dea3e8ad7f05f82d28dfdd23ad9e45b38e92
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765283"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>Migrieren des Adressbuchs

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-09_

Im Allgemeinen wird das lync Server 2010-Adressbuch zusammen mit der restlichen Topologie migriert. Möglicherweise müssen Sie jedoch einige Schritte nach der Migration durchführen, wenn Sie die folgenden Schritte in ihrer lync Server 2010-Umgebung angepasst haben:

  - Legen Sie die WMI-Eigenschaft **PartitionbyOU** auf Gruppen Adressbucheinträge nach Organisationseinheit (Organizational Unit, OU).

  - Benutzerdefinierte Adressbuch-Normalisierungsregeln.

  - Der Standardwert für den **UseNormalizationRules** -Parameter wurde auf "false" geändert.

**Gruppierte Adressbucheinträge**

Wenn Sie die **PartitionbyOU** -WMI-Eigenschaft auf "true" festlegen, um Adressbücher für jede OU zu erstellen, müssen Sie das Active Directory-Attribut " **Attribut msRTCSIP-Gruppierung** " für Benutzer und Kontakte festlegen, wenn Sie die Gruppierung von Adressbucheinträgen fortsetzen möchten. Möglicherweise möchten Sie Adressbucheinträge gruppieren, um den Umfang der Adressbuchsuche zu begrenzen. Wenn Sie das **Attribut msRTCSIP-GROUPING-** Attribut verwenden möchten, schreiben Sie ein Skript zum Auffüllen des Attributs, und weisen Sie allen Benutzern, die Sie gruppieren möchten, denselben Wert zu. Weisen Sie beispielsweise allen Benutzern in einer OU einen einzelnen Wert zu.

**Regeln für die Normalisierung des Adressbuchs**

Wenn Sie in ihrer lync Server 2010-Umgebung Adressbuch-Normalisierungsregeln angepasst haben, müssen Sie die angepassten Regeln in Ihren Pilot Pool migrieren. Wenn Sie die Regeln für die Adressbuch Normalisierung nicht angepasst haben, müssen Sie für den Adressbuchdienst nichts migrieren. Die standardmäßigen Normalisierungsregeln für lync Server 2013 entsprechen den Standardregeln für lync Server 2010. Führen Sie die Schritte weiter unten in diesem Abschnitt aus, um angepasste Normalisierungsregeln zu migrieren.

<div>


> [!NOTE]  
> Wenn in Ihrer Organisation die Remoteanrufsteuerung verwendet wird und Sie die Regeln für die Adressbuch Normalisierung angepasst haben, müssen Sie das in diesem Thema beschriebene Verfahren ausführen, bevor Sie die Remoteanrufsteuerung verwenden können. Für das Verfahren ist die Mitgliedschaft in der RTCUniversalServerAdmins-Gruppe oder entsprechende Rechte erforderlich.



</div>

**UseNormalizationRules auf "false" festgelegt**

Wenn Sie den Wert für **UseNormalizationRules** auf "false" festlegen, damit Benutzer Telefonnummern verwenden können, wie Sie in Active Directory-Domänendiensten definiert sind, ohne dass lync Server 2013 Normalisierungsregeln anwenden, müssen Sie die **UseNormalizationRules** -und **IgnoreGenericRules** -Parameter auf true festlegen. Führen Sie die Schritte weiter unten in diesem Abschnitt aus, um diese Parameter auf "true" festzulegen.

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a>So migrieren Sie Adressbuch angepasste Normalisierungsregeln

1.  Suchen Sie die\_Datei\_"\_\_Rules. txt" der Firmentelefonnummer im Stammverzeichnis des freigegebenen Adressbuch Ordners, und kopieren Sie Sie in den Stammordner des freigegebenen Adressbuch Ordners in Ihrem lync Server 2013-Pilot Pool.
    
    <div>
    

    > [!NOTE]  
    > Das Beispiel für die Normalisierungsregeln für das Adressbuch wurde im Dateiverzeichnis der ABS-Webkomponente installiert. Der Pfad ist <STRONG>$installedDriveLetter: \Programme\Microsoft lync Server 2013 \ Web Components\Address Adress Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules. txt</STRONG>. Diese Datei kann als &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules. txt</STRONG> &nbsp;in das Stammverzeichnis des freigegebenen Ordners des Adressbuchs kopiert und umbenannt werden. Beispielsweise ist das in <STRONG>$serverX</STRONG>freigegebene&nbsp;Adressbuch der Pfad ähnlich wie: <STRONG> \\$serverX \LyncFileShare\2-Webservices-1\ABFiles</STRONG>.

    
    </div>

2.  Verwenden Sie einen Text-Editor wie Editor, um die Datei für\_die\_\_normalisierungs\_Regeln für Firmentelefone zu öffnen.

3.  Bestimmte Typen von Einträgen funktionieren in lync Server 2013 nicht ordnungsgemäß. Durchsuchen Sie die Datei nach den in diesem Schritt beschriebenen Arten von Einträgen, bearbeiten Sie Sie nach Bedarf, und speichern Sie die Änderungen im freigegebenen Ordner des Adressbuchs in Ihrem Pilot Pool.
    
    Zeichenfolgen, die erforderliche leer-oder Interpunktionszeichen enthalten, führen zu Normalisierungsregeln, da diese Zeichen aus der Zeichenfolge entfernt werden, die für die Normalisierungsregeln eingegeben wurde. Wenn Zeichenfolgen vorhanden sind, die die erforderlichen Leerzeichen oder Interpunktionszeichen enthalten, müssen Sie die Zeichenfolgen ändern. Die folgende Zeichenfolge würde beispielsweise dazu führen, dass die Normalisierungsregel fehlschlägt:
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    Die folgende Zeichenfolge würde nicht dazu führen, dass die Normalisierungsregel fehlschlägt:
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>So setzen Sie UseNormalizationRules und IgnoreGenericRules auf "true"

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie einen der folgenden Schritte aus:
    
      - Wenn Ihre Bereitstellung nur lync Server 2013 umfasst, führen Sie das folgende Cmdlet auf globaler Ebene aus, um die Werte für **UseNormalizationRules** und **IgnoreGenericRules** auf "true" zu ändern:
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - Wenn Ihre Bereitstellung eine Kombination aus lync Server 2013 und lync Server 2010 oder Office Communications Server 2007 R2 umfasst, führen Sie das folgende Cmdlet aus, und weisen Sie es jedem lync Server 2013-Pool in der Topologie zu:
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  Warten Sie, bis die Replikation des zentralen Verwaltungsspeichers in allen Pools ausgeführt wird.

4.  Ändern Sie die Regeldatei für Telefon Normalisierungsregeln\_,\_"\_Unternehmens-Telefonnummern-normalisierungs\_Regeln. txt", für Ihre Bereitstellung, um den Inhalt zu löschen. Die Datei befindet sich auf der Dateifreigabe der einzelnen lync Server 2013-Pools. Wenn die Datei nicht vorhanden ist, erstellen Sie eine leere Datei mit dem Namen\_"\_unter\_nehmens\_-Telefonnummern-Normalisierungsregeln. txt".

5.  Warten Sie einige Minuten, bis alle Front-End-Pools die neuen Dateien gelesen haben.

6.  Führen Sie das folgende Cmdlet für jeden lync Server 2013-Pool in Ihrer Bereitstellung aus:
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

