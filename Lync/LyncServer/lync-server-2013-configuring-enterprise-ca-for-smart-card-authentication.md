---
title: Konfigurieren einer Zertifizierungsstelle im Unternehmen für die SmartCard-Authentifizierung
TOCTitle: Konfigurieren einer Zertifizierungsstelle im Unternehmen für die SmartCard-Authentifizierung
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn308571(v=OCS.15)
ms:contentKeyID: 56269339
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren einer Zertifizierungsstelle im Unternehmen für die SmartCard-Authentifizierung

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Im folgenden Abschnitt wird die Konfiguration einer Stammzertifizierungsstelle (Certification Authority, CA) im Unternehmen zum Unterstützen der SmartCard-Authentifizierung beschrieben. Informationen zum Installieren einer Stammzertifizierungsstelle im Unternehmen finden Sie in "Installieren einer Stammzertifizierungsstelle" unter [http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364).

## Konfigurieren einer Stammzertifizierungsstelle im Unternehmen zur Unterstützung der SmartCard-Authentifizierung

In den folgenden Schritten wird das Konfigurieren einer Stammzertifizierungsstelle im Unternehmen zur Unterstützung der SmartCard-Authentifizierung beschrieben:

1.  Melden Sie sich beim CA-Computer des Unternehmens mit dem Konto eines Domänenadministrators an.

2.  Starten Sie den System-Manager, und überprüfen Sie, ob die Zertifizierungsstellen-Webregistrierungsrolle installiert ist.

3.  Öffnen Sie im Menü **Verwaltungstools** die Verwaltungskonsole **Zertifizierungsstelle**.

4.  Erweitern Sie im Navigationsbereich den Knoten **Zertifizierungsstelle**.

5.  Klicken Sie mit der rechten Maustaste auf **Zertifikatvorlagen**, wählen Sie **Neu** aus, und wählen Sie dann **Auszustellende Zertifikatvorlage** aus.

6.  Wählen Sie **Enrollment Agent**, **SmartCard-Benutzer** und **SmartCard-Anmeldung** aus.

7.  Klicken Sie auf **OK**.

8.  Klicken Sie mit der rechten Maustaste auf **Zertifikatvorlagen**.

9.  Wählen Sie **Verwalten** aus.

10. Öffnen Sie die Eigenschaften der Vorlage "SmartCard-Benutzer".

11. Klicken Sie auf die Registerkarte **Sicherheit**.

12. Ändern Sie die Berechtigungen wie folgt:
    
      - Fügen Sie einzelne AD-Konten mit den Berechtigungen "Lesen/Registrieren (Zulassen)" hinzu, oder
    
      - Fügen Sie eine Sicherheitsgruppe hinzu, die SmartCard-Benutzer mit den Berechtigungen "Lesen/Registrieren (Zulassen)" enthält, hinzu, oder
    
      - Fügen Sie die Gruppe "Domänenbenutzer" mit den Berechtigungen "Lesen/Registrieren (Zulassen") hinzu.

