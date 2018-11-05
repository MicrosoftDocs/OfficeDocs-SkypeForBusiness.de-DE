---
title: Voraussetzungen hinsichtlich Gruppenmitgliedschaften und Benutzerberechtigungen für Best Practices Analyzer
TOCTitle: Voraussetzungen hinsichtlich Gruppenmitgliedschaften und Benutzerberechtigungen für Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg591354(v=OCS.15)
ms:contentKeyID: 49295950
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Voraussetzungen hinsichtlich Gruppenmitgliedschaften und Benutzerberechtigungen für Best Practices Analyzer

 

_**Letztes Änderungsdatum des Themas:** 2012-10-21_

Damit Best Practices Analyzer fehlerfrei ausgeführt werden kann, muss das Benutzerkonto, unter dem Sie sich anmelden, ein Mitglied der Gruppe **Administratoren** auf dem lokalen Computer sein. Für das Scannen der Umgebung muss das Benutzerkonto außerdem ein Mitglied der folgenden Gruppen sein:

  - **Domänen-Admins**   Zum Aufzählen von Informationen für Active Directory-Domänendienste (Active Directory Domain Services, AD\&nbsp;DS) und zum Aufrufen der WMI-Anbieter (Windows Management Instrumentation, Windows-Verwaltungsinstrumentation) auf Domänencontrollern und globalen Katalogservern.

  - **Administratoren**   Auf jedem internen Lync Server 2013-Computer und jedem Edgeserver zum Aufrufen der WMI-Anbieter und Zugreifen auf die Registrierung erforderlich.

  - **RTCUniversalReadOnlyAdmins**   Vollzugriff oder delegierte Leseberechtigung für Lync Server 2013-Administratoren.

  - **Exchange-Administrator mit Leserechten**   Vollzugriff oder delegierter Zugriff für Exchange-Administratoren mit Leserechten in der Microsoft\&nbsp;Exchange-Organisation.

Wenn Ihr Benutzerkonto nicht über ausreichende Benutzerrechte verfügt, haben Sie zwei Möglichkeiten:

  - Geben Sie an der Eingabeaufforderung den Befehl **runas** ein, um das Tool unter einem anderen Konto mit ausreichenden Benutzerrechten auszuführen. Die Syntax lautet wie folgt:
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - Legen Sie auf der Seite **Mit Active Directory verbinden** die Anmeldeinformationen für die Konten fest, die Sie für die Ausführung von Best Practices Analyzer verwenden wollen. Klicken Sie auf **Erweiterte Anmeldeoptionen anzeigen**. Sie können drei Konten eingeben: eines zum Herstellen der Verbindung zu Active Directory-Domänendienste, eines zum Herstellen der Verbindung mit Lync Server 2013-Edgeservern und eines zum Herstellen der Verbindung mit den Exchange-Servern. Wenn Sie keines dieser Konten angeben, wird das Benutzerkonto verwendet, das Sie zum Anmelden bei und Ausführen von Best Practices Analyzer verwendet haben.

