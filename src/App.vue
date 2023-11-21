<template>
  <header>
    <nav>
      <h1 class="titulo">SF <span>sistemas</span></h1>
      <div class="navlinks">
        <a href="#home" class="navlink">Home</a>
        <a href="#produto" class="navlink">Produto</a>
        <a href="#quem-somos" class="navlink">Empresa</a>
        <a href="#clientes" class="navlink">Portfólio</a>
        <a href="#localizacao" class="navlink">Localização</a>
        <a href="#contato" class="navlink">Fale Conosco</a>
      </div>
      <input v-model="open" type="checkbox" id="checkbox" class="checkbox" />
      <label for="checkbox" class="label-menu">
        <a id="hamburger">
          <v-icon icon="fa-solid fa-bars"></v-icon>
        </a>
      </label>
      <div id="menu-lateral" @click.stop>
        <div id="container-links__menu-lateral">
          <a href="#home" class="navlink">Home</a>
          <a href="#produto" class="navlink">Produto</a>
          <a href="#quem-somos" class="navlink">Empresa</a>
          <a href="#clientes" class="navlink">Portfólio</a>
          <a href="#localizacao" class="navlink">Localização</a>
          <a href="#contato" class="navlink">Fale Conosco</a>
        </div>
      </div>
    </nav>
  </header>
  <body>
    <main>
      <div id="home">
        <div class="conteudo-home">
          <h1>Soluções sistêmicas para sua empresa</h1>
          <h3>
            A SF Sistemas é uma empresa com
            <strong
              >soluções sistêmicas para facilitar a gestão da sua
              empresa</strong
            >
            de forma prática, fácil, com ótima relação custo benefício, aliando
            sempre a qualidade e profissionalismo
          </h3>
        </div>
      </div>
      <div id="produto">
        <h1>Módulo do sistema SAFI</h1>
        <div class="produtos">
          <div class="produtos_esquerda">
            <card-produto
              v-for="produto in produtos_esquerda"
              :key="produto.titulo"
              :conteudo="produto.conteudo"
              :header="produto.header"
            />
          </div>
          <div class="produtos_direita">
            <card-produto
              v-for="produto in produtos_direita"
              :key="produto.titulo"
              :conteudo="produto.conteudo"
              :header="produto.header"
            />
          </div>
        </div>
      </div>
      <div id="quem-somos">
        <h1>Quem somos</h1>
        <p>
          Somos uma empresa que desenvolve sistemas para atender aos segmentos
          de Comércio Varejista, Prestação de Serviços e pequenas indústrias.
        </p>
        <p>
          Por ser de simples operação com telas padronizadas, diminui-se o tempo
          de treinamento e consequentemente os resultados ocorrem mais
          rapidamente.
        </p>
        <p>
          O sistema assegura a emissão de documentos eletrônicos cumprindo
          rigorosamente a legislação das Secretarias de Fazenda mantendo-se
          sempre atualizado.
        </p>
        <p>
          Os recursos de análise gerencial possibilitam ao gestor uma visão
          completa do ciclo de atendimento, facilitando a tomada de decisões
          corretas pois, possui todas as informações comerciais, financeiras,
          produtivas em uma única ferramenta no momento necessário para tornar o
          seu negócio mais lucrativo.
        </p>
        <p>
          Com o SAFI ganhe velocidade e competitividade, diminuindo o tempo de
          execução e aumentando a produtividade da equipe.
        </p>
      </div>
      <div id="clientes">
        <h1>Clientes</h1>
        <div class="clientes">
          <img
            v-for="cliente in clientes"
            :key="cliente.link"
            :src="cliente.link"
            :alt="cliente.alt"
            class="cliente"
          />
        </div>
      </div>
      <div id="localizacao">
        <iframe
          src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3738.064228223536!2d-54.62889962664127!3d-20.462555008080212!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x9486e639244f765d%3A0xaf88eb95aa7dc631!2sR.%20Mal.%20Rondon%2C%20332%20-%20Centro%2C%20Campo%20Grande%20-%20MS%2C%2079008-001!5e0!3m2!1spt-BR!2sbr!4v1700586780803!5m2!1spt-BR!2sbr"
          width="600"
          height="450"
          style="border: 0"
          allowfullscreen=""
          loading="lazy"
          referrerpolicy="no-referrer-when-downgrade"
        ></iframe>
      </div>
      <div id="contato">
        <div class="contato">
          <h1>Entre em contato conosco</h1>
          <p>
            Se você quer contratar ou saber mais sobre as nossas soluções, envie
            seus dados com a mensagem que entraremos em contato. Desde já
            agradecemos pelo preenchimento do formulário.
          </p>
          <v-container class="form">
            <v-row>
              <v-col cols="12">
                <v-text-field
                  type="string"
                  v-model="contato.nome"
                  :error-messages="
                    v$.contato.nome.$errors.map((e) => e.$message)
                  "
                  counter="255"
                  label="Nome completo"
                  @input="v$.contato.nome.$touch"
                  @blur="v$.contato.nome.$touch"
                ></v-text-field>
              </v-col>
            </v-row>
            <v-row>
              <v-col cols="12">
                <v-text-field
                  type="email"
                  v-model="contato.email"
                  :error-messages="
                    v$.contato.email.$errors.map((e) => e.$message)
                  "
                  counter="255"
                  label="E-mail"
                  @input="v$.contato.email.$touch"
                  @blur="v$.contato.email.$touch"
                ></v-text-field>
              </v-col>
            </v-row>
            <v-row>
              <v-col cols="12">
                <v-text-field
                  type="string"
                  v-model="contato.telefone"
                  :error-messages="
                    v$.contato.telefone.$errors.map((e) => e.$message)
                  "
                  label="Telefone"
                  @input="v$.contato.telefone.$touch"
                  @blur="v$.contato.telefone.$touch"
                ></v-text-field>
              </v-col>
            </v-row>
            <v-row>
              <v-col cols="12">
                <v-text-field
                  type="string"
                  v-model="contato.assunto"
                  :error-messages="
                    v$.contato.assunto.$errors.map((e) => e.$message)
                  "
                  counter="255"
                  label="Assunto"
                  @input="v$.contato.assunto.$touch"
                  @blur="v$.contato.assunto.$touch"
                ></v-text-field>
              </v-col>
            </v-row>
            <v-row>
              <v-col cols="12">
                <v-textarea
                  label="Mensagem"
                  v-model="contato.mensagem"
                ></v-textarea>
              </v-col>
            </v-row>
            <v-row>
              <v-btn
                variant="tonal"
                color="primary"
                class="ml-auto"
                @click="envio"
                >Enviar</v-btn
              >
            </v-row>
          </v-container>
        </div>
      </div>
    </main>
  </body>
  <footer>
    <div class="logradouro">
      <p class="endereco">R. Mal Candido Mariano, 332 - 1º Andar - Sala 2</p>
      <p class="cidade">Campo Grande - MS</p>
    </div>
    <p class="telefone">(67) 3382-4080</p>
    <p class="email">comercial@sfsistemas.com</p>
  </footer>
  <voltar-inicio />
</template>

<script>
import CardProduto from "./components/CardProduto.vue";
import VoltarInicio from "./components/VoltarInicio.vue";
import { helpers, required, maxLength, email } from "@vuelidate/validators";
import { useVuelidate } from "@vuelidate/core";
export default {
  components: {
    CardProduto,
    VoltarInicio,
  },
  data() {
    return {
      produtos_esquerda: [
        {
          header: {
            imagem: {
              link: "https://i.ibb.co/MBDj3YC/imagem-2023-11-21-110204171.png",
              alt: "Imagem com uma caneta e um papel simbolizando a rotina de cadastros dentro do sistemas",
            },
            titulo: "Cadastros",
          },
          conteudo:
            "Módulo de inserção de dados básicos no ERP, como empresas, clientes, fornecedores, produtos, centros de custos entre outras informações utilizadas nos demais módulos.",
        },

        {
          header: {
            imagem: {
              link: "https://i.ibb.co/vvsCrL1/image.png",
              alt: "Imagem de uma caixa com uma seta apontada para baixo no canto inferior esquerdo simbolizando a rotina de estoque",
            },
            titulo: "Estoque",
          },
          conteudo:
            "Controle de estoque por local, inventário, ajustes, transferências, emissão de etiquetas, rastreabilidade de produtos, controle de ponto de reposição. Telas práticas e funcionais que permitem analisar rapidamente a movimentação e dados fiscais e cadastrais do produto.",
        },

        {
          header: {
            imagem: {
              link: "https://i.ibb.co/swWk5YW/3-compras.png",
              alt: "Imagem de um carrinho de compras para simbolizar a rotina de compras",
            },
            titulo: "Compras",
          },
          conteudo:
            "Neste módulo temos funcionalidades para controle de fluxo de compras tais como: pedido de compra, entrada de notas (digitado e XML) com integração financeira e estoque. O sistema controla os pedidos com entrada parcial e total, permite uma analise criteriosa para formação de preços considerando todas as variáveis para simulação e definição do preço de acordo com a lucratividade desejada. Apura os custos das mercadorias tais como: custo médio, CMV, custo de compra, entre outros. Oferece vários relatórios relacionados a Compras.",
        },

        {
          header: {
            imagem: {
              link: "https://i.ibb.co/DD5vdV4/4-vendas.png",
              alt: "Imagem de duas pilhas de moedas uma ao lado da outra com um simbolo de porcentagem no canto superior direito simbolizado a rotina de vendas",
            },
            titulo: "Vendas",
          },
          conteudo:
            "O sistema permite o gerenciamento completo do processo de vendas, desde o orçamento, separação e faturamento, além de cobrir todo o processo operacional. No momento da venda é possível analisar a lucratividade e desta forma fornecer parâmetros para permitir uma negociação mais segura e rápida. Outros recursos do módulo: controle de comissões, limite de crédito, formação de tabela de preços, promoções, permissão de descontos, controle de vendas com entrega futura, entre outros.",
        },

        {
          header: {
            imagem: {
              link: "https://i.ibb.co/xqLZzrx/5-gerenciamento-notafiscal-eletronica.png",
              alt: "Imagem de uma folha de papel com linhas ao centro e um simbolo de cifrão no canto superior direito para simbolizar a rotina de gerenciamento de nota fiscal eletrônica",
            },
            titulo: "Gerenciamento de Nota Fiscal Eletrônica",
          },
          conteudo:
            "Módulo responsável pelo gerenciamento de envio e manutenção da Nota Fiscal Eletrônica (Cancelamento, Reenvio, Inutilização, DANFE, Carta de Correção, entre outros).",
        },
      ],
      produtos_direita: [
        {
          header: {
            imagem: {
              link: "https://i.ibb.co/7vXLcB8/imagem-2023-11-21-113453068.png",
              alt: "Imagem com uma mão e uma engrenagem dentro da mão para simbolizar a rotina de ordem de serviços",
            },
            titulo: "Ordem de Serviço",
          },
          conteudo:
            "Destinado a controlar os processos da Ordem de Serviço desde a sua abertura até o faturamento. De forma bem prática o sistema permite informar dados específicos para veículo e/ou equipamentos. Permite o controle de produtividade por técnico, estoque, serviço, financeiro e relatórios.",
        },
        {
          header: {
            imagem: {
              link: "https://i.ibb.co/mbKJfWh/image.png",
              alt: "Imagem com uma calculadora, uma folha atrás com ticks verdadeiros no papel e um lápis ao lado simbolizando a rotina de financeiro",
            },
            titulo: "Financeiro",
          },
          conteudo:
            "Contas a pagar, contas a receber, conciliação bancária, cobrança eletrônica, controle de cheques e recibos, descontos de títulos entre outros processos da área financeira.",
        },
        {
          header: {
            imagem: {
              link: "https://i.ibb.co/c6bWYBK/8-caixa.png",
              alt: "Imagem de uma máquina registradora para simbolizar a rotina do caixa",
            },
            titulo: "Caixa",
          },
          conteudo:
            "Permite o recebimento de pré-vendas, vendas direto no caixa, operações inerentes a caixa (abertura, sangria, suprimentos, fechamento) procedimentos fiscais (Cupom Fiscal e NFC-e), recebimento de títulos entre outros.",
        },
        {
          header: {
            imagem: {
              link: "https://i.ibb.co/McmTC55/9-controles-gerenciais.png",
              alt: "Imagem de uma engrenagem com um boneco dentro simbolizando a rotina de controles gerenciais",
            },
            titulo: "Controles Gerenciais",
          },
          conteudo:
            "Fluxo de Caixa, Fluxo Financeiro, Resultado Operacional, Razão de Resultado Operacional, Painel Financeiro.",
        },
        {
          header: {
            imagem: {
              link: "https://i.ibb.co/M88z37Z/10-producao.png",
              alt: "Imagem de uma industria para simbolizar a rotina de produção",
            },
            titulo: "Produção",
          },
          conteudo:
            "Ficha Técnica de Produto, Ordem de Produção, Informe de Produção, processamento das Ordens (Baixa de matérias primas e embalagens, entrada de produto acabado no estoque conforme quantidade produzida), apuração do custo do produto acabado, permite informar lote e validade nos produtos e relatórios inerentes a produção.",
        },
        {
          header: {
            imagem: {
              link: "https://i.ibb.co/dbSMf8v/11-logistica.png",
              alt: "Imagem de dois caminhões rodeando o globo simbolizando a rotina de logistica",
            },
            titulo: "Logística",
          },
          conteudo:
            "Romaneio, Montagem de Rota, Controle de Viagem e Faturamento.",
        },
        {
          header: {
            imagem: {
              link: "https://i.ibb.co/tYchM86/12-emprestimo.png",
              alt: "Imagem de uma mão com uma moeda dentro para simbolizar a rotina de empréstimo",
            },
            titulo: "Empréstimo",
          },
          conteudo: "Controle de empréstimos para empresas de Factoring.",
        },
        {
          header: {
            imagem: {
              link: "https://i.ibb.co/F4JVMDX/13-arquivos-fiscais.png",
              alt: "Imagem de uma folha com dados dentro e uma moeda no canto inferior direito para simbolizar a rotina de arquivos fiscais",
            },
            titulo: "Arquivos Fiscais",
          },
          conteudo:
            "Geração de arquivos para atender obrigações acessórias como SINTEGRA, SPED FISCAL e SPED CONTRIBUIÇÕES, EFD Pis/Cofins.",
        },
      ],
      clientes: [
        {
          link: "https://i.ibb.co/q5jNPff/1-Pax-nacional-logo.png",
          alt: "Logo da Pax Nacional",
        },
        {
          link: "https://i.ibb.co/t4jVw8J/2-H-T-logo.png",
          alt: "Logo da H & T",
        },
        {
          link: "https://i.ibb.co/GFR2ZK6/3-Calderan-logo.png",
          alt: "Logo da Calderan",
        },
        {
          link: "https://i.ibb.co/vXNYfH8/4-Obraativa-logo.png",
          alt: "Logo da Obrativa",
        },
        {
          link: "https://i.ibb.co/cb2cZcd/5-Ping-logo.png",
          alt: "Logo da Ping",
        },
        {
          link: "https://i.ibb.co/yN5gZLq/6-Mafisa-logo.png",
          alt: "Logo da Mafisa",
        },
      ],
      contato: {
        nome: "",
        telefone: "",
        email: "",
        assunto: "",
        mensagem: "",
      },
      open: false,
    };
  },
  setup() {
    return {
      v$: useVuelidate(),
    };
  },
  methods: {
    fechaMenuLateral() {
      this.open = false;
    },
    async envio() {
      if (await this.v$.contato.$validate()) {
        const mensagem = encodeURI(
          `Olá 😊.$Meu nome é *${this.contato.nome}* e fiquei interessado no seu produto.$✉️ = *${this.contato.email}*.$📱 = *${this.contato.telefone}*.$🤔 = *${this.contato.assunto}*.$💬 = *${this.contato.mensagem}*`
        );

        window.open(
          `https://api.whatsapp.com/send?phone=5567999832455&text=${mensagem.replaceAll(
            "$",
            "%0D"
          )}`
        );
      }
    },
  },
  created() {
    window.addEventListener("click", this.fechaMenuLateral);
  },
  destroy() {
    window.removeEventListener("click", this.fechaMenuLateral);
  },
  validations() {
    return {
      contato: {
        nome: {
          required: helpers.withMessage(
            "O campo de nome completo e obrigatorio.",
            required
          ),
          maxLength: helpers.withMessage(
            "O nome completo deve conter ate 255 caracteres",
            maxLength(255)
          ),
        },
        email: {
          required: helpers.withMessage(
            "O campo de email e obrigatorio.",
            required
          ),
          maxLength: helpers.withMessage(
            "O email deve conter ate 255 caracteres",
            maxLength(255)
          ),
          email: helpers.withMessage("O email e invalido.", email),
        },
        telefone: {
          required: helpers.withMessage(
            "O campo de telefone é obrigatorio.",
            required
          ),
        },
        assunto: {
          required: helpers.withMessage(
            "O campo de assunto e obrigatorio.",
            required
          ),
          maxLength: helpers.withMessage(
            "O assunto deve conter ate 255 caracteres",
            maxLength(255)
          ),
        },
      },
    };
  },
};
</script>

<style scoped>
html {
  overflow-y: scroll;
  scroll-behavior: smooth;
}

/* Navbar */

nav {
  background-color: var(--darkblue);
  display: flex;
  align-items: center;
  justify-content: space-evenly;
  height: 5vh;
}
.navlinks {
  display: flex;
  gap: 2rem;
}

.navlink {
  font-family: DM Sans, sans-serif;
  font-weight: 300;
  text-decoration: none;
  color: white;
  transition: 0.5s;
}

.navlink:hover {
  color: var(--sistemas);
}

.titulo {
  font-family: Nunito, sans-serif;
  font-weight: 700;
  color: white;
}

.titulo span {
  color: var(--sistemas);
}

/* Home */

#home {
  background-image: linear-gradient(
    90deg,
    rgba(255, 255, 255, 1) 0%,
    rgba(37, 136, 194, 0.8365721288515406) 15%,
    rgba(37, 136, 194, 0.8365721288515406) 75%
  );
  height: 95vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.conteudo-home {
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 4rem;
  width: 50%;
  color: white;
}

.conteudo-home h1 {
  font-family: Poppins, sans-serif;
  font-weight: 700;
  font-size: 58px;
  width: 80%;
}

.conteudo-home h3 {
  font-family: Poppins, sans-serif;
  font-weight: 300;
  font-size: 24px;
  width: 75%;
}

.conteudo-home h3 strong {
  font-weight: 700;
}

/* Produtos */

#produto {
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 2rem;
  margin-bottom: 1rem;
}

#produto h1 {
  color: var(--sistemas);
  font-family: DM Sans, sans-serif;
  font-weight: 300;
  font-size: 78px;
}

.produtos {
  display: flex;
  width: 60%;
  gap: 4rem;
}

.produtos_direita,
.produtos_esquerda {
  display: flex;
  flex-direction: column;
  width: 50%;
  gap: 1rem;
}

/* Quem somos */

#quem-somos {
  background-color: #0e1c29;
  color: white;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 3rem;
  padding: 2rem 0;
}

#quem-somos p {
  width: 60%;
  font-family: DM Sans, sans-serif;
  font-size: 24px;
}

/* Clientes */

#clientes {
  background-color: #0e1c29;
  padding: 4rem 0;
}

#clientes h1 {
  text-align: center;
  padding-bottom: 4rem;
  color: white;
  font-family: DM Sans, sans-serif;
  font-weight: 500;
  font-size: 32px;
}

.clientes {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  grid-gap: 16px;
  place-items: center;
}

/* Localização */

#localizacao iframe {
  width: 100%;
}

/* Contato */

#contato {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 3rem 0;
  width: 100%;
}

.contato {
  width: 50%;
  font-family: DM Sans, sans-serif;
}

/* Footer */

footer {
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  background-color: #0e1c29;
  height: 10vh;
  color: white;
}

/* Mobile */

.label-menu,
.checkbox,
#menu-lateral {
  display: none;
}

@media screen and (max-width: 950px) {
  .conteudo-home h1 {
    font-size: 36px;
  }

  .conteudo-home h3 {
    font-size: 15px;
  }

  #produto h1 {
    font-size: 39px;
  }

  .produtos {
    flex-direction: column;
    align-items: center;
    width: 80%;
  }

  .contato {
    width: 80%;
    font-family: DM Sans, sans-serif;
  }

  .produtos_direita,
  .produtos_esquerda {
    width: 80%;
  }

  footer {
    font-size: 8px;
  }
}

@media screen and (max-width: 800px) {
  nav {
    position: unset;
    top: 0;
    left: 0;
    width: 100%;
    height: 75px;
    align-items: center;
  }

  .navlinks {
    display: none;
  }

  .label-menu {
    display: block;
  }

  #menu-lateral {
    display: flex;
    flex-direction: column;
    width: 0;
    height: 100%;
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    background-color: var(--darkblue);
    z-index: 20;
    gap: 5.625rem;
    transition: 0.5s;
    overflow-x: hidden;
  }

  #hamburger,
  #close {
    font-size: 26px;
    color: #ffffff;
  }

  .checkbox:checked ~ #wrapper__menu-lateral {
    width: 100vw;
  }

  .checkbox:checked ~ #menu-lateral {
    width: calc(100vw / 2);
  }

  #wrapper__menu-lateral {
    height: 100vh;
    width: 0;
    position: absolute;
    top: 0;
    right: 0;
    z-index: 19;
  }

  .navlink {
    margin-inline: 1rem;
    border-bottom: 0.0625rem solid #4e4e4e;
    width: 80%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    color: white;
    padding: 1rem;
    font-family: DM Sans, sans-serif;
    font-size: 1rem;
    font-weight: 700;
  }
}
</style>