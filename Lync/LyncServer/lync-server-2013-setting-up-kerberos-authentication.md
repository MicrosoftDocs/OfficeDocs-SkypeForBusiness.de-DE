---
title: 'Lync Server 2013: Einrichten der Kerberos-Authentifizierung'
TOCTitle: Einrichten der Kerberos-Authentifizierung
ms:assetid: dd8009ef-6265-4cc0-b2c7-e474cd1f4b09
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398976(v=OCS.15)
ms:contentKeyID: 49295629
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Einrichten der Kerberos-Authentifizierung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Lync Server 2013 unterstützt NTLM- und Kerberos-Authentifizierung für die Webdienste. Office Communications Server 2007 und Office Communications Server 2007 R2 verwendeten standardmäßig die Benutzerkonten "RTCComponentService" und "RTCService" als Benutzerkonten zum Ausführen der Webdienste-Anwendungspools. So kann den Benutzerkonten ein Dienstprinzipalname zugeordnet werden, der als Authentifizierungsprinzipal fungieren kann. Lync Server verwendet "NetworkService" zum Ausführen der Webdienste, und "NetworkService" können keine Dienstprinzipalnamen zugewiesen werden.

Bei nicht vorhandenen Active Directory-Objekten nutzt Lync Server-Systemsteuerung zur Speicherung der Dienstprinzipalnamen ersatzweise Computerkontoobjekte. Die Computerkontoobjekte können die Dienstprinzipalnamen enthalten und unterliegen keinem Kennwortablauf, was bei der Verwendung von Benutzerkonten in früheren Versionen ein Problem darstellte.

Sie verwenden Windows PowerShell-Cmdlets, um die Computerobjekte zur Bereitstellung der Kerberos-Authentifizierung zu konfigurieren.

## In diesem Abschnitt

  - [Voraussetzungen zur Aktivierung der Kerberos-Authentifizierung in Lync Server 2013](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [Erstellen eines Kerberos-Authentifizierungskontos in Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [Zuweisen eines Kerberos-Authentifizierungskontos zu einem Standort in Lync Server 2013](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [Einrichten von Kennwörtern für ein Kerberos-Authentifizierungskonto in Lync Server 2013](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [Hinzufügen der Kerberos-Authentifizierung zu weiteren Standorten in Lync Server 2013](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [Entfernen der Kerberos-Authentifizierung aus einem Standort in Lync Server 2013](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [Test und Berichterstellung zu Status und Zuweisung der Kerberos-Authentifizierung in Lync Server 2013](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

