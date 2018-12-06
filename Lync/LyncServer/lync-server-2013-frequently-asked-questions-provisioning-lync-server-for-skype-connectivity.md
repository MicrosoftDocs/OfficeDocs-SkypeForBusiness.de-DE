---
title: 'Lync Server 2013: Häufig gestellte Fragen: Bereitstellen der Skype-Konnektivität für Lync Server'
TOCTitle: 'Häufig gestellte Fragen: Bereitstellen der Skype-Konnektivität für Lync Server'
ms:assetid: 4d1b2bfc-780b-4b8c-afd5-11c2e59203b5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn440172(v=OCS.15)
ms:contentKeyID: 59373604
ms.date: 12/28/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Häufig gestellte Fragen: Bereitstellen der Skype-Konnektivität für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-27_

**F: Welche Funktionen werden im Zusammenspiel zwischen Microsoft Lync und Skype unterstützt?**

**A:** Da Skype nun Teil der Microsoft-Produktfamilie ist, eröffnen sich neue Möglichkeiten für die Erweiterung von Unified Communications-Szenarien auf die Hunderte Millionen Menschen, die Skype verwenden. Diese Kombination ermöglicht es Lync-Kunden, mit Lieferanten, Kunden und Partnern in Verbindung zu treten und mit diesen zusammenzuarbeiten, wobei sie auf den Funktionsreichtum von Lync und die Reichweite von Skype aufsetzen können.

  - Chatnachrichten sowie Audio- und Videoanrufe – Kombinierte Audio- und Videoanrufe sowie Chatnachrichten zwischen Lync- und Skype-Benutzern

  - Freigabe von Anwesenheitsinformationen - Austausch von Anwesenheitsinformationen zwischen Kontakten im Partnerverbund

  - Einfache Verwaltung - Einstellungen und Steuerelemente zum Konfigurieren der Partnerverbundkommunikation in Übereinstimmung mit den Richtlinien und Standards Ihrer Organisation

**F: Welche Voraussetzungen muss ich für die Verbindung meiner Lync-Bereitstellung mit Skype erfüllen?**

**A:** Sie sind für die Skype-Konnektivität berechtigt, wenn Sie über Folgendes verfügen:

  - Lync Server (2010 oder 2013) plus Lync Server Standard-Clientzugriffslizenzen ("CALs", 2010 oder 2013) für die Benutzer und/oder die Geräte in Ihrer Organisation, die die Verbindung zu Skype herstellen werden. 

  - Lync Online (als eigenständige Lizenzen oder als Teil einer Office 365-Suite). Dieser Dienst ("pic.lync.com") kann jedoch nur für die Bereitstellung in Lync Server- und hybriden Lync Server- und Lync Online-Implementierungen verwendet werden. Die Bereitstellung von Lync Online PIC erfolgt in der Lync Online-Systemsteuerung (Lync Online Control Panel, LOCP).

**F: Wie müssen Lync-Endbenutzer vorgehen, um die Verbindung zu Skype-Kontakten herzustellen?**

**A:** Nachdem eine Domäne aktiviert und die Funktionen von einem Lync-Administrator in der Organisation aktiviert wurden, können Lync-Benutzer ihren Kontaktlisten im Lync-Client Skype-Kontakte hinzufügen.

**F: Wie müssen Skype-Endbenutzer vorgehen, um die Verbindung zu Lync-Kontakten herzustellen?**

**A:** Alle Skype-Benutzer, die die Verbindung zu einem Lync-Benutzer herstellen möchten, müssen über ein Microsoft-Konto verfügen, das mit ihrer Skype-ID verbunden ist und sich mit dem Microsoft-Konto anmelden. Dies kann im Skype-Client aktiviert werden.

**F: Steht der Partnerverbund mit Windows Live noch zur Verfügung?**

**A:** Anfang Oktober 2012 hat Microsoft begonnen, den Benutzern von Windows Live Messenger (WLM) beim Umstieg auf Skype zu helfen, und zwar in Anbetracht der Tatsache, dass WLM schließlich eingestellt werden soll. Lync wird den Partnerverbund mit WLM solange unterstützen, wie WLM auf dem Markt ist, es sind jedoch keine weiteren Windows-Live-Domänenaktivierungen mehr möglich. Der Umstieg von WLM-Benutzern wird mit Skype 6.0 für Mac und Windows (veröffentlicht am 25. Oktober 2012) möglich. In dieser Version können sich die Benutzer mit einem Microsoft-Konto anmelden (d. h. mit denselben Anmeldeinformationen wie in WLM). Nach der Anmeldung bei Skype werden die WLM-Buddylisten automatisch nach Skype übernommen, und die Benutzer können nun die Vorteile der erweiterten Kommunikationsmöglichkeiten Skype nutzen, wie Anrufe von Festnetz- und Mobiltelefonen, Bildschirmfreigabe, Gruppenanrufe mit Video und Unterstützung einer Vielzahl unterschiedlicher Geräte. Darüber hinaus folgen auch die Lync-Partnerverbundkontakte von WLM-Benutzern dem Umstieg auf Skype mit den restlichen Buddylisten, und Chatunterhaltungen zwischen Skype und Lync zwischen diesen Kontakten sind sofort möglich. Lync-Kunden müssen nichts tun, um den Fortbestand des Diensts zu gewährleisten.

**F: Steht der Partnerverbund mit Yahoo\! oder AOL noch zur Verfügung?**

**A:** Für Kunden von Lync und Office Communications Server wird der Partnerverbund mit Yahoo\! und AOL demnächst eingestellt. Die Fähigkeit von Microsoft, diese beiden Dienste bereitzustellen, war von der Unterstützung durch Yahoo\! und AOL abhängig, und die dieser Unterstützung zugrunde liegenden Vereinbarungen laufen demnächst aus. Sowohl für Yahoo\! als auch für AOL wird der Dienst bis Juni 2014 weiterhin bereitgestellt.

  - Yahoo\!: Der Dienst wird bis Juni 2014 weiterhin bereitgestellt, und Kunden benötigen weiterhin eine Microsoft Lync PIC USL (Benutzerabonnementlizenz für die Verbindung mit öffentlichen Instant Messaging-Diensten). Seit dem 1. September 2012 kann die PIC USL für neue Verträge oder die Erneuerung von Verträgen nicht mehr erworben werden. Kunden mit Lizenzen, die vor diesem Datum erworben wurden, können den Partnerverbund mit Yahoo\! bis entweder zum Einstellungsdatum des Diensts oder bis zum Ablaufdatum der Lizenz weiterhin nutzen. Kunden mit PIC-Lizenzen aus Verträgen, die über den 30. Juni 2014 hinaus gültig sind, erhalten eine anteilige Gutschrift für bereits geleistete Zahlungen, die über den 30. Juni 2014 hinausgehen.

  - AOL: Ab dem 30. Juni 2014 steht der Lync-Konnektivitätsdienst zur Herstellung der Verbindung zu Anbietern von öffentlichen Instant Messaging-Diensten nicht mehr zur Verfügung. Um das Ausmaß der Störungen bei den Kunden möglichst gering zu halten, wurde die Bereitstellung weiterer Kundendomänen bereits eingestellt. Bis zum 30. Juni 2014 müssen die Kunden nichts unternehmen, um die Kommunikation im Partnerverbund mit AIM fortzusetzen. Nach diesem Datum (oder für Kunden, die in der Zwischenzeit weitere Domänen bereitstellen möchten) steht ein Ersatzdienst direkt von AOL zur Verfügung. Weitere Informationen zu dem neuen Dienst von AOL finden Sie unter <http://aimenterprise.aol.com/pic.php> (mit diesem Link wird eine neue Seite auf AOL.com geöffnet). 

**F: Kann ich die Skype-Konnektivität testen, bevor ich Lync kaufe?**

**A:** Die Skype-Konnektivität wird nicht in Form eines Tests angeboten. Anstelle eines Testlaufs sollten sich Lync-Kunden mit qualifizierenden Lizenzen einfach bei dem Dienst anmelden, um ihn zu testen.

**F: Welche Informationen sind für die Bereitstellung erforderlich?**

**A:** Für die Übermittlung einer Bereitstellungsanforderung unter einer qualifizierenden Lizenz benötigen Sie Folgendes:

  - Die Microsoft-Vertragsnummer:
    
      - Microsoft-Volumenlizenz-Support: Nummer des Microsoft-Volumenlizenzvertrags
    
      - Microsoft Partner Network: Partner-ID der Unternehmenszentrale
    
      - Dienstanbieter-Lizenzvertrag: Ursprüngliche Beitrittsvertragsnummer
    
      - High Volume-Dienste: Produktregistrierungsnummer

  - Vollständig qualifizierte Domänennamen (FQDNs) für den Zugriffs-Edgedienst
    
      - Es ist ein FQDN für mindestens einen Zugriffs-Edgedienst erforderlich.
    
      - Wenn der Zugriffs-Edgedienst in Ihrer Organisation auf mehr als einem Server ausgeführt wird, geben Sie die FQDNs für jeden zusätzlichen Zugriffs-Edgedienst an. Wichtig: Wenn Sie schon früher einen FQDN für den Zugriffs-Edgedienst angegeben haben und diesen nun ändern möchten, kann die Durchführung der Änderung mehrere Tage in Anspruch nehmen und zu einer Dienstunterbrechung führen. Zur Vermeidung von Dienstunterbrechungen wird empfohlen, den zuvor für den Zugriffs-Edgedienst angegebenen FQDN beizubehalten.

  - SIP-Domäne/n (Session Initiation Protocol). Dies ist das Domänensuffix des SIP URI, den die Benutzer derzeit für Chatunterhaltungen verwenden. Wenn es in Ihrer Organisation mehr als eine SIP-Domäne gibt, geben Sie das Suffix jeder Domäne an, die für Chatnachrichten verwendet wird. Geben Sie beispielsweise für "Benutzer1@contoso.com" als SIP-Domäne "contoso.com" an, für "Benutzer1@example.fabrikam.com" geben Sie "example.fabrikam.com" als SIP-Domäne an.
    

    > [!NOTE]
    > Geben Sie nur das Domänensuffix der SIP-Domäne an. Geben Sie keine FQDNs für die SIP-Domäne an, auch nicht den FQDN für den Zugriffs-Edgedienst.



  - Kontaktinformationen: Geben Sie die E-Mail-Adresse des Administrators jeder SIP-Domäne an, die Sie einbeziehen.

**F: Wie kann ich die Lync-Skype-Konnektivität in einem Szenario mit geteilter Domäne aktivieren?**

**A:** In einem Szenario mit geteilter Domäne, d. h. wenn Sie sowohl Lync Online 2013 als auch lokal Lync Server nutzen und die Benutzer sowohl online als auch lokal die gleiche SIP-Domäne verwenden, aktivieren Sie die Lync-Skype-Konnektivität mit zwei Schritten in der nachstehenden Reihenfolge:

1.  Richten Sie die Lync-Skype-Konnektivität lokal wie in der Anleitung zur Bereitstellung von Verbindungen mit öffentlichen Instant Messaging-Diensten beschrieben ein.

2.  Warten Sie, bis eine Bestätigung anzeigt wird, dass Ihre Domäne von Microsoft bereitgestellt wurde.

3.  Nachdem die Bestätigung angezeigt wurde, aktivieren Sie **Externe Kommunikation** im Lync Admin Center. Weitere Informationen finden Sie unter [http://office.microsoft.com/de-de/support/configure-external-communications-HA102817865.aspx?CTT=5\&origin=HA102817356](http://office.microsoft.com/de-de/support/configure-external-communications-ha102817865.aspx?ctt=5%26origin=ha102817356).

Diese Reihenfolge ist wichtig. Sie müssen die lokale Konnektivität einrichten, bevor Sie die Kommunikation in Lync Online aktivieren. Wird die Reihenfolge nicht eingehalten, können die Informationen, die Sie für die lokale Konnektivität auf <https://pic.lync.com> eingeben, nicht übermittelt werden. Wenn Sie Lync Online bereits für die externe Kommunikation mit dieser Domäne eingerichtet haben, müssen Sie die Option deaktivieren, 24 Stunden warten und dann neu beginnen, indem Sie zuerst die lokalen Informationen auf <https://pic.lync.com> eingeben und dann die externe Kommunikation für Lync Online aktivieren.

**F: kann ich mehrere FQDNs für den Zugriffs-Edgedienst für die Skype-Konnektivität bereitstellen?**

**A:** Sie können mit jeder Bereitstellungsanforderung bis zu 10 FQDNs für den Zugriffs-Edgedienst bereitstellen.

**F: Kann ich die Liste mit den E-Mail-Adressen der Microsoft-Konten bekommen, bei Ihnen für die Organisation vorliegt, die die Bereitstellung anfordert?**

**A:** Nein. Diese Adressen enthalten Informationen, über die die jeweiligen Benutzer persönlich identifiziert werden können und werden daher nicht weitergegeben.

**F: Wie kann ich einen Windows Live Messenger-Kontakt hinzufügen, dessen ID eine andere Domäne als die von Windows Live unterstützten enthält?**

**A:** Wenn Sie einen Windows Live Messenger-Benutzer mit einem Konto oder einer ID hinzufügen, die eine andere Domäne als die von Windows Live unterstützten enthält, geben Sie die Adresse im folgenden Format ein: \<Benutzername\>(\<Domänenname\>)@msn.com, wobei \<Domänenname\> der Domänenname in der E-Mail-Adresse des Benutzers ist. Wenn Sie beispielsweise "ted@contoso.com" hinzufügen möchten, verwenden Sie das Format "ted(contoso.com)@msn.com". Eine Liste der Domänen, die von Windows Live verwaltet werden, finden Sie im Abschnitt "Unterstützte Domänen" im Artikel "Bekannte Probleme mit öffentlichen Instant Messaging-Diensten nach der Installation von Live Communications Server Service Pack 1" an "http://support.microsoft.com/?kbid=897567".

**F: Wie lange dauert der Bereitstellungsprozess?**

**A:** Die Bereitstellung kann bis zu 30 Tage in Anspruch nehmen.

**F: Wie erfahre ich, wann die Bereitstellung abgeschlossen ist?**

**A:** Microsoft sendet Ihnen nach Abschluss der Bereitstellung eine E-Mail-Benachrichtigung.

**F: Wie kann ich die Konfigurations- oder Kontaktdetails aktualisieren, die ich übermittelt habe?**

**A:** Sie können Ihre Angaben nach Abschluss der Bereitstellung auf der gleichen Website aktualisieren, auf der Sie auch die Bereitstellung angefordert haben. Geben Sie Ihre Vertragsnummer ein, und klicken Sie auf **Dienst aktualisieren**.

