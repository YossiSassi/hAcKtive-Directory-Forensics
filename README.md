<h1 style="color: #5e9ca0;"><span style="color: #008080;">h</span><span style="color: #2b2301;">Ac</span><span style="color: #008080;">K</span><span style="color: #2b2301;">tive Directory Forensics</span></h1>
<hr />
<h3 style="color: #2e6c80;"><span style="color: #333399;">Compiled by 1nTh35h311 (<a title="#yossi_sassi" href="https://twitter.com/yossi_sassi" target="_blank">#yossi_sassi</a>)</span></h3>
<p>Page last updated on February 13th 2023 (tools in links may update routinely)</p>
<p><strong>Comments and improvements are <a href="mailto:yossis@protonmail.com" target="_blank"><span style="color: #333333;">welcome</span></a></strong></p>
<hr />
<h2 style="color: #2e6c80;">Talks, slides &amp; videos:</h2>
'HackCon' 2023 talk: <a title="Hacktive Directory Forensics - a toolkit for understanding who|what|when in your domain" href="https://www.hackcon.org/hacktive-directory-forensics-a-toolkit-for-understanding-whowhatwhen-in-your-domain" target="_blank"><span style="color: #000080;">Hacktive Directory Forensics - a toolkit for understanding who|what|when in your domain</span></a></span> <span style="color: #000000;">
<p><a href="https://www.slideshare.net/yossis1/hacktive-directory-forensics-hackcon18-oslo" target="_blank"><strong>Slides</strong></a> - Presentation slides</p>
'Hack In Paris' 2022 talk: <a title="&quot;I know what your 'Microsoft Mainframe' did last summer!&quot;" href="https://hackinparis.com/archives/2022/#talk-2022-i-know-what-your-microsoft-mainframe-did-last-summer-hacktive-directory-forensics" target="_blank"><span style="color: #000080;">Hacktive Directory Forensics (announcing 'GoldFinger' - Suspicious TGT Detector)</span></a></span> <span style="color: #000000;">
<p><a title="Talk video on youtube" href="https://www.youtube.com/watch?v=a9LKT49JSd0" target="_blank"><strong>Video</strong></a> - Talk video on YouTube</p>
<BR>SecurityFest 2022 talk: <a title="&quot;I know what your 'Microsoft Mainframe' did last summer!&quot;" href="https://securityfest.com/speakers/2022/i-know-what-your-microsoft-mainframe-did-last-summer-hacktive-directory-forensics/" target="_blank"><span style="color: #000080;">"I know what your 'Microsoft Mainframe' did last summer!"</span></a></span> <span style="color: #000000;">
<p><a title="Talk video on youtube" href="https://youtu.be/PXHmXvWcJPY" target="_blank"><strong>Video</strong></a> - Talk video on YouTube</p>
<BR>OSDFCon 2021 talk: <a title="&quot;I know what your AD did last summer!..&quot;" href="https://www.osdfcon.org/events_2021/i-know-what-your-ad-did-last-summer/" target="_blank"><span style="color: #000080;">"I know what your AD did last summer!.."</span></a></span> <span style="color: #000000;">
<p><a href="https://s3.amazonaws.com/resources.osdfcon.org/presentations/2021/Yossi_Sassi_What_Your_AD_Did_Last_Summer_OSDFCon_2021.pdf" target="_blank"><strong>Slides</strong></a> - Presentation slides in PDF</p>
<p><a title="Talk video on youtube" href="https://www.youtube.com/watch?v=0WG186KOkLc" target="_blank"><strong>Video</strong></a> - Talk video on YouTube</p>
<hr />
<h2 style="color: #2e6c80;">Open source tools &amp; Scripts:</h2>
<p><strong><a title="Invoke-TgsMonitor - Monitor TGS requests (All, or just Failed)" href="https://github.com/YossiSassi/Invoke-TgsMonitor" target="_blank">Invoke-TgsMonitor - Monitor TGS requests (All, or just Failed)</a>- </strong>Monitor TGS requests (All, or just Failed). Useful during a live IR without other central threat hunting log solution, or in general, to monitor access & failure reasons. Requires 'Event Log Readers' permission or equivalent.</p>
<p><strong><a title="Invoke-PostKrbtgtResetMonitor - Centralized detection of Golden Ticktes after resetting the krbtgt password TWICE" href="https://github.com/YossiSassi/Invoke-PostKrbtgtResetMonitor" target="_blank">Invoke-PostKrbtgtResetMonitor - Centralized detection of Golden Ticktes after resetting the krbtgt password TWICE</a>- </strong>Centralized detection of Golden Ticktes via event ID 4769 (TGS) with Error code 0x1f & TGT Anomalies. Useful when coming to a site recently After a krbtgt double-reset. No Dependencies/modules. Requires Event Log Redears or equivalent</p>
<p><strong><a title="GoldFinger - Suspicious Kerberos TGT detector" href="https://github.com/YossiSassi/GoldFinger-Suspicious_TGT_Hunter" target="_blank">GoldFinger - Suspicious Kerberos TGT detector</a>- </strong>Collects | analyzes | hunts for potential Golden Tickets & Pass-The-Hash in domain-joined Endpoints. No Agent, uses WinRM or SMB</p>
<p><strong><a title="Get-ADGroupChanges" href="https://github.com/YossiSassi/Get-ADGroupChanges" target="_blank">Get-ADGroupChanges</a>- </strong>"pure" powershell cmdlet (no module dependencies or special AD permissions needed) to retrieve change history in an AD group membership, or all groups, or per user since the creation of the domain. relies on object metadata rather than event logs. useful for DF/IR, tracking changes in groups etc'. Supports querying AD Metadata either from an Online Domain Controller, or from an offline system state backup/Snapshot</p>
<p><strong><a title="Get-ADUserAddedToGroup" href="https://github.com/YossiSassi/Get-ADUserAddedToGroup" target="_blank">Get-ADUserAddedToGroup</a>- </strong>simple &amp; quick script to check when a user was added to a group (basic/entry level forensics, requires activedirectory module)</p>
<p><strong><a title="AD Replication Metadata History" href="https://github.com/YossiSassi/AD-Replication-Metadata" target="_blank">AD Replication Metadata History</a> - </strong>Quickly tracks changes on your AD objects, even if event logs were wiped or recycled (e.g. during an Incident Response), using Replication metadata history. for both Online &amp; Offline scenarios. No special permissions needed for Live AD query (local admin only required when using Offline DB for port bind)<strong><br /></strong></p>
<p><strong><a title="TimeLineGenerator - AD account timeline generator - parse DC security logs & display activity timeline" href="https://github.com/YossiSassi/TimeLineGenerator" target="_blank">TimeLineGenerator - AD account timeline generator - parse DC security logs & display activity timeline</a>- </strong>AD account timeline generator, displaying grid/CSV with accounts' activity timeline. Can run directly on Domain Controllers (Live, through WinRM), OR - specify Path to Evtx files. Can run a Full/Longer report, or a more Focused/Quicker one, with a select set of events to filter. Can set the Max Events to fetch Per DC.</p>
<p><strong><a href="https://github.com/ANSSI-FR/ADTimeline" target="_blank" rel="noopener">ADTimeLine</a> - </strong>Generates a timeline based on Active Directory replication metadata for objects considered of interest (by <a href="https://www.ssi.gouv.fr/" target="_blank">ANSSI-FR</a>, national authority for security and defense of information systems de France)</p>
<p><strong><a title="Get-LDAPperformance - LDAP Query Performance Analysis for Threat Hunting or IT optimization" href="https://github.com/YossiSassi/Get-LDAPperformance" target="_blank" rel="noopener">Get-LDAPperformance - LDAP Query Performance Analysis for Threat Hunting or IT optimization</a> - </strong>Collects LDAP Query Performance Events and analyzes them to CSV & Grid. Helps in identifying large or unusual LDAP queries, either for Threat Hunting or IT optimization. No Dependencies. No modules required. Requires Event Log Readers permission or equivalent (privileged/access to DC 'directory Services' logs).</p>
<p><strong><a title="Get Last Logon of an account (user or computer)" href="https://github.com/YossiSassi/Get-LastLogon" target="_blank">Get Last Logon of an account (user or computer)</a> - </strong>Get up-to-date last logon of any user or computer from all Domain Controllers in the domain. no dependencies, no special permissions, just LDAP connectivity.</p>
<p><strong><a title="Get-DCShadowNTDSdsa" href="https://github.com/YossiSassi/Get-DCShadowNTDSdsa" target="_blank" rel="noopener">Get-DCShadowNTDSdsa</a> - </strong>Finds potential exploitation of DCShadow, in retrospect, from relevant DC demotion/ntdsDSA deletion</p>
<p><strong><a title="Search for String in AD Objects" href="https://github.com/YossiSassi/Misc_Tools/blob/main/Search%20for%20string%20in%20AD%20Objects.ps1" target="_blank">Search for String in AD Objects</a> - </strong>Looks for interesting strings (e.g. password), as well as IP addresses, in all AD objects</p>
<p><strong><a title="Get-ADPrincipalKerberosTokenGroup" href="https://github.com/YossiSassi/Get-ADPrincipalKerberosTokenGroup" target="_blank">Get-ADPrincipalKerberosTokenGroup</a> - </strong>a powershell implementation of PAC enum (similar to <a title="getpac.py" href="https://github.com/SecureAuthCorp/impacket/blob/master/examples/getPac.py" target="_blank">getpac.py</a>). does not require special privileges. enumerates effective token (cumulative group SIDs from Kerberos PAC) for any user, by any authenticated user</p>
<p><strong><a href="https://github.com/YossiSassi/LDAPmonitor" target="_blank" rel="noopener">LDAPMonitor</a> - </strong>My updated ps1 version of @<a href="https://github.com/p0dalirius/LDAPmonitor" target="_blank">p0dalirius</a>'s script. Monitor creation, deletion and changes to LDAP objects during a *live* forensics session, or pentest and/or for sys admin|secops during a pentest</p>
<p><span style="text-decoration: underline;"><strong>Additional topic-related scripts:</strong></span></p>
<p><strong><a title="Get-UserSession" href="https://github.com/YossiSassi/Get-UserSession" target="_blank" rel="noopener">Get-UserSession</a> - </strong>Queries user sessions for the entire domain (Interactive/RDP etc), allowing you to query a user and see all his logged on sessions, whether Active or Disconnected. Can be correlated during live forensics with active entity sessions</p>
<p><strong><a title="Get-RemotePSSession" href="https://github.com/YossiSassi/Get-RemotePSSession" target="_blank">Get-RemotePSSession</a>&nbsp;- </strong>Query PS Sessions (wsman) for their connected users, IPs &amp; hosts, locally &amp; remotely. Can be correlated during live forensics with active entity sessions</p>
<p><strong><a title="WeakCipherUsage" href="https://github.com/YossiSassi/WeakCipherUsage" target="_blank">WeakCipherUsage</a> - </strong>Gets weak cipher usage (RC4 used in Domain environments). useful for On-Prem diagnostics, similar to MDI (cloud app sec) weak cupher usage report.&nbsp;Can be useful to assess if can move to AES only (see which systems still use RC4), as well as basic indication for potential Kerberoasting attack (with False Positives, naturally, since systems may generate downgrade TGS regardless of this common attack)</p>
<p><strong><a title="ZeroLogon Post-Exploitation Check" href="https://github.com/YossiSassi/ZeroLogon-Exploitation-Check" target="_blank" rel="noopener">ZeroLogon Post-Exploitation Check</a> - </strong>Script to automate checks for potential exploitation of CVE-2020-1472 (aka ZeroLogon) in the domain. This is a <em>very</em> "quick and dirty" lookup for some of the leading artifects in determining an actual exploitation of CVE-2020-1472, compiled from multiple blogs. Ideally, the 2nd check (for events from Security &amp; System event logs) can be done from a SIEM/Syslog/Event collector, which keeps events far enough back to detect such exploits. Note that if netlogon logs were not enabled in the environment, and DC logs were overwritten by newer events, an exploitation could have happened and would not be noticed by the remaining artifacts in the environment checked</p>
<p><strong><a title="Hunt for PrintNightmare Exploitation" href="https://github.com/YossiSassi/HuntPrintNightmareExploitation" target="_blank">Hunt for PrintNightmare Exploitation</a> - </strong>Looks for evidence of PrintNightmare exploitation execution in Logs. Requires 'Event Log Readers' or higher permissions. Defaults to domain controllers, yet can be pointed to any/all domain machines (using -AllComputers parameter, or changes to LDAP query). Outputs results of potential PrintNightmare exploitation to console + CSV file</p>
<p><strong><a title="Find renamed users (with updated &amp; previous samaccountname values)" href="https://github.com/YossiSassi/Misc_Tools/blob/main/Find%20renamed%20users%20-%20get%20current%20%26%20previous%20samAccountName.ps1" target="_blank"> Find renamed users (with current &amp; previous samaccountname values)</a> - </strong>Useful to detect SamAccountName Spoofing (CVE-2021-42278 and CVE-2021-42287). Find renamed accounts in AD logs (and their current and previous samaccountname values). No dependencies/No AD module required. Requires 'Event Log Redears' permission or higher</p>
<hr />
<h2 style="color: #2e6c80;">Other useful resources:</h2>
<p><strong><a title="ADSecurity.org" href="https://adsecurity.org/" target="_blank" rel="noopener">ADSecurity.org</a> - </strong>Useful articles on AD Security in general, including on AD replication metadata</p>
<p><strong><a title="DC Recovery steps (for DFIR)" href="https://github.com/gtworek/PSBits/blob/master/DFIR/DC_Recovery.md" target="_blank" rel="noopener">DC Recovery steps (for DFIR)</a> - </strong>Some proposed steps to reinstall DCs after a compromise</p>
<!--<p><strong><a title="Hunting with AD Repl metadata" href="http://www.harmj0y.net/blog/defense/hunting-with-active-directory-replication-metadata/" target="_blank" rel="noopener">Hunting with AD Replication metadata</a> - </strong>article on AD repl metadata, from another cool blog by <a title="harmj0y.net" href="http://www.harmj0y.net/blog/" target="_blank">harmj0y</a></p>-->
<p>&nbsp;</p>
