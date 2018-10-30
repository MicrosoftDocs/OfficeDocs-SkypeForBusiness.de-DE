---
title: 'Lync Server 2013: Überprüfen der Schemareplikation'
TOCTitle: Überprüfen der Schemareplikation
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412822(v=OCS.15)
ms:contentKeyID: 49295075
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überprüfen der Active Directory-Schemareplikation in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-29_

Stellen Sie vor dem Ausführen der Gesamtstrukturvorbereitung manuell sicher, dass die Schemapartition repliziert wurde.

## So überprüfen Sie die Schemareplikation manuell

1.  Melden Sie sich bei einem Domänencontroller als Mitglied der Gruppe "Organisations-Admins" an.

2.  Öffnen Sie den ADSI-Editor, indem Sie nacheinander auf **Start** , **Verwaltung** und dann auf **ADSI-Editor** klicken.
    

    > [!TIP]
    > Alternativ dazu können Sie <STRONG>adsiedit.msc</STRONG> auch über die Befehlszeile ausführen.



3.  Klicken Sie in der MMC-Konsolenstruktur (Microsoft Management Console) auf **ADSI-Editor** , falls er nicht bereits ausgewählt ist.

4.  Klicken Sie im Menü **Aktion** auf **Verbinden mit** .

5.  Wählen Sie im Dialogfeld **Verbindungseinstellungen** unter **Bekannten Namenskontext auswählen** die Option **Schema** aus, und klicken Sie auf **OK** .

6.  Suchen Sie unter dem Schemacontainer nach "CN=ms-RTC-SIP-SchemaVersion". Wenn dieses Objekt vorhanden und der Wert des Attributs **rangeUpper** 1150 und der Wert des Attributs **rangeLower** 3 ist, wurde das Schema erfolgreich aktualisiert und repliziert. Wenn dieses Objekt nicht vorhanden ist oder die Werte der Attribute **rangeUpper** und **rangeLower** nicht diesen Werten entsprechen, wurde das Schema nicht geändert oder repliziert.

## Siehe auch

#### Aufgaben

[Ausführen der Active Directory-Schemavorbereitung in Lync Server 2013](lync-server-2013-running-schema-preparation.md)  

#### Konzepte

[Vorbereiten des Active Directory-Schemas in Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)

