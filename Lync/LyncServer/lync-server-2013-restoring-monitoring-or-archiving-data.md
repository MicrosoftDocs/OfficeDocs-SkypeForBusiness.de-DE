---
title: Wiederherstellen von Überwachungs- oder Archivierungsdaten
TOCTitle: Wiederherstellen von Überwachungs- oder Archivierungsdaten
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh202175(v=OCS.15)
ms:contentKeyID: 52056349
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Wiederherstellen von Überwachungs- oder Archivierungsdaten

 

_**Letztes Änderungsdatum des Themas:** 2013-02-18_

Das Wiederherstellen von Überwachungs- und Archivierungsdaten ist nicht erforderlich, um Lync Server nach einem Ausfall wieder einsatzbereit zu machen. Wenn Überwachungs- und Archivierungsdaten allerdings für Ihre Organisation von entscheidender Bedeutung sind, empfiehlt es sich, die Daten nach dem Neuerstellen der Datenbanken wiederherzustellen.

Im folgenden Verfahren wird beschrieben, wie Sie mithilfe von SQL Server Management Studio Archivierungs- oder Überwachungsdaten wiederherstellen.

## So stellen Sie Überwachungs- oder Archivierungsdaten aus einer Sicherungsdatei wieder her

1.  Melden Sie sich auf dem wiederherzustellenden Server als Mitglied der Administratorengruppe auf dem lokalen Computer oder einer Gruppe mit gleichwertigen Benutzerrechten an.

2.  Öffnen Sie SQL Server Management Studio: Klicken Sie im Startmenü auf **Alle Programme**, dann auf **Microsoft SQL Server 2012** oder **Microsoft SQL Server 2008** und anschließend auf **SQL Server Management Studio**.

3.  Stellen Sie unter **Verbindung mit Server herstellen** eine Verbindung zur SQL Server-Instanz her, indem Sie mindestens den Namen des Servers und die Authentifizierungsinformationen angeben.

4.  Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf **Datenbanken**, und klicken Sie dann auf **Datenbank wiederherstellen**.

5.  Klicken Sie unter **Seite auswählen** auf **Allgemein**, und wählen Sie dann im Feld **In Datenbank** den Datenbanknamen wie folgt aus:
    
      - Wählen Sie für eine Archivierungsdatenbank**LcsLog** aus.
    
      - Wählen Sie für eine Datenbank mit Kommunikationsdatensätzen **LcsCDR** aus.
    
      - Wählen Sie für eine QoE-Datenbank (Quality of Experience) **QoEMetrics** aus.

6.  Klicken Sie auf **Von Medium**.

7.  Klicken Sie unter **Wählen Sie die wiederherzustellenden Sicherungssätze aus** auf die Sicherungsdatei, und klicken Sie dann auf **Wiederherstellen**.

8.  Klicken Sie unter **Seite auswählen** auf **Optionen**, vergewissern Sie sich, dass der Datendateipfad und der Protokollpfad sich im richtigen Ordner befinden, und klicken Sie dann auf **OK**.

## So stellen Sie die Richtigkeit der Zugriffssteuerungslisten (Access Control Lists, ACLs) sicher

1.  Erweitern Sie **Datenbanken**, dann die Archivierungs- oder Überwachungsdatenbank, dann den Knoten **Sicherheit** und anschließend **Benutzer**.

2.  Stellen Sie sicher, dass die Domänengruppe **RTCComponentUniversalServices** als Benutzer vorhanden ist.

3.  Falls "RTCComponentUniversalServices" unter **Benutzer** nicht vorhanden sind, gehen Sie wie folgt vor:
    
    1.  Klicken Sie mit der rechten Maustaste auf **Benutzer**, und klicken Sie dann auf **Neuer Benutzer**.
    
    2.  Geben Sie in **Anmeldename** den fehlenden Gruppennamen "RTCComponentUniversalServices" ein.
    
    3.  Wählen Sie unter **Mitgliedschaft in Datenbankrollen** die Berechtigung **ServerRole** aus, und klicken Sie auf **OK**.
    

    > [!NOTE]
    > Sie müssen den Archivierungs- oder Überwachungsdienst nicht neu starten.


