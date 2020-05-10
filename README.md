Gustavo Henrique Gomes Silva - 31623061
João Pedro Ruas Ferreira – 31818772
Mateus Pereira de Sá - 318127864
Matheus Augusto Silva de Morais Ramos – 318117417
Rodolfo Joarley de Oliveira - 318118181

Escolhemos o site da empresa Take que oferece soluções e serviços para solucionar comunicações entre a empresa e o cliente. 

Escolhemos Vagas (que são as vagas da empresa que estão sendo disponibilizadas no momento) do site da empresa.


<a class="job job__row" id="job-476395" href="/o/developer-220">          
        <div class="job__column job__column--title">
            <h5 class="title">
              Developer            </h5>
          </div>
          <div class="job__column job__column--meta">
            <span class="location">
              BH, Brasil            </span>
                          <span class="department-field">
                Plataforma              </span>
                      </div>
          <div class="job-data hidden">
            <div class="department">
              Plataforma            </div>
            <div class="city">
              BH            </div>
            <div class="state">
              Minas Gerais            </div>
            <div class="country">
              Brasil            </div>
            <div class="language">
              ["pt"]            </div>
            <div class="tag">
              []            </div>
          </div>
        </a>


Titulo: a.job job__row/div.jobcolumn job__column—title/h5.title
Localização: a.job job__row/div.jobcolumn job__column—meta/span.location
Departamento: a.job job__row/div.jobcolumn job__column—meta/span.department-field
Departamento: a.job job__row/div.job-data hidden/div.department
Cidade: a.job job__row/div.job-data hidden/div.city
Estado: a.job job__row/ div.job-data hidden/div.state
Pais: a.job job__row/div.job-data hidden/div.country
Idioma: a.job job__row/div.job-data hidden/div.language

Título: Developer
Localização: BH, Brasil
Data: Plataforma
Cidade: BH
Estado: Minas Gerais
País: Brasil
Idioma: [“pt”]

import scrapy


class VagasSpider(scrapy.Spider):
    name = 'vagas'
    start_urls = ['https://take1.recruitee.com/']

    def parse(self, response):
        for citacao in response.css("div.jobs-container"):
            yield {
                "title": citacao.css("h5.title::text").get(),
                "location": citacao.css("span.location::text").get(),
                "data": citacao.css("div.department::text").get(),
                "city": citacao.css("div.city::text").get(),
                "state": citacao.css("div.state::text").get(),
                "country": citacao.css("div.country::text").get(),
                "language": citacao.css("div.language::text").get(),

            }






