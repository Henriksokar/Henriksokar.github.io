<!DOCTYPE html>
<!---
comment: The following html document is the HTML structure of the personal web-page of Henrik Skaaning 
and can be found @ www.Henrikskaaning.dk. The page is power by a css stylesheet and hosted on github, 
has service with dkhostmaster. My first attempt in coding something for the world to see. Based on a 
youtube tutorial. 

Table of contents: 

1. language
2. head
3. body
--->

<!--- comment: 1. LANGUAGE OF THE CODE--->

<html lang="da">
  <!--- comment: language of the code is "da" (i use a danish keyboard and we have the ÆØÅ), the funtional
  languge of the code itself will be in english as far as i remember not to do it in danish. The language
  of the content will - as this is a curriculum vitae, be in danish as this is where i am searching for a job
  --->

  <!--- comment: 2. HEAD --->

  <head>
    <meta charset="UTF-8" />

    <!--- comment: i have no idea what the following code does. --->
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <!--- comment: end of comment --->

    <meta name="keywords" content="CV, Resume, Personlig hjemmeside" />
    <meta
      name="description"
      content="En lille hjemmeside som indeholder Henrik Skaanings CV, information om uddannelse og tidligere ansættelser og projekter."
    />
    <title>Henrikskaaning.dk - resumé og CV</title>

    <!--- comment: CSS stylesheet: when in testing use href="test-styles.css" when in standard operating mode,
      use href="styles.css" --->
    <link rel="stylesheet" type="text/css" href="test-styles.css" />

    <!--- comment: my fontawesome kit in use for this webpage --->
    <script
      src="https://kit.fontawesome.com/d0f17566dd.js"
      crossorigin="anonymous"
    ></script>
  </head>

  <!--- comment: 3. BODY: BEGINNING OF CONTENT: THE ONE DIV TO RULE THEM ALL. --->
  <body>
    <div class="resumé_og_cv">
      <!--- comment: This webpage consists, basically, of two sides - the left_side (venstre_side) & 
        right side (højre_side) --->

      <div class="venstre_side">
        <!--- comment: the venstre_side Has the following elements split into two elements, firstly a picture and lastly
          some resume info, a list of skills, and some links to social profiles. 
          
        first the picture: --->
        <div class="resume_profile_picture">
          <!--- comment: profile picture. taken when i worked for ATP. I think it is sources locally - maybe i should replace
            this with a link to github, might make the page run faster --->
          <img src="14340_henrik.jpg" alt="A picture of me" />
        </div>

        <!--- comment: lastly, the rest --->
        <div class="resume_content">
          <!--- comment: container div --->
          <div class="resume_item resume_info">
            <!--- comment: Basic info such as name, education, phone number en email-address and web-page the list-items are made with css and 
              icons sourced through a third party. --->
            <div class="title">
              <p class="bold">Henrik Skaaning</p>
              <p class="regular">Kandidat i socialvidenskab & psykologi</p>
            </div>
            <ul>
              <li>
                <div class="icon">
                  <i class="fas fa-mobile" aria-hidden="true"></i>
                </div>
                <div class="data">+45 91768924</div>
              </li>
              <li>
                <div class="icon">
                  <i class="fas fa-envelope" aria-hidden="true"></i>
                </div>
                <div class="data">Smelt4@hotmail.com</div>
              </li>
              <li>
                <div class="icon">
                  <i class="fas fa-wifi" aria-hidden="true"></i>
                </div>
                <div class="data">www.henrikskaaning.dk</div>
              </li>
            </ul>
          </div>

          <!--- comment: List of skills --->
          <!--- comment: container div --->
          <div class="resume_item resume_skills">
            <div class="title">
              <p class="bold">Skills</p>
            </div>

            <!--- comment: The following code can be manipulated in such a way the you create a "progress-bar" for skills in the 
              following lists: There are however still problems with the code. I have failed to integrate a "sublist" beneath the  individual
              skills, even if i have made it look as if that was not the case: --->

            <!--- comment: coding that (doesent) contains a sublist: i want this to be an accordion button, that keeps the same dimensions and the
              progress bar. i also want a small white-ish arrow pointing down (a wedge would do) to indicate that there is a button. If
              this is sucessfull i should also have a "combined" skill-element --->

            <!--- i have now created the accordion button. i will now try to make the wedge turn upside down when the accorion is cliked. --->

            <!--- First Accordion Button -->
            <div class="accordion">
              <button type="button" class="accordion_button">
                <div class="accordion_skill">
                  <ul class="ul_accordion">
                    <li class="li_accordion">
                      <div class="skill_name">Kodning</div>
                      <div class="skill_progress">
                        <span style="width: 2%"> </span>
                      </div>
                      <div class="skill_per">2%</div>
                    </li>
                  </ul>
                </div>
                <div class="accordion_button_icon">
                  <i
                    id="icon"
                    class="fas fa-angle-double-down"
                    aria-hidden="true"
                  ></i>
                </div>
              </button>
              <div class="accordion_content">
                <div class="kodning_sublists_box">
                  <ul class="ul_kodning_sublists">
                    <li class="li_kodning_sublist">
                      <div class="skill_element">Basic HTML & HTML5</div>
                      <div class="skill_element_progress">
                        <span style="width: 100%"> </span>
                      </div>
                      <div class="skill_element_per">100%</div>
                    </li>
                    <li class="li_kodning_sublist">
                      <div class="skill_element">Basic CSS</div>
                      <div class="skill_element_progress">
                        <span style="width: 100%"> </span>
                      </div>
                      <div class="skill_element_per">100%</div>
                    </li>
                  </ul>
                </div>
              </div>
            </div>

            <!--- Script running the accordion button -->
            <script>
              document
                .querySelectorAll(".accordion_button")
                .forEach((button) => {
                  button.addEventListener("click", () => {
                    const accordionContent = button.nextElementSibling;

                    button.classList.toggle("accordion_button--active");

                    if (button.classList.contains("accordion_button--active")) {
                      accordionContent.style.maxHeight =
                        accordionContent.scrollHeight + "px";
                    } else {
                      accordionContent.style.maxHeight = 0;
                    }
                  });
                });
            </script>

            <!--- 
              
              Script trying to run the animation of the "angles down" button so it turns upside down. 
              This absolutely does not work. it however doesnt ruin the webpage.

              --->
            <script>
              if (button.classList.contains("accordion_button--active")) {
                icon.className = "fa-angle-double-down open";
              } else {
                icon.className = "fa-angle-double-down";
              }
            </script>

            <!--- comment: coding sublist that consists of the following elements: Basic HTML & HTML5, Basic CSS --->

            <!--- comment: sagsbehandling --->
            <div class="kodning">
              <ul class="ul_kodning">
                <li class="li_kodning">
                  <div class="skill_name_sagsbehandling">Sagsbehandling</div>
                  <div class="skill_progress">
                    <span style="width: 60%"> </span>
                  </div>
                  <div class="skill_per">60%</div>
                </li>
              </ul>
            </div>

            <!--- comment: Customer Service --->
            <div class="kodning">
              <ul class="ul_kodning">
                <li class="li_kodning">
                  <div class="skill_name">Kundeservice/rådgivning</div>
                  <div class="skill_progress">
                    <span style="width: 99%"> </span>
                  </div>
                  <div class="skill_per">99%</div>
                </li>
              </ul>
            </div>

            <!--- comment: Interview Methods --->
            <div class="kodning">
              <ul class="ul_kodning">
                <li class="li_kodning">
                  <div class="skill_name">Interviewmetodik</div>
                  <div class="skill_progress">
                    <span style="width: 99%"> </span>
                  </div>
                  <div class="skill_per">99%</div>
                </li>
              </ul>
            </div>

            <!--- comment: change workshops --->
            <div class="kodning">
              <ul class="ul_kodning">
                <li class="li_kodning">
                  <div class="skill_name">Forandringsværksteder</div>
                  <div class="skill_progress">
                    <span style="width: 99%"> </span>
                  </div>
                  <div class="skill_per">99%</div>
                </li>
              </ul>
            </div>

            <!--- comment: statistics --->
            <div class="kodning">
              <ul class="ul_kodning">
                <li class="li_kodning">
                  <div class="skill_name">Statistik</div>
                  <div class="skill_progress">
                    <span style="width: 50%"> </span>
                  </div>
                  <div class="skill_per">50%</div>
                </li>
              </ul>
            </div>

            <!--- comment: Discourse Analysis --->
            <div class="kodning">
              <ul class="ul_kodning">
                <li class="li_kodning">
                  <div class="skill_name">Diskursanalyse</div>
                  <div class="skill_progress">
                    <span style="width: 60%"> </span>
                  </div>
                  <div class="skill_per">60%</div>
                </li>
              </ul>
            </div>

            <!--- comment: Volunteer management --->
            <div class="kodning">
              <ul class="ul_kodning">
                <li class="li_kodning">
                  <div class="skill_name">Frivilligorganisering</div>
                  <div class="skill_progress">
                    <span style="width: 99%"> </span>
                  </div>
                  <div class="skill_per">99%</div>
                </li>
              </ul>
            </div>

            <!--- comment: Youth Organinization --->
            <div class="kodning">
              <ul class="ul_kodning">
                <li class="li_kodning">
                  <div class="skill_name">Ungeorganisering</div>
                  <div class="skill_progress">
                    <span style="width: 99%"> </span>
                  </div>
                  <div class="skill_per">99%</div>
                </li>
              </ul>
            </div>

            <!--- comment: Organizational management --->
            <div class="kodning">
              <ul class="ul_kodning">
                <li class="li_kodning">
                  <div class="skill_name">Organisationsledelse</div>
                  <div class="skill_progress">
                    <span style="width: 66%"> </span>
                  </div>
                  <div class="skill_per">66%</div>
                </li>
              </ul>
            </div>
          </div>

          <!--- comment: A listing of links to social media accounts --->
          <div class="resume_item resume_social">
            <div class="title">
              <p class="bold">Social</p>
            </div>
            <ul>
              <li>
                <div class="icon">
                  <i class="fab fa-facebook-f" aria-hidden="true"></i>
                </div>
                <div class="data">
                  <p class="semi_bold">Facebook:</p>
                  <a href="https://www.fb.me/henrik.skaaning" class="link">
                    klik hér!
                  </a>
                </div>
              </li>
              <li>
                <div class="icon">
                  <i class="fab fa-instagram-square" aria-hidden="true"></i>
                </div>
                <div class="data">
                  <p class="semi_bold">Instagram:</p>
                  <a href="https://www.instagr.am/skaanings" class="link">
                    klik hér!
                  </a>
                </div>
              </li>
              <li>
                <div class="icon">
                  <i class="fab fa-linkedin" aria-hidden="true"></i>
                </div>
                <div class="data">
                  <p class="semi_bold">LinkedIn:</p>
                  <a
                    href="https://www.linkedin.com/in/henrikskaaning/"
                    class="link"
                  >
                    klik hér!
                  </a>
                </div>
              </li>
            </ul>
          </div>
        </div>
      </div>

      <!--- comment: the højre_side that contains most of the "meat" in the presentation, so to say --->
      <div class="højre_side">
        <div class="resume_item resume_om">
          <div class="title">
            <p class="bold">Hvem er jeg?</p>
          </div>
          <p>
            www.henrikskaaning.dk er et af mine første forsøg ud af et reelt
            kodningsprojekt - her i meget simpel HTML og CSS. Siden har til
            formål at være et interaktivt CV (selvom vi ikke helt er der endnu)
            og en måde at få fat i mig på.
          </p>
        </div>
        <div class="resume_item resume_faglig_profil">
          <div class="title">
            <p class="bold">Faglig profil:</p>
          </div>
          <p class="regular">
            Kandidat i socialvidenskab og Psykologi fra Roskilde Universitet.
            Erfaringer inden for så forskelligtartede områder som salg og
            service, telefonisk kunderådgivning og organiationsledelse i
            politiske organisationer. Jeg kan køre dit uddannelsesforløb,
            programmere en simpel hjemmeside, planlægge og udføre
            borgerindragelse. Sagsbehandle ud fra gældende lovgivning på
            beskæftigelses, uddannelses og socialområdet. Arrangere dit event.
            Eller hente dig en kop kaffe og tage en god snak med dig. Jeg er en
            behagelig bulldozer som er dedikeret til at levere løsninger af høj
            kvalitet til gavn for kolleger og borgere.
          </p>
        </div>
        <div class="resume_item resume_erhvervserfaring">
          <div class="title">
            <p class="bold">Erhvervserfaring:</p>
          </div>
          <ul>
            <li>
              <div class="date">2021(7) - Present:</div>
              <div class="info">
                <p class="small_bold">Københavns Kommune</p>
                <p class="semi_bold">Vikar i hjemmeplejen</p>
              </div>
              <div>
                <p class="content">
                  Rengøringsvikar hos hjemmeplejen i Københavns Kommune.
                </p>
              </div>
            </li>
            <li>
              <div class="date">2021(6) - 2021 (7):</div>
              <div class="info">
                <p class="small_bold">Styrelsen for Patientsikkerhed</p>
                <p class="semi_bold">Operatør</p>
              </div>
              <div>
                <p class="content">
                  Operatør i coronaopsporingsenheden hos Styrelsen for
                  Patientsikkerhed; rådgivning af borgere ifbm. covid-19
                  pandemien.
                </p>
              </div>
            </li>
            <li>
              <div class="date">2021(5) - 2021(6):</div>
              <div class="info">
                <p class="small_bold">ATP</p>
                <p class="semi_bold">Floorwalker</p>
                <p class="small_content">
                  Resultater: Sørgede for at mit hold var knivskarpe og leverede
                  rådgivning af højeste kvalitet ind til nedlukningen af
                  smitteopsporingen hos ATP.
                </p>
              </div>
              <div>
                <p class="content">
                  Ansat som floorwalker hos ATP, i smitteopsporings-enheden,
                  hvor vi dagligt har rådgivet tusindvis af smittede og danskere
                  i nærkontakt med smittede, om styrelsen for patientsikkerheds
                  retningslinjer ifbm. Covid-19 pandemien. Jeg har som
                  floorwalker haft ansvar for den daglige rådgivning & faglige
                  opkvalificering af hold 17's kunderådgivere. Opgave udført
                  pva. Styrelsen for patientsikkerhed.
                </p>
              </div>
            </li>
            <li>
              <div class="date">2021(2) - 2021(5):</div>
              <div class="info">
                <p class="small_bold">ATP</p>
                <p class="semi_bold">Kunderådgiver</p>
                <p class="small_content">
                  Resultater: Jeg klarede jobbet så godt at jeg endte med at
                  blive forfremmet til floorwalker for mit hold.
                </p>
              </div>
              <div>
                <p class="content">
                  Kunderådgiver i ATP's smitteopsporings-enhed på team-17 ifbm.
                  Covid-19 Pandemien. Opgaven bestod i at rådgive og informere
                  om styrelsen for patientsikkerheds retninglinjer om test,
                  isolation og hygiejne bla. Opgave udført pva. Styrelsen for
                  patientsikkerhed.
                </p>
              </div>
            </li>
            <li>
              <div class="date">2020(12) - 2021(2):</div>
              <div class="info">
                <p class="small_bold">Falck</p>
                <p class="semi_bold">Poder</p>
                <p class="small_content">
                  Resultater: fik voksne brandmænd til at bæve i frygt - kun
                  vha. en 10cm lang podepind.
                </p>
              </div>
              <div>
                <p class="content">
                  Podning af borgere i Falcks testcenter på Frederiksberg. Havde
                  flere hundrede borgere ved min podestation - en mulighed for
                  kundeservice med et smil bag mundbindet, foruden registrering
                  og håndtering af de mange tusinde borgere vi endte med at have
                  igennem
                </p>
              </div>
            </li>
            <li>
              <div class="date">2020(12) - 2021(1):</div>
              <div class="info">
                <p class="small_bold">Copenhagen Medical</p>
                <p class="semi_bold">Steward</p>
                <p class="small_content">
                  Resultater: lærte at stå, ret op og ned i 10 stive timer af
                  gangen.
                </p>
              </div>
              <div>
                <p class="content">
                  Håndtering af de mange tusinde borgere der kom igennem
                  Copenhagen Medicals testcenter i Parken, herunder generel
                  information til borgere, håndtering af kø og deslige.
                </p>
              </div>
            </li>
            <li>
              <div class="date">2015 - 2020:</div>
              <div class="info">
                <p class="small_bold">Strömma Danmark</p>
                <p class="semi_bold">Billetsælger</p>
                <p class="small_content">
                  Resultater: årets medarbejder 2018 (valgt af kolleger).
                </p>
              </div>
              <div>
                <p class="content">
                  Billetsalg og kundeservice hos Strömma Danmark som ejer
                  kanalbådende i Københavns kanaler. God kundeservice med fokus
                  på kvalitet - og en oplagt mulighed for at lære de mange sprog
                  turisterne i København har med sig.
                </p>
              </div>
            </li>
          </ul>
        </div>
        <div class="resume_item resume_uddannelse">
          <div class="title">
            <p class="bold">Uddannelse:</p>
          </div>
          <ul>
            <li>
              <div class="date">2016 - 2019:</div>
              <div class="info">
                <p class="semi_bold">Roskilde Universitet</p>
                <p class="small_bold">
                  Kandidat i socialvidenskab og psykologi.
                </p>
                <p class="small_content">Cand. Soc.</p>
              </div>
              <div>
                <p class="small_content">
                  Kurser: Sociale & samfundsmæssige forandringsprocesser,
                  Kollektive undersøgelsesmetoder - praksisrettet metodekursus,
                  Arbejds- & organisationspsykologi, Pædagogisk psykologi,
                  Kursus i Teknologi-psykologi - studier i menneske-teknologi
                  interaktion, Rettigheder i velfærdsstaten - nationale og
                  internationale perspektiver, diskursanalyse - hvilken og
                  hvordan?
                </p>
                <p class="small_content">
                  Projekter: Speciale: Frygt og fjendtlighed i Dannevang(7). Et
                  lærerperspektiv i forandring (7), Individualisering som
                  psykologisk resultat og samfundsmæssig omstændighed - En
                  undersøgelse af gymnasieelevers håndtering af
                  individualiseringen (12), Konkurrencen, dannelsen og den
                  studerende (10).
                </p>
                <p class="content">
                  Min kandidat er fagligt placeret solidt i tværfeltet mellem
                  socialvidenskaben og psykologien. Den socialvidenskabelige
                  faglighed indeholder elementer fra flere
                  samfundsvidenskabelige områder som økonomi, politologi,
                  sociologi, retssociologi & videnskabsteori og gør brug af en
                  hel værktøjskasse af metoder som eks. statistik og
                  modellering, interviews, deltagende observation og
                  forandrings- og fremtidsværksteder. Det solide teoretiske
                  grundlag og metodikken rettes som oftens mod områder hvor nye
                  burdflader opstår i samfundet; i familien, i arbejdslivet
                  eller uddannelse. ifht. køn, generation, etnicitet og klasse
                  eller klima. Formålet er klart: uddannelsen giver
                  socialvidenskaberen evnen til at tænke - også kritisk,
                  analysere og vha. eksperviden hjælpe organisationer,
                  virksomheder, offentlige organisationer i kommune, region
                  eller stat med at navigere og tilpasse sig nye krav. Hvordan
                  skal vi håndtere me2? Hvordan sikrer vi at folks
                  datarettigheder beskyttes i en tid hvor sociale medier i nogen
                  grad har monopol på vores persondata, hvordan tilpasser vi os
                  klimakrisen? hvordan do we handle the globalisering? Hvad skal
                  der til for at den måde vores samfund er skruet sammen på er
                  til gavn for de mennesker der bor i danmark? Hvad er
                  identitetspolitik? - det er nogle af de spørgsmål en
                  socialvidenskaber kan forsøge at give dig et kvalificeret og
                  videnskabeligt velfunderet bud på.
                </p>
              </div>
            </li>
            <li>
              <div class="date">2012 - 2016:</div>
              <div class="info">
                <p class="semi_bold">Roskilde Universitet</p>
                <p class="small_bold">Bachelor socialvidenskab bsc.</p>
              </div>
              <div>
                <p class="content">
                  Grundlæggende og grundig indføring i social-videnskabens
                  teorier og metoder, i høj grad under samme overskrifter som
                  beskrevet ovenfor.
                </p>
                <p class="small_content">
                  Ekstra aktiviter: kassérer for SamRåd (fagråd for
                  socialvidenskabelige studerende), medlem af Studenterrådet på
                  RUC's bestyrelse.
                </p>
              </div>
            </li>
            <li>
              <div class="date">2008 - 2011:</div>
              <div class="info">
                <p class="semi_bold">Viborg Gymnasium & HF</p>
                <p class="small_bold">Sprog og musik</p>
              </div>
              <div>
                <p class="content">
                  Sprog og musik-klassen på Viborg Gymnasium & HF. Et godt sted
                  at være - musiklinjen var super! Grethe er min gud.
                  Transporttiden ind til byen kunne jeg dog godt have været
                  foruden.
                </p>
                <p class="small_content">
                  Ekstra aktiviteter: Næstformand for elevrådet, Musical (som
                  både skuespiller & musiker), Medlem af Råbekorets triumvirat.
                </p>
              </div>
            </li>
            <li>
              <div class="date">1999 - 2008:</div>
              <div class="info">
                <p class="semi_bold">Skals Folkeskole</p>
              </div>
              <div>
                <p class="content">
                  Lokal folkeskole for skals og omegns børn.
                </p>
                <p class="small_content">
                  Ekstra aktiviteter: Næstformand for elevrådet.
                </p>
              </div>
            </li>
          </ul>
        </div>
        <div class="resume_item resume_organisationsarbejde">
          <div class="title">
            <p class="bold">Organisationsarbejde:</p>
          </div>
          <ul>
            <li>
              <div class="date">2007 - 2020:</div>
              <div class="info">
                <p class="semi_bold">Socialistisk UngdomsFront - SUF</p>
                <p class="small_bold">
                  Almen aktiv; aktivist & medlem af ledelsen.
                </p>
              </div>
              <div>
                <p class="content">
                  Socialistisk ungdomsorganisation med tilknytning til
                  Enhedslisten og Internationalt Forum.
                </p>
              </div>
            </li>
            <li>
              <div class="date">2012 - 2019:</div>
              <div class="info">
                <p class="semi_bold">Studenterrådet på RUC</p>
                <p class="small_bold">Almen aktiv; medlem af bestyrelsen</p>
              </div>
              <div>
                <p class="content">
                  Interesseorganisation for de studerende på Roskilde
                  Universitet. Opgaver herunder kampagnearbejde, koordinering af
                  demonstrationer & aktioner med formål om at skabe opmærksomhed
                  for studerendes vilkår og afskaffelse af eks.
                  uddannelsesloftet og fremdriftsreformen.
                </p>
              </div>
            </li>
            <li>
              <div class="date">2013 - 2016:</div>
              <div class="info">
                <p class="semi_bold">SamRåd</p>
                <p class="small_bold">
                  Kassérer og medlem af koordinationsgruppen
                </p>
              </div>
              <div>
                <p class="content">
                  Fagråd for studerende på de samfundsvidenskabelige uddannelser
                  på Roskilde Universitet; studiemiljø, faglige debatter og
                  organisering i forbindelse med protester.
                </p>
              </div>
            </li>
            <li>
              <div class="date">2011 - 2012:</div>
              <div class="info">
                <p class="semi_bold">Danske Gymnasieelevers Sammenslutning</p>
                <p class="small_bold">Sekretariatsfrivillig; klagesager</p>
              </div>
              <div>
                <p class="content">
                  Frivillig på foreningen for danske gymnasie-elevers
                  sekretariat i København. Mine opgaver var særligt klagesager,
                  men her var jeg også inde over kampagnearbejde,
                  demonstrationer & aktioner, skoling og opkvalificering af
                  medlemmer og elevråd rundt i landet, organisering af stormøder
                  (med op mod 400 deltagere) og debatter.
                </p>
              </div>
            </li>
            <li>
              <div class="date">2009 - 2010:</div>
              <div class="info">
                <p class="semi_bold">Netværket af Ungdomsråd</p>
                <p class="small_bold">Næstformand</p>
              </div>
              <div>
                <p class="content">
                  Næstformand for NAU der repræsenterer kommunale ungdomsråd
                  overfor kulturministeren og desuden forsøger at sætte unges
                  forhold til debat og skabe øget fokus på unges deltagelse i
                  demokratiet.
                </p>
              </div>
            </li>
            <li>
              <div class="date">2008 - 2011:</div>
              <div class="info">
                <p class="semi_bold">Danske Gymnasieelevers Sammenslutning</p>
                <p class="small_bold">
                  Almen aktiv; medlem af bestyrelsen i region skive & senere
                  næstformand for region skive.
                </p>
              </div>
              <div>
                <p class="content">
                  Frivillig i foreningen for danske gymnasie-elever på Viborg
                  Gymnasium & HF, desuden aktiv i den lokale region, skive.
                  Arbejdet bestod af kampagnearbejde, skoling organisering,
                  demonstrationer og aktioner. Jeg lærte for at sige det mildt
                  en del om organisering af unge og frivillige.
                </p>
              </div>
            </li>
            <li>
              <div class="date">2007 - 2010:</div>
              <div class="info">
                <p class="semi_bold">Viborg Ungdomsråd</p>
                <p class="small_bold">
                  Medlem af bestyrelsen & senere næstformand
                </p>
              </div>
              <div>
                <p>
                  Kommunal interessevaretagelse på ungeområdet - herudover
                  forvaltning af en årlig pulje på 100.000 kr, der blev brugt på
                  debatarrangementer, støtte til lokale ungdomsforeninger,
                  kulturelle arrangementer og aktioner for at sætte fokus på
                  bla. ungdomsfattigdom i juletiden med en traditionsrig
                  uddeling af juletræer på hjultorvet i Viborg.
                </p>
              </div>
            </li>
          </ul>
        </div>
        <div class="resume_item resume_fritidsinteresser">
          <div class="title">
            <p class="bold">Fritidsinteresser:</p>
          </div>
          <ul>
            <li><i class="fas fa-book" aria-hidden="true"></i></li>
            <li><i class="fas fa-gamepad" aria-hidden="true"></i></li>
            <li><i class="fas fa-music" aria-hidden="true"></i></li>
            <li><i class="fas fa-tree" aria-hideen="true"></i></li>
          </ul>
        </div>
      </div>
    </div>
  </body>
</html>

