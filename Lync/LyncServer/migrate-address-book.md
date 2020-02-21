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
ms.openlocfilehash: 42d28161eab03d494dd5ebb3771c0879dd3dbb99
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210124"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>Migrieren des Adressbuchs

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-09_

Im Allgemeinen wird das lync Server 2010 Adressbuch zusammen mit der restlichen Topologie migriert. Möglicherweise müssen Sie jedoch einige Schritte nach der Migration durchführen, wenn Sie Folgendes in ihrer lync Server 2010 Umgebung angepasst haben:

  - Sie haben die WMI-Eigenschaft **PartitionbyOU** so festgelegt, dass Adressbucheinträge nach Organisationseinheit (Organizational Unit, OU) zusammengefasst werden.

  - Sie haben die Normalisierungsregeln für das Adressbuch angepasst.

  - Sie haben den Standardwert für den **UseNormalizationRules**-Parameter in "False" geändert.

**Gruppierte Adressbucheinträge**

Wenn Sie die WMI-Eigenschaft **PartitionbyOU** auf "True" festgelegt haben, sodass für jede Organisationseinheit Adressbücher erstellt werden, müssen Sie das Active Directory-Attribut **msRTCSIP-GroupingId** für Benutzer und Kontakte festlegen, wenn Adressbucheinträge weiterhin gruppiert werden sollen. Das Gruppieren von Adressbucheinträgen ist vorteilhaft, um den Umfang von Adressbuchsuchen einzugrenzen. Zur Verwendung des **msRTCSIP-GroupingId**-Attributs schreiben Sie ein Skript zum Auffüllen des Attributs, wobei Sie allen Benutzern, die in einer Gruppe zusammengefasst werden sollen, den gleichen Wert zuweisen. Beispiel: Weisen Sie allen Benutzern in einer Organisationseinheit einen einzigen Wert zu.

**Adressbuch-Normalisierungsregeln**

Wenn Sie die Regeln für die Adressbuch Normalisierung in ihrer lync Server 2010 Umgebung angepasst haben, müssen Sie die benutzerdefinierten Regeln in Ihren Pilot Pool migrieren. Haben Sie die Adressbuch-Normalisierungsregeln nicht angepasst, ist für den Adressbuchdienst nichts zu migrieren. Die Standard Normalisierungsregeln für lync Server 2013 entsprechen den Standardregeln für lync Server 2010. Führen Sie das später in diesem Abschnitt beschriebene Verfahren aus, um angepasste Normalisierungsregeln zu migrieren.

<div>


> [!NOTE]  
> Wenn in Ihrer Organisation Remoteanrufsteuerung verwendet wird und Sie Normalisierungsregeln für Adressbücher angepasst haben, müssen Sie das Verfahren in diesem Thema ausführen, bevor Sie die Remoteanrufsteuerung nutzen können. Dazu müssen Sie Mitglied der Gruppe "RTCUniversalServerAdmins" sein oder gleichwertige Rechte innehaben.



</div>

**Festlegen von "UseNormalizationRules" auf "False"**

Wenn Sie den Wert für **UseNormalizationRules** auf false festlegen, damit Benutzer Telefonnummern so verwenden können, wie Sie in Active Directory-Domänendienste definiert sind, ohne Normalisierungsregeln lync Server 2013 anzuwenden, müssen Sie die Parameter **UseNormalizationRules** und **IgnoreGenericRules** auf true festlegen. Führen Sie das später in diesem Abschnitt beschriebene Verfahren aus, um diese Parameter auf "True" festzulegen.

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a>So migrieren Sie angepasste Normalisierungsregeln für Adressbücher

1.  Suchen Sie die\_\_Datei "\_Normalisierung\_Rules. txt" im Stammverzeichnis des freigegebenen Adressbuch Ordners, und kopieren Sie Sie in den Stamm des freigegebenen Adressbuch Ordners in Ihrem lync Server 2013 Pilot-Pool.
    
    <div>
    

    > [!NOTE]  
    > Die Beispiele für die Normalisierungsregeln für Adressbücher wurden in Ihrem ABS Web-Komponentendateiverzeichnis installiert. Der Pfad lautet <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>. Diese Datei kann in das Stammverzeichnis des &nbsp;freigegebenen Adressbuch Ordners kopiert und in <STRONG>Company_Phone_Number_Normalization_Rules. txt</STRONG> &nbsp;umbenannt werden. Beispielsweise ist das in <STRONG>$serverX</STRONG>freigegebene&nbsp;Adressbuch der Pfad ähnlich wie: <STRONG> \\$serverX \LyncFileShare\2-Webservices-1\ABFiles</STRONG>.

    
    </div>

2.  Verwenden Sie einen Text-Editor wie Editor, um die Datei "\_Normalisierung\_\_\_Rules. txt" für Firmen Telefonnummern zu öffnen.

3.  Bestimmte Typen von Einträgen funktionieren in lync Server 2013 nicht ordnungsgemäß. Durchsuchen Sie die Datei nach den hier beschriebenen Typen von Einträgen, bearbeiten Sie die Einträge entsprechend, und speichern Sie die Änderungen im freigegebenen Adressbuchordner im Pilotpool.
    
    Zeichenfolgen, die erforderliche Leerzeichen oder Satzzeichen enthalten, können Fehler bei der Ausführung der Normalisierungsregeln verursachen, weil diese Zeichen aus den Zeichenfolgen, die in die Normalisierungsregeln eingelesen werden, entfernt werden. Wenn Sie Zeichenfolgen mit erforderlichen Leerzeichen oder Satzzeichen haben, müssen Sie diese Zeichenfolgen bearbeiten. Beispielsweise würde die folgende Zeichenfolge einen Fehler bei der Normalisierungsregel verursachen:
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    Mit der folgenden Zeichenfolge würde die Normalisierungsregel fehlerfrei ausgeführt werden:
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>So legen Sie "UseNormalizationRules" und "IgnoreGenericRules" auf "True" fest

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie einen der folgenden Schritte aus:
    
      - Wenn Ihre Bereitstellung nur lync Server 2013 enthält, führen Sie das folgende Cmdlet auf globaler Ebene aus, um die Werte für **UseNormalizationRules** und **IgnoreGenericRules** in true zu ändern:
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - Wenn Ihre Bereitstellung eine Kombination aus lync Server 2013 und lync Server 2010 oder Office Communications Server 2007 R2 enthält, führen Sie das folgende Cmdlet aus, und weisen Sie es jedem lync Server 2013 Pool in der Topologie zu:
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  Warten Sie, bis die Replikation des zentralen Verwaltungsspeichers in allen Pools ausgeführt wird.

4.  Ändern Sie die Regeldatei für die Normalisierung der Telefon\_\_Nummer\_, "Normalisierung\_Rules. txt" für Ihre Bereitstellung, um den Inhalt zu löschen. Die Datei befindet sich in der Dateifreigabe der einzelnen lync Server 2013 Pools. Wenn die Datei nicht vorhanden ist, erstellen Sie eine leere Datei mit dem Namen\_"\_Company\_Phone Number\_normalize Rules. txt".

5.  Warten Sie einige Minuten, bis alle Front-End-Pools die neuen Dateien gelesen haben.

6.  Führen Sie das folgende Cmdlet für jeden lync Server 2013 Pool in der Bereitstellung aus:
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

