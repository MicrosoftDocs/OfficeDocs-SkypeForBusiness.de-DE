---
title: Konfigurieren der Besprechungseinladung
TOCTitle: Konfigurieren der Besprechungseinladung
ms:assetid: 7faa4797-0344-418b-9fa3-59dfb9c2baf7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398638(v=OCS.15)
ms:contentKeyID: 49294550
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der Besprechungseinladung

 

_**Letztes Änderungsdatum des Themas:** 2013-07-16_

Sie können die vom Onlinebesprechungs-Add-In für Lync 2013 gesendeten Besprechungseinladungen anpassen, indem Sie die folgenden optionalen Elemente in den Text der Besprechungseinladung aufnehmen:

  - **Das Logo Ihrer Organisation:** Fügen Sie einer Besprechungseinladung das Logo Ihrer Organisation hinzu, indem Sie die Option "Logo der URL" verwenden. Werden Besprechungseinladungen an Personen außerhalb Ihres Unternehmens gesendet, sollte sich die Bilddatei unter einer öffentlich zugänglichen URL befinden. Die unterstützten Bildformate sind GIF und JPG. Obwohl Lync Server 2013 die URL ohne Größeneinschränkung für das Bild speichert, empfehlen wir für die besten Ergebnisse eine maximale Bildgröße von 30 Pixel hoch mal 188 Pixel breit.

  - **Ein benutzerdefinierter Hilfe- oder Support-Link:** Fügen Sie eine URL für die Hilfe- oder Supportteam-Website Ihrer Organisation hinzu. Werden Besprechungseinladungen an Personen außerhalb Ihres Unternehmens gesendet, sollte die URL öffentlich zugänglich sein. Die maximale URL-Länge beträgt 1 KB.

  - **Haftungsausschluss:** Fügen Sie eine URL für rechtliche Hinweise oder einen Haftungsausschluss hinzu, die in allen Besprechungseinladungen angezeigt wird. Werden Besprechungseinladungen an Personen außerhalb Ihres Unternehmens gesendet, sollte die URL öffentlich zugänglich sein. Die maximale URL-Länge beträgt 1 KB.

  - **Benutzerdefinierte Fußzeile:** Fügen Sie Text hinzu, der in der Einladung als benutzerdefinierte Fußzeile angezeigt wird. Die maximale Länge des Texts beträgt 2 KB.

Sie können diese Optionen entweder über die Lync Server-Systemsteuerung oder die Lync Server-Verwaltungsshell konfigurieren.


**So passen Sie die Besprechungseinladung über die Lync Server-Systemsteuerung an**

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer des Netzwerks an, in dem Sie Lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Konferenzen**, und klicken Sie anschließend auf **Besprechungskonfiguration**.

4.  Klicken Sie auf der Seite **Besprechungskonfiguration** auf **Neu**, und führen Sie einen der folgenden Schritte aus:
    
      - Klicken Sie auf **Standortkonfiguration**, um eine Richtlinie auf Standortebene zu erstellen. Geben Sie im Suchfeld **Standort auswählen** einen Teil oder den gesamten Namen des Standorts ein, für den Sie Einstellungen für den Besprechungsbeitritt definieren möchten. Klicken Sie in der resultierenden Liste der Standorte auf den gewünschten Standort, und klicken Sie auf **OK**.
    
      - Klicken Sie auf **Poolkonfiguration**, um eine Richtlinie auf Poolebene zu erstellen. Geben Sie im Suchfeld **Dienst auswählen** einen Teil oder den gesamten Namen des Pooldiensts ein, für den Sie Einstellungen für den Besprechungsbeitritt definieren möchten. Klicken Sie in der resultierenden Liste der Dienste auf den gewünschten Pool, und klicken Sie auf **OK**.

5.  Führen Sie einen der folgenden Schritte aus:
    
      - Geben Sie im Feld **Logo-URL** die URL für das Logo Ihrer Organisation ein.
    
      - Geben Sie im Feld **Hilfe-URL** die URL für die Hilfe- oder Support-Website Ihrer Organisation ein.
    
      - Geben Sie im Feld **Rechtliche Hinweise** die URL für die rechtlichen Hinweise oder den Haftungsausschluss ein, die oder den Sie in den Besprechungseinladungen anzeigen möchten.
    
      - Geben Sie im Feld **Benutzerdefinierter Fußzeilentext** den gewünschten Text mit einer Länge von bis zu 2 KB ein.

**So passen Sie die Besprechungseinladung über die Lync Server-Verwaltungsshell an**

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet **New-CsMeetingConfiguration** oder **Set-CsMeetingConfiguration** aus, um die Optionen für die Besprechungseinladungen zu erstellen oder zu konfigurieren. Führen Sie beispielsweise Folgendes aus:
    
        New-CsMeetingConfiguration -Identity site:Redmond -EnableInviteCustomization $True -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

