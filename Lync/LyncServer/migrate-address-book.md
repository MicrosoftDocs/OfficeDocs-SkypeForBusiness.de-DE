---
title: Migrieren des Adressbuchs
TOCTitle: Migrieren des Adressbuchs
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205160(v=OCS.15)
ms:contentKeyID: 49295068
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrieren des Adressbuchs

 

_**Letztes Änderungsdatum des Themas:** 2012-10-09_

Das Lync Server 2010-Adressbuch wird generell zusammen mit der übrigen Topologie migriert. Es kann jedoch erforderlich sein, einige zusätzliche Schritte nach der Migration durchzuführen, wenn Sie in der Lync Server 2010-Umgebung folgende Anpassungen vorgenommen haben:

  - Sie haben die WMI-Eigenschaft **PartitionbyOU** so festgelegt, dass Adressbucheinträge nach Organisationseinheit (Organizational Unit, OU) zusammengefasst werden.

  - Sie haben die Normalisierungsregeln für das Adressbuch angepasst.

  - Sie haben den Standardwert für den **UseNormalizationRules**-Parameter in "False" geändert.

**Gruppierte Adressbucheinträge**

Wenn Sie die WMI-Eigenschaft **PartitionbyOU** auf "True" festgelegt haben, sodass für jede Organisationseinheit Adressbücher erstellt werden, müssen Sie das Active Directory-Attribut **msRTCSIP-GroupingId** für Benutzer und Kontakte festlegen, wenn Adressbucheinträge weiterhin gruppiert werden sollen. Das Gruppieren von Adressbucheinträgen ist vorteilhaft, um den Umfang von Adressbuchsuchen einzugrenzen. Zur Verwendung des **msRTCSIP-GroupingId** -Attributs schreiben Sie ein Skript zum Auffüllen des Attributs, wobei Sie allen Benutzern, die in einer Gruppe zusammengefasst werden sollen, den gleichen Wert zuweisen. Beispiel: Weisen Sie allen Benutzern in einer Organisationseinheit einen einzigen Wert zu.

**Adressbuch-Normalisierungsregeln**

Wenn Sie in der Lync Server 2010-Umgebung Normalisierungsregeln für Adressbücher angepasst haben, müssen Sie die angepassten Regeln in den Pilotpool migrieren. Haben Sie die Adressbuch-Normalisierungsregeln nicht angepasst, ist für den Adressbuchdienst nichts zu migrieren. Die Standardnormalisierungsregeln für Lync Server 2013 sind mit denen für Lync Server 2010 identisch. Führen Sie das später in diesem Abschnitt beschriebene Verfahren aus, um angepasste Normalisierungsregeln zu migrieren.


> [!NOTE]
> Wenn in Ihrer Organisation Remoteanrufsteuerung verwendet wird und Sie Normalisierungsregeln für Adressbücher angepasst haben, müssen Sie das Verfahren in diesem Thema ausführen, bevor Sie die Remoteanrufsteuerung nutzen können. Dazu müssen Sie Mitglied der Gruppe "RTCUniversalServerAdmins" sein oder gleichwertige Rechte innehaben.



**Festlegen von "UseNormalizationRules" auf "False"**

Wenn Sie den Wert für **UseNormalizationRules** auf "False" festlegen, sodass die Benutzer Telefonnummern gemäß Definition in Active Directory-Domänendienste verwenden können, ohne dass in Lync Server 2013 Normalisierungsregeln anzuwenden sind, müssen Sie die Parameter **UseNormalizationRules** und **IgnoreGenericRules** auf "True" festlegen. Führen Sie das später in diesem Abschnitt beschriebene Verfahren aus, um diese Parameter auf "True" festzulegen.

## So migrieren Sie angepasste Normalisierungsregeln für Adressbücher

1.  Suchen Sie die Datei **Company\_Phone\_Number\_Normalization\_Rules.txt** im Stamm des freigegebenen Adressbuchordners heraus, und kopieren Sie sie in den Stamm des freigegebenen Adressbuchordners im Lync Server 2013-Pilotpool.
    

    > [!NOTE]
    > Die Beispiele für die Normalisierungsregeln für Adressbücher wurden in Ihrem ABS Web-Komponentendateiverzeichnis installiert. Der Pfad lautet <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>. Diese Datei kann in <STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;umbenannt und in das Stammverzeichnis des freigegebenen Adressbuchordners kopiert werden. Der Pfad für das in <STRONG>$serverX</STRONG> freigegebene Adressbuch wird zum Beispiel ähnlich aussehen wie <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.



2.  Öffnen Sie die Datei "Company\_Phone\_Number\_Normalization\_Rules.txt" in einem Text-Editor, z. B. Editor.

3.  Bestimmte Arten von Einträgen funktionieren in Lync Server 2013 nicht ordnungsgemäß. Durchsuchen Sie die Datei nach den hier beschriebenen Typen von Einträgen, bearbeiten Sie die Einträge entsprechend, und speichern Sie die Änderungen im freigegebenen Adressbuchordner im Pilotpool.
    
    Zeichenfolgen, die erforderliche Leerzeichen oder Satzzeichen enthalten, können Fehler bei der Ausführung der Normalisierungsregeln verursachen, weil diese Zeichen aus den Zeichenfolgen, die in die Normalisierungsregeln eingelesen werden, entfernt werden. Wenn Sie Zeichenfolgen mit erforderlichen Leerzeichen oder Satzzeichen haben, müssen Sie diese Zeichenfolgen bearbeiten. Beispielsweise würde die folgende Zeichenfolge einen Fehler bei der Normalisierungsregel verursachen:
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    Mit der folgenden Zeichenfolge würde die Normalisierungsregel fehlerfrei ausgeführt werden:
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

## So legen Sie "UseNormalizationRules" und "IgnoreGenericRules" auf "True" fest

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie einen der folgenden Schritte aus:
    
      - Wenn die Bereitstellung nur Lync Server 2013 beinhaltet, führen Sie auf globaler Ebene das folgende Cmdlet aus, um die Werte für **UseNormalizationRules** und **IgnoreGenericRules** in "True" zu ändern:
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - Wenn Ihre Bereitstellung eine Kombination aus Lync Server 2013 und Lync Server 2010 oder Office Communications Server 2007 R2 umfasst, führen Sie das folgende Cmdlet aus, und weisen Sie es jedem Lync Server 2013-Pool in der Topologie zu:
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  Warten Sie, bis die Replikation für zentralen Verwaltungsspeicher in allen Pools erfolgt.

4.  Ändern Sie die Datei mit den Telefonnormalisierungsregeln ("Company\_Phone\_Number\_Normalization\_Rules.txt") für die Bereitstellung, sodass die Inhalte gelöscht werden. Die Datei befindet sich in der Dateifreigabe der einzelnen Lync Server 2013-Pools. Wenn die Datei nicht vorhanden ist, erstellen Sie eine leere Datei mit der Bezeichnung "Company\_Phone\_Number\_Normalization\_Rules.txt".

5.  Warten Sie einige Minuten, bis die neuen Dateien von allen Front-End-Pools gelesen wurden.

6.  Führen Sie das folgende Cmdlet auf allen Lync Server 2013-Pools in der Bereitstellung aus:
    
        Update-CsAddressBook

