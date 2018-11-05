---
title: Migrieren eines Adressbuchs
TOCTitle: Migrieren eines Adressbuchs
ms:assetid: b6e000ce-8b2e-460c-8a8b-000254b9d778
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205198(v=OCS.15)
ms:contentKeyID: 49295171
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrieren eines Adressbuchs

 

_**Letztes Änderungsdatum des Themas:** 2012-10-02_

**So migrieren Sie angepasste Normalisierungsregeln für Adressbücher**

1.  Suchen Sie die Datei **Company\_Phone\_Number\_Normalization\_Rules.txt** im Stamm des freigegebenen Adressbuchordners heraus, und kopieren Sie sie in den Stamm des freigegebenen Adressbuchordners im Lync Server 2013-Pilotpool.
    

    > [!NOTE]
    > Die Beispiele für die Normalisierungsregeln für Adressbücher wurden in Ihrem ABS Web-Komponentendateiverzeichnis installiert. Der Pfad lautet <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>. Diese Datei kann in <STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;umbenannt und in das Stammverzeichnis des freigegebenen Adressbuchordners kopiert werden. Der Pfad für das in <STRONG>$serverX</STRONG> freigegebene Adressbuch wird zum Beispiel ähnlich aussehen wie <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.



2.  Öffnen Sie die Datei "Company\_Phone\_Number\_Normalization\_Rules.txt" in einem Text-Editor, z. B. Editor.

3.  Bestimmte Arten von Einträgen funktionieren in Lync Server 2013 nicht ordnungsgemäß. Durchsuchen Sie die Datei nach den hier beschriebenen Typen von Einträgen, bearbeiten Sie die Einträge entsprechend, und speichern Sie die Änderungen im freigegebenen Adressbuchordner im Pilotpool.
    
    Zeichenfolgen, die erforderliche Leerzeichen oder Satzzeichen enthalten, können Fehler bei der Ausführung der Normalisierungsregeln verursachen, weil diese Zeichen aus den Zeichenfolgen, die in die Normalisierungsregeln eingelesen werden, entfernt werden. Wenn Sie Zeichenfolgen mit erforderlichen Leerzeichen oder Satzzeichen haben, müssen Sie diese Zeichenfolgen bearbeiten. Beispielsweise würde die folgende Zeichenfolge einen Fehler bei der Normalisierungsregel verursachen:
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    Mit der folgenden Zeichenfolge würde die Normalisierungsregel fehlerfrei ausgeführt werden:
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

