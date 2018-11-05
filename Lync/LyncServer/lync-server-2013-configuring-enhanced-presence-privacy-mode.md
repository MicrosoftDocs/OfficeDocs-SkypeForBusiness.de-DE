---
title: Konfigurieren des erweiterten Datenschutzmodus für Anwesenheitsinformationen
TOCTitle: Konfigurieren des erweiterten Datenschutzmodus für Anwesenheitsinformationen
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg399028(v=OCS.15)
ms:contentKeyID: 49295742
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren des erweiterten Datenschutzmodus für Anwesenheitsinformationen

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Mit dem erweiterten Datenschutzmodus für Anwesenheitsinformationen können die Benutzer den Zugriff auf ihre Anwesenheitsinformationen einschränken, sodass diese nur für Kontakte in ihrer Lync 2013-Kontaktliste sichtbar sind. Diese Option kann mit dem EnablePrivacyMode-Parameter der Cmdlets **New-CsPrivacyConfiguration** und **Set-CsPrivacyConfiguration** gesteuert werden. Wenn EnablePrivacyMode auf True festgelegt ist, steht die Option zum Einschränken von Anwesenheitsinformationen für Kontakte in den Lync 2013-Statusoptionen zur Verfügung. Wird EnablePrivacyMode auf False festgelegt, können die Benutzer entscheiden, Anwesenheitsinformationen entweder für alle Kontakte anzuzeigen oder Änderungen zu übernehmen, die der Administrator zukünftig am Datenschutzmodus vornimmt.


> [!IMPORTANT]
> Die Datenschutzeinstellungen von Lync 2013 und Lync 2010 werden von früheren Versionen (Microsoft Office Communicator 2007 R2 oder Microsoft Office Communicator 2007) nicht unterstützt. Falls eine Anmeldung über frühere Versionen von Office Communicator zulässig ist, könnten der Status, die Kontaktinformationen oder das Bild eines Benutzers von Lync 2013 für unbefugte Personen zugänglich sein. Darüber hinaus werden die Datenschutzeinstellungen eines Lync 2013-Benutzers zurückgesetzt, wenn dieser sich zu einem späteren Zeitpunkt mit einer früheren Version von Communicator anmeldet.<BR>Aus diesem Grund sollten Sie in einem Migrationsszenario vor der Aktivierung des erweiterten Datenschutzmodus für Anwesenheitsinformationen die folgenden Schritte ausführen: 
> <UL>
> <LI>
> <P>Stellen Sie sicher, dass für jeden Benutzer Lync 2013 installiert wurde.</P>
> <LI>
> <P>Definieren Sie eine Clientversionsrichtlinie, um eine Anmeldung über frühere Versionen von Communicator zu verhindern.</P></LI></UL>



## So aktivieren Sie den erweiterten Datenschutzmodus für Anwesenheitsinformationen

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie den folgenden Befehl aus:
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    Mit diesem Befehl wird der Datenschutzmodus für alle derzeit in der Organisation verwendeten Datenschutzkonfigurationseinstellungen aktiviert.

## Siehe auch

#### Weitere Ressourcen

[Get-CsPrivacyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPrivacyConfiguration)  
[New-CsPrivacyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsPrivacyConfiguration)  
[Set-CsPrivacyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPrivacyConfiguration)

