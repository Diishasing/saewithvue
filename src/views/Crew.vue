<template>
  <main>
    <div>
      <div class="department-heading" id="zfr5">
        <div>
          <div class="department-heading-box">
            <h1>ZFR5.0</h1>
          </div>
        </div>
      </div>
      
      <!-- chairperson -->
      <section class="firsttier" id="top-member">
        <div>
          <div class="member">
            <div class="member-image">
              <img
                :src="
                  require(`@/assets/team images/team-members/${captain.image}`)
                "
                alt
              />
            </div>

            <div>
              <div class="perse-des">
                <h2>{{ captain.position }}</h2>
                <h4>{{ captain.name }}</h4>
              </div>
            </div>
            <div class="linksofmembers">
              <div v-for="(link, index) in captain.links" :key="index">
                <a :href="link.link">
                  <img
                    v-lazy="require(`@/assets/icons/team_icons/${link.image}`)"
                    :alt="link.name"
                  />
                </a>
              </div>
            </div>
          </div>
        </div>
      </section>
      <!-- other leaders -->
      <section class="second-tier" id="top-member">
        <div v-for="leader in leaders" :key="leader.name">
          <div class="member">
            <div class="member-image">
              <img
                :src="
                  require(`@/assets/team images/team-members/${leader.image}`)
                "
                alt
              />
            </div>

            <div>
              <div class="perse-des">
                <h2>{{ leader.position }}</h2>
                <h4>{{ leader.name }}</h4>
              </div>
            </div>
            <div class="linksofmembers">
              <div v-for="(link, index) in leader.links" :key="index">
                <a :href="link.link">
                  <img
                    v-lazy="require(`@/assets/icons/team_icons/${link.image}`)"
                    :alt="link.name"
                  />
                </a>
              </div>
            </div>
          </div>
        </div>
      </section>

      <div v-for="department in departments" :key="department.name">
        <div class="department-heading">
          <div>
            <div class="department-heading-box">
              <h1>{{ department.departmentName }}</h1>
            </div>
          </div>
        </div>

        <section class="firsttier">
          <div>
            <div class="member">
              <div class="member-image">
                <img
                  v-lazy="
                    require(`@/assets/team images/team-members/${department.lead.image}`)
                  "
                  alt
                />
              </div>

              <div>
                <div class="perse-des">
                  <h2>{{ department.lead.position }}</h2>
                  <h4>{{ department.lead.name }}</h4>
                </div>
              </div>
              <div class="linksofmembers">
                <div
                  v-for="(link, index) in department.lead.links"
                  :key="index"
                >
                  <a :href="link.link">
                    <img
                      v-lazy="
                        require(`@/assets/icons/team_icons/${link.image}`)
                      "
                      :alt="link.name"
                    />
                  </a>
                </div>
              </div>
            </div>
          </div>
        </section>

        <section class="second-tier">
          <div v-for="member in department.members" :key="member.name">
            <div class="member">
              <div class="member-image">
                <img
                  v-lazy="
                    require(`@/assets/team images/team-members/${member.image}`)
                  "
                  alt
                />
              </div>

              <div class="details">
                <div class="perse-des-small">
                  <h2>{{ member.position }}</h2>
                  <h4>{{ member.name }}</h4>
                </div>
                <div class="linksofmembers">
                  <div v-for="(link, index) in member.links" :key="index">
                    <a :href="link.link">
                      <img
                        v-lazy="
                          require(`@/assets/icons/team_icons/${link.image}`)
                        "
                        :alt="link.name"
                      />
                    </a>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </section>
      </div>

      <div class="department-heading">
          <div>
            <div class="department-heading-box">
              <h1>TEAM MENTORS</h1>
            </div>
          </div>
        </div>
        <section class="second-tier">
          <div v-for="fmember in fmembers" :key="fmember.name">
            <div class="member">
              <div class="member-image">
                <img
                  v-lazy="
                    require(`@/assets/team images/team-members/${fmember.image}`)
                  "
                  alt
                />
              </div>

              <div class="details">
                <div class="perse-des-small">
                  <h2>{{ fmember.position }}</h2>
                  <h4>{{ fmember.name }}</h4>
                </div>
                <div class="linksofmembers">
                  <div v-for="(link, index) in fmember.links" :key="index">
                    <a :href="link.link">
                      <img
                        v-lazy="
                          require(`@/assets/icons/team_icons/${link.image}`)
                        "
                        :alt="link.name"
                      />
                    </a>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </section>
    </div>
  </main>
</template>
<script>
export default {
  data() {
    return {

      captain: {
        image: "HammadQamar.jpg",
        position: "Captain",
        name: "Hammad Qamar",
        links: [
          {
            name: "insta",
            image: "insta.png",
            link: "https://www.instagram.com/ham_mad_hu_/"
          },
          { name: "email", image: "email.png", link: "mailto:hammadqamar3@gmail.com" },
          { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/hammad-qamar/" }
        ]
      },
      leaders: [
      {
        name: "Asjad Ali Khan",
        position: "Vice-Captain",
        image: "asjad ali khan.jpg",
        links: [
         {
                  name: "insta",
                  image: "insta.png",
                  link:
                    "https://www.instagram.com/asjad_khan_13/"
                },
                { name: "email", image: "email.png", link: "mailto:asjadkhan1303@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/asjad-ali-khan-1877731b3" }
        ]
      },
      { 
        name: "Abdul Samad",
        position: "Team Manager",
        image: "abdul samad.jpeg",
        links: [
          {
            name: "insta",
            image: "insta.png",
            link:
              "#"
          },
          { name: "email", image: "email.png", link: "#" },
          { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/asamadalig/" }
        ]
      }
      ],
      departments: [
        {
          departmentName: "Vehicle Dynamics",
          lead: {
            name: "Hammad Qamar",
            position: "Vehicle Dynamics Lead",
            image: "HammadQamar.jpg",
            links: [
              {
                name: "insta",
                image: "insta.png",
                link: "https://www.instagram.com/ham_mad_hu_/"
              },
              { name: "email", image: "email.png", link: "mailto:hammadqamar3@gmail.com" },
              { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/mwlite/in/hammad-qamar-96602016b" }
            ]
          },
          members: [
            {
              name: "MD Kashif Raza",
              position: "Suspension",
              image: "md kashif raza.jpeg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link:
                    "https://www.instagram.com/kashif.abbas44/"
                },
                { name: "email", image: "email.png", link: "mailto:kashifreza44@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/md-kashif-raza-862649207/" }
              ]
            },
            {
              name: "Abdul Muiz Khan",
              position: "Suspension",
              image: "abdul muiz khan.jpg",
              links: [
                { name: "insta", image: "insta.png", link: "#" },
                { name: "email", image: "email.png", link: "#" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/abdul-muiz-khan-37b073210" }
              ]
            }, 
            {
              name: "Tushar Gupta",
              position: "Suspension",
              image: "tushar gupta.jpg",
              links: [
                { name: "insta", image: "insta.png", link: "#" },
                { name: "email", image: "email.png", link: "#" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/tushar-gupta-amu" }
              ]
            },
              {
              name: "Abu Bakr",
              position: "Steering",
              image: "abu bakr.jpg",
              links: [
                { name: "insta", image: "insta.png", link: "#" },
                { name: "email", image: "email.png", link: "#" },
                { name: "linkedin", image: "linkedin.png", link: "www.linkedin.com/in/abu-bakr-gl9745" }
              ]
            },
             {
              name: "Mohd Moin Khan",
              position: "Brakes",
              image: "mohd moin khan.jpg",
              links: [
                { name: "insta", image: "insta.png", link: "#" },
                { name: "email", image: "email.png", link: "#" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/md-moin-khan-51023b164" }
              ]
            },
             {
              name: "Zulkifle Anwar",
              position: "Brakes",
              image: "zulkifle anwar.jpg",
              links: [
                { name: "insta", image: "insta.png", link: "#" },
                { name: "email", image: "email.png", link: "#" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/zulkifle-anwar-38a988211/" }
              ]
            }
            
            
          ]
        },
        {
          departmentName: "Chassis & Aerodynamics",
          lead: {
            name: "Tazeem Khan",
              position: "Chassis lead",
              image: "Mohd Tazeem Khan.jpg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link:
                    "https://instagram.com/mohammed_tazeem?igshid=167to096kjg8u"
                },
                { name: "email", image: "email.png", link: "mailto:khantazeem12@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/mohammed-tazeem-34b462189" }
              ]
          },
          members: [
            {
              name: "Mohammad Ali Gauhar ",
              position: "Frame",
              image: "137 - 19CEB524 Md Ali Gauhar (1).jpg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link: "https://instagram.com/md_aligauhar?igshid=pdig82i4q4ez"
                },
                { name: "email", image: "email.png", link: "mailto:aligauhar16122000@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "http://www.linkedin.com/in/md-ali-gauhar-ba4219195" }
              ]
            },
            
          ]
        },
        {
          departmentName: "Powertrain",
          lead: {
            name: "Muhammad Aatif Qazi",
              position: "Powertrain Lead",
              image: "IMG_20210217_171704atif - SAE ZHCET.jpg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link: "https://instagram.com/aatif_qazi?igshid=4l70lh37fh7m"
                },
                { name: "email", image: "email.png", link: "mailto:mohammadaatif99.ma@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/aatifqazi" }
              ]
            
          },
          members: [
            {
              name: "Syed Mohmmad Barik",
              position: "Intake",
              image: "syed mohd. barik.jpg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link: "#"
                },
                { name: "email", image: "email.png", link: "#" },
                { name: "linkedin", image: "linkedin.png", link: "linkedin.com/in/syed-barik-804ba91ab" }
              ]
            },
            {
              name: "MD Mobassir Alam",
              position: "Exhaust",
              image: "md mobassir.jpeg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link: "#"
                },
                { name: "email", image: "email.png", link: "#" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/md-mobassir-alam-30980221b" }
              ]
            },
           
          ]
        },
        {
          departmentName: "Electronics",
          lead: {
            name: "Ritik Prabhat",
            position: "Electronics Lead",
            image: "ritik prabhat.jpg",
            links: [
              { name: "insta", image: "insta.png", link: "#" },
              { name: "email", image: "email.png", link: "#" },
              { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/ritik-prabhat-3357b420b" }
            ]
          },
          members: [
            
            // {
            //   name: "Monti Sharma",
            //   position: "Team Member",
            //   image: "IMG_20191125_200046.jpg",
            //   links: [
            //     {
            //       name: "insta",
            //       image: "insta.png",
            //       link:
            //         "https://instagram.com/kcunalsharma?igshid=1ene441cgnfx8"
            //     },
            //     { name: "email", image: "email.png", link: "mailto:kunalsharma.jaipur1999@gmail.com" },
            //     { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/kunal-sharma-b757021a1" }
            //   ]
            // },
            
            {
              name: "Syed Imaduddin",
              position: "Harness",
              image: "syed imamuddin.jpg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link:
                    "#"
                },
                { name: "email", image: "email.png", link: "#" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/syed-imaduddin-227169205/" }
              ]
            },
            // {
            //   name: "Abdul Suboor",
            //   position: "Team Member",
            //   image: "IMG_20191125_200046.jpg",
            //   links: [
            //     {
            //       name: "insta",
            //       image: "insta.png",
            //       link:
            //         "https://instagram.com/kcunalsharma?igshid=1ene441cgnfx8"
            //     },
            //     { name: "email", image: "email.png", link: "mailto:kunalsharma.jaipur1999@gmail.com" },
            //     { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/kunal-sharma-b757021a1" }
            //   ]
            // },
            // {
            //   name: "Sana ",
            //   position: "Team Member",
            //   image: "IMG_20191125_200046.jpg",
            //   links: [
            //     {
            //       name: "insta",
            //       image: "insta.png",
            //       link:
            //         "https://instagram.com/kcunalsharma?igshid=1ene441cgnfx8"
            //     },
            //     { name: "email", image: "email.png", link: "mailto:kunalsharma.jaipur1999@gmail.com" },
            //     { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/kunal-sharma-b757021a1" }
            //   ]
            // },
            {
              name: "Sayeedurahman",
              position: "Sensors",
              image: "sayeedurrahman.jpg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link:
                    "#"
                },
                { name: "email", image: "email.png", link: "#" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/sayeedurrahman-khan-979900171" }
              ]
            }
          ]
        },
        {
          departmentName: "Management",
          lead: {
            name: "Abdul Samad ",
              position: "Management Team Lead",
              image: "abdul samad.jpeg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link:
                    "#"
                },
                { name: "email", image: "email.png", link: "#" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/asamadalig/" }
              ]
          },
          members: [
            
            {
              name: "Salman Ahmad",
              position: "Cost Report",
              image: "Salman.jpg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link: "#"
                },
                { name: "email", image: "email.png", link: "#" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/salman-ahm-" }
              ]
            },
            {
              name: "Arsheen Amir Khan",
            position: "Cost Report",
            image: "arsheen khan.jpeg",
            links: [
              {
                name: "insta",
                image: "insta.png",
                link: "#"
              },
              { name: "email", image: "email.png", link: "mailto:khan.arsheen5@gmail.com" },
              { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/arsheen-a-9b71971ab" }
            ]
            },
            {
              name: "Abid Hasan Zim",
              position: "Management",
              image: "abid hasan.jpg",
              links: [
                { name: "insta", image: "insta.png", link: "#" },
                { name: "email", image: "email.png", link: "#" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/hasan-abid/" }
              ]
            },
             {
              name: "Disha Singh",
              position: "Management",
              image: "DishaSing.jpeg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link: "#"
                },
                { name: "email", image: "email.png", link: "diishasiing@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/diishasiing10122002/" }
              ]
            },
          
          ]
        }
      ],
      fmembers : [
        {
              name: "Yogesh Kumar",
              position: "Chairperson",
              image: "IMG_20191125_200830.jpg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link:
                    "https://instagram.com/invincibleface?igshid=1xwuvvbehip8d"
                },
                { name: "email", image: "email.png", link: "mailto:kryogesh831@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/yogesh-kumar-433414172" }
              ]
            },
        {
               name: "Mohammad Aatif Qazi",
              position: "Team Mentor",
              image: "IMG_20210217_171704atif - SAE ZHCET.jpg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link: "https://instagram.com/aatif_qazi?igshid=4l70lh37fh7m"
                },
                { name: "email", image: "email.png", link: "mailto:mohammadaatif99.ma@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/aatifqazi" }
              ]
            },
            
           
            {
              name: "Meesum Raza Zaidi",
              position: "Team Mentor",
              image: "meesum raza zaidi.jpg",
              links: [
               {
                  name: "insta",
                  image: "insta.png",
                  link:
                    "https://instagram.com/meesumbilgrami?igshid=p2bx6sq11bcf"
                },
                { name: "email", image: "email.png", link: "mailto:meesumbilgrami@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/meesum-raza-zaidi-4375ba195" }
              ]
            },
            {
              name: "Qazi Mohammad Taha",
            position: "Vice Captian FB2020",
            image: "IMG_20191125_201205.jpg",
            links: [
              {
                name: "insta",
                image: "insta.png",
                link: "https://instagram.com/the_qmt?igshid=1rehizz3lyxjx"
              },
              { name: "email", image: "email.png", link: "mailto:qazimdtaha@gmail.com" },
              { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/qazi-t-297392146" }
            ]
            },
           
            {
              name: "Mohd Suboor Aziz",
            position: "Vice Captain FB2021",
            image: "IMG_20191125_200516.jpg",
            links: [
              {
                name: "insta",
                image: "insta.png",
                link: "https://instagram.com/aziz.suboor?igshid=u6gbqw4qva5j"
              },
              { name: "email", image: "email.png", link: "mailto:aziz.ms52090@gmail.com" },
              { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/mohd-suboor-18b594171" }
            ]
            },
            
            {
              name: "Burhan Shamsi",
              position: "Manager FB2021",
              image: "IMG_20191130_011434.jpg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link:
                    "https://instagram.com/__whateverittakes_?igshid=38uj0roq4jfo"
                },
                { name: "email", image: "email.png", link: "mailto:bmdshamsi@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/md-burhan-shamsi-a182b6171" }
              ]
            },
            
            {
              name: "Rehan Abad Siddiqui",
              position: "Team Mentor",
              image: "rehan.jpeg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link: "https://instagram.com/_abadrehan?igshid=kynl9e6k5x9v"
                },
                { name: "email", image: "email.png", link: "mailto:siddiquirehanabad@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/rehan-abad-siddiqui-623868176" }
              ]
            },
            {
              name: "Waris Khan",
              position: "Brakes Lead FB2021",
              image: "IMG_20191130_010441.jpg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link:
                    "https://instagram.com/waris______khan?igshid=12n9s65qrt0pd"
                },
                { name: "email", image: "email.png", link: "mailto:wariskhan1998@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/waris-khan-a40110134/" }
              ]
            },
            {
              name: "Shubham Jain",
              position: "Cost Lead SUPRA 19",
              image: "shubham.jpg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link: "https://instagram.com/mech_hustle?igshid=1h1fw0zzq35l5"
                },
                { name: "email", image: "email.png", link: "maito:shubham.jain.alig@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/shubham-jain-891726144" }
              ]
            },
            
      ]
    };
  }
};
</script>

<style scoped>
main {
  background-color: rgb(35, 34, 34);
  background-size: 100vw 100vh;
  background-attachment: fixed;
  position: relative;
  padding-bottom: 50px;
  padding-top: 1px;
}
main > div {
  border: 5px white ridge;
  margin: 5% 2%;
  margin-top: 8rem;
}
#zfr5 {
  position: relative;
  top: -70px;
}
#top-member {
  margin-top: 0;
  padding-top: 0;
}
.firsttier {
  margin: 30px 0;
  padding: 30px;
  /* border: 2px solid green; */
}
.firsttier > div {
  width: fit-content;
  min-width: 250px;
  max-width: 300px;
  margin: auto;
  transition: transform 300ms;
}
.firsttier > div,
.second-tier > div {
  box-shadow: 0 0 20px 5px rgb(14, 14, 14), inset 0 -1px 0 0 #dadce0;
  border-radius: 12px;
  background: rgb(255, 255, 255);
}
.member {
  margin-top: 10px;
  /* padding: 10px; */
}
.member > div {
  margin: 20px 0;
  text-align: center;
}
.member-image img {
  margin-top: 12px;
  width: 60%;
  border-radius: 20% 20% 20% 20% / 20% 20% 20% 20%;
  box-shadow: 0 0 12px 0px rgb(0, 0, 0);
}
.second-tier {
  margin: 30px 0;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  align-items: center;
  align-content: space-around;
}
.second-tier > div {
  margin: 50px 15px;
  flex-basis: 40% !important;
  min-width: 230px;
  max-width: 260px;
  transition: transform 300ms;
}
.second-tier > div:hover,
.firsttier > div:hover {
  transform: scale(1.1);
}
.linksofmembers {
  margin: 20px 0;
  display: flex;
  justify-content: space-around;
  background-color: rgb(138, 138, 138);
  margin: 0 0 -30px 0;
  border-bottom-right-radius: 12px;
  border-bottom-left-radius: 12px;
  padding: 12px 0;
}
.linksofmembers div a img:hover {
  transform: scale(1.1);
}
.linksofmembers div {
  padding-bottom: 5px;
  transition: border-bottom 300ms;
}
.linksofmembers div:hover {
  border-bottom: 2px solid #330926;
}
.linksofmembers div a img {
  height: 40px;
  border-radius: 50%;
  transition: transform 400ms;
  /* box-shadow: 0 0 5px 0 black; */
}
.perse-des,
.perse-des-small {
  color: rgb(18, 62, 98);
  font-family: Domile;
}
.perse-des h2,
.perse-des-small h2 {
  padding: 1%;
  font-weight: 700;
  border-bottom: 4px ridge black;
  color: #000;
}
.perse-des h2 {
  font-size: 1.8rem;
}
.perse-des h4 {
  font-size: 1.4rem;
}
.perse-des-small h2 {
  font-size: 1.4rem;
}
.perse-des-small h4 {
  font-size: 1.1rem;
}
.department-heading > div {
  padding: 1% 10%;
  color: white;
  font-weight: 800;
  font-family: Roboto;
  text-shadow: #000 4px 3px 3px;
  /* text-decoration: underline white; */
  margin: auto;
  width: 80%;
  border-radius: 12px;
  background-color: #09332a;
}
.department-heading-box {
  border-bottom: 2px ridge white;
  margin: auto;
  width: fit-content;
}
.department-heading-box h1 {
  text-align: center;
}
#zfr5 {
  margin-top: 30px;
}
#zfr5 > div {
  width: 95%;
  background: linear-gradient(45deg, #1f171c, rgb(87, 40, 40), #1f171c);
}
@media screen and (max-width: 991px) {
  main {
    background-color:  rgb(35, 34, 34);
  }
  #zfr5 {
    top: -60px;
  }
  .department-heading-box h1 {
    font-size: 1.5rem;
  }
  .perse-des h2 {
    font-size: 1.6rem;
  }
  .second-tier {
    margin: 8% 0;
  }
  .firsttier {
    margin: 4% 0;
  }
  .perse-des h4 {
    font-size: 1.2rem;
  }
}
</style>