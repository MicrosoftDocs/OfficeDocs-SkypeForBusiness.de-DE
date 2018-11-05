---
title: 'Lync Server 2013: Windows PowerShell und Lync Server-Verwaltungstools'
TOCTitle: Windows PowerShell und Lync Server 2013-Verwaltungstools
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59679132
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Windows PowerShell und Lync Server 2013-Verwaltungstools

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

In Microsoft Lync Server 2013 werden Verwaltungstools über Windows PowerShell implementiert. Windows PowerShell umfasst eine Befehlszeilenumgebung, produktspezifische Befehle und eine vollständige Skriptsprache. Lync Server 2013-Tools, die über Windows PowerShell implementiert werden, umfassen die folgenden:

  - **Topologie-Generator**: Sie verwenden Topologie-Generator zum Erstellen, Anpassen und Veröffentlichen Ihrer geplanten Topologie, die zudem validiert wird, bevor Sie Serverinstallationen beginnen. Einzelne Server, auf denen Lync Server 2013 installiert wird, lesen die veröffentlichte Topologie im Rahmen des Installationsprozesses und das Installationsprogramm stellt den Server gemäß Festlegung in der Topologie bereit. Nach dem Setup werden Konfigurationsinformationen automatisch an alle Server repliziert. Komponenten können Ihrer Bereitstellung nur mit dem Topologie-Generator hinzugefügt werden.

  - **Lync Server-Verwaltungsshell**: Sie können Lync Server-Verwaltungsshell für die vollständige Befehlszeilenverwaltung Ihrer Bereitstellung verwenden.

  - **Lync Server-Systemsteuerung**: Sie können die Systemsteuerung für Microsoft Lync Server 2013-Benutzeroberfläche verwenden, um die am häufigsten ausgeführten Aufgaben in Ihrer Bereitstellung zu verwalten.

Diese Tools verwenden Windows PowerShell-cmdlets für die Verwaltung Ihrer Bereitstellung, darunter fast 550 produktspezifische cmdlets. Die in Lync Server 2013 enthaltenen Sicherheits-cmdlets werden primäre für die Verwaltung der Authentifizierung sowie von Benutzerrechten und Berechtigungen verwendet. Für die Verwaltung der Authentifizierung sind vielfältige cmdlets verfügbar, darunter cmdlets für die Zertifikat- und PIN-Authentifizierung. Darüber hinaus können Sie mit einer Reihe von cmdlets die neue rollenbasierte Zugriffssteuerungsfunktion (RBAC) verwenden, um die administrative Steuerung von Lync Server 2013 zu delegieren. Ausführliche Informationen zu den Lync Server-cmdlets finden Sie in der Betriebsdokumentation unter [Lync Server-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md). Einzelheiten zur Verwendung von Topologie-Generator und Systemsteuerung für Lync Server 2013 zur Verwaltung Ihrer Bereitstellung finden Sie in der Betriebsdokumentation unter [Lync Server 2013-Systemsteuerung](https://technet.microsoft.com/de-de/library/gg133224\(v=ocs.15\)).

Die Skriptsicherheitsfunktionen für Windows PowerShell sind speziell entwickelt, um einige der skriptrelevanten Sicherheitsprobleme älterer Technologien wie Microsoft Visual Basic Scripting Edition (VBScript) zu vermeiden. Die Windows PowerShell-Sicherheitsfunktionen sollen eine Umgebung erstellen, in der Benutzer nicht einfach oder unwissentlich Skripte ausführen können. Standardmäßig sind Windows PowerShell-Sicherheitsfunktionen aktiviert. Sie können den Status dieser Sicherheitsfunktionen ändern, um Ihre Skripterstellungsanforderungen und verschiedene Sicherheitsziele zu erfüllen. Das heißt nicht, dass die Shell die Ausführung von Skripts unmöglich macht, sondern es heißt, dass die Shell – standardmäßig – Benutzern die Ausführung von Skripts erschwert, ohne dass sie es bemerken. Ausführliche Informationen finden Sie unter Windows PowerShell-Skriptsicherheit unter [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145).

