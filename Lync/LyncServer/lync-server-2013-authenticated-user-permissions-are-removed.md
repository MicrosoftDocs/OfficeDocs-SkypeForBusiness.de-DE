---
title: 'Lync Server 2013: Entfernte Berechtigungen für authentifizierte Benutzer'
TOCTitle: Entfernte Berechtigungen für authentifizierte Benutzer
ms:assetid: 5fcd70a5-813a-4076-9bb6-5b0d47505038
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398425(v=OCS.15)
ms:contentKeyID: 49294158
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Entfernte Berechtigungen für authentifizierte Benutzer in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

In einer gesperrten Active Directory-Umgebung werden die Zugriffssteuerungseinträge (ACEs) authentifizierter Benutzer in den Active Directory-Standardcontainern (inklusive dem Benutzer-, Konfigurations- oder Systemcontainer) und den Organisationseinheiten entfernt, in denen Benutzer- und Computerobjekte gespeichert sind. Das Entfernen der Zugriffssteuerungseinträge authentifizierter Benutzer verhindert den Lesezugriff auf Active Directory-Informationen. Das Entfernen dieser Einträge verursacht jedoch Probleme in Lync Server 2013, da die Anwendung Leseberechtigungen für diese Container benötigt, damit seine Benutzer Domänenvorbereitung ausführen können.

In dieser Situation wird durch die Mitgliedschaft in der Gruppe "Domänen-Admins", die für das Ausführen der Domänenvorbereitung, die Serveraktivierung und das Erstellen von Pools erforderlich ist, kein Lesezugriff mehr auf die Active Directory-Informationen gewährt, die in den Standardcontainern gespeichert sind. Diese Lesezugriffsberechtigungen für verschiedene Container in der Gesamtstruktur-Stammdomäne müssen manuell gewährt werden, damit das erforderliche Verfahren zur Gesamtstrukturvorbereitung abgeschlossen werden kann.

Wenn Sie Benutzern das Ausführen von Domänenvorbereitung und Serveraktivierung und das Erstellen von Pools für Stammdomänen ermöglichen, die sich nicht in einer Gesamtstruktur befinden, können Sie folgende Schritte ausführen:

  - Verwenden Sie ein Konto, das Mitglied der Gruppe "Organisations-Admins" ist, um die Domänenvorbereitung auszuführen.

  - Verwenden Sie ein Konto, das Mitglied der Gruppe "Domänen-Admins" ist, und gewähren Sie diesem Konto Lesezugriffsberechtigungen für jeden der folgenden Container in der Gesamtstruktur-Stammdomäne:
    
      - Domäne
    
      - Konfiguration oder System

Wenn Sie kein Konto verwenden möchten, das Mitglied der Gruppe "Organisations-Admins" ist, um die Domänenvorbereitung oder andere Setupaufgaben durchzuführen, gewähren Sie dem Konto, das Sie verwenden möchten, explizit Lesezugriff auf die relevanten Container im Gesamtstrukturstamm.

## So gewähren Sie Benutzern Lesezugriffsberechtigungen für Container in der Gesamtstruktur-Stammdomäne

1.  Melden Sie sich an dem Computer, der Mitglied der Gesamtstruktur-Stammdomäne ist, mit einem Konto an, das Mitglied der Gruppe "Domänen-Admins" für die Gesamtstruktur-Stammdomäne ist.

2.  Führen Sie "adsiedit.msc" für die Gesamtstruktur-Stammdomäne aus.
    
    Wenn die Zugriffssteuerungseinträge authentifizierter Benutzer aus dem Domänen-, Konfigurations- oder Systemcontainer entfernt wurden, müssen Sie für den Container Leseberechtigungen gewähren. Dies ist in den folgenden Schritten beschrieben.

3.  Klicken Sie mit der rechten Maustaste auf den Container, und klicken Sie auf **Eigenschaften** .

4.  Klicken Sie auf die Registerkarte **Sicherheit** .

5.  Klicken Sie auf **Erweitert** .

6.  Klicken Sie auf der Registerkarte **Berechtigungen** auf **Hinzufügen** .

7.  Geben Sie den Namen des Benutzers bzw. der Gruppe, dem bzw. der die Berechtigungen zugewiesen werden sollen, im Format `domain\account name` ein, und klicken Sie dann auf **OK** .

8.  Klicken Sie auf der Registerkarte **Objekte** unter **Übernehmen für** auf **Nur dieses Objekt** .

9.  Aktivieren Sie unter **Berechtigungen** die folgenden Zugriffssteuerungseinträge, indem Sie in die Spalte **Zulassen** klicken: **Inhalt auflisten** , **Alle Eigenschaften lesen** und **Berechtigungen lesen** .

10. Klicken Sie zweimal auf **OK** .

11. Wiederholen Sie diese Schritte für alle in Schritt 2 aufgelisteten relevanten Container.

