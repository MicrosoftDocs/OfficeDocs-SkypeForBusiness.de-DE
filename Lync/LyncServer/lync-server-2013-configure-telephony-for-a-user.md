---
title: Konfigurieren von Telefonieoptionen für einen Benutzer
TOCTitle: Konfigurieren von Telefonieoptionen für einen Benutzer
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg520988(v=OCS.15)
ms:contentKeyID: 49293855
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Telefonieoptionen für einen Benutzer

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Telefonieeinstellungen sind einige der individuellen Einstellungen eines Benutzerkontos, die für den Benutzer in Lync Server-Systemsteuerung konfiguriert werden können (vorausgesetzt, der einzelne Benutzer wurde für Lync Server 2013 aktiviert und die Organisation unterstützt Telefonie).

Folgende Optionen gehören zu den Lync Server-Benutzertelefonieoptionen:

  - **Audio/Video deaktiviert**   Der Benutzer kann keine Anrufe mit Audio und Video tätigen.

  - **Nur PC zu PC**   Der Benutzer kann nur Audio- oder Videoanrufe von PC zu PC tätigen.

  - **Enterprise-VoIP**   Der Benutzer kann über die Lync Server 2013-Infrastruktur alle eingehenden und ausgehenden Anrufe routen. Außerdem kann der Benutzer Anrufe von PC zu PC tätigen.

  - **Remoteanrufsteuerung**   Der Benutzer kann mithilfe von Lync Server 2013 das herkömmliche Telefon steuern und außerdem Anrufe von PC zu PC tätigen.

Ausführliche Informationen zum Konfigurieren der Telefonie für eine Organisation finden Sie unter [Konfigurieren von Telefonieoptionen für einen Benutzer](lync-server-2013-configure-telephony-for-a-user.md) und [Bereitstellen von Enterprise-VoIP in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in der Bereitstellungsdokumentation.

## So konfigurieren Sie Telefonieoptionen für ein bestimmtes Benutzerkonto

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des gewünschten Benutzerkontos ein, und klicken Sie dann auf **Suchen**.

5.  Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie ändern möchten.

6.  Klicken Sie im Menü **Bearbeiten** auf **Ändern**.

7.  Führen Sie im Dialogfeld **Telefonie** die folgenden Schritte aus:
    
      - Klicken Sie zum Deaktivieren von Audio- und Videoanrufen für den Benutzer auf **Audio/Video deaktiviert**.
    
      - Wenn Sie für den Benutzer die Audiokommunikation von PC zu PC, jedoch nicht die Remoteanrufsteuerung oder Enterprise-VoIP aktivieren möchten, klicken Sie auf **Nur PC zu PC**. Geben Sie einen Wert für **Anschluss-URI** für das Telefon an, das der Benutzer für die Audiokommunikation von PC zu PC verwendet.
    
      - Klicken Sie auf **Enterprise-VoIP**, um die Telefonanrufe des Benutzers entsprechend der Dienstklassenrichtlinie über die Lync Server 2010-Infrastruktur weiterzuleiten, einschließlich der Audiokommunikation von PC zu PC. Geben Sie unter **Anschluss-URI** die Telefonnummer für Enterprise-VoIP an. Geben Sie unter **Richtlinie für Wähleinstellungen** und **VoIP-Richtlinie** die entsprechenden Richtlinien für den Benutzer an. Wählen Sie unter **Ortungsrichtlinie** das angemessene Standortprofil aus, um die Normalisierungsregeln für die Übersetzung der vom Benutzer gewählten Telefonnummern in das E.164-Format anzugeben.
    
      - Klicken Sie auf **Remoteanrufsteuerung**, um die Remoteanrufsteuerung zu aktivieren. Damit können Benutzer ihre herkömmliche Telefonleitung über Lync Server 2013 steuern, um Anrufe von PC zu PC oder von PC zu Telefon zu tätigen. Geben Sie unter **Anschluss-URI** die Telefonnummer für die Remoteanrufsteuerung an. Für die Anrufweiterleitung muss der Benutzer ein herkömmliches Telefon und eine Verbindung mit einer Nebenstellenanlage (Private Branch Exchange, PBX) besitzen.

## Siehe auch

#### Weitere Ressourcen

[Ändern der Eigenschaften von Benutzerkonten](lync-server-2013-modifying-user-account-properties.md)

