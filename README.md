# Curso_JavaScript
Curso JavaScript




// import React from 'react';
// import CardUsuario from './CardUsuario';
// import Comentario from './Comentario';
// import Painel from './Painel';
// import Produto from './Produto';     
// import ListaProdutos from './ListaProduto';
// import Box from './Box';
// import Divider from './Divider';
// import Steps from './Steps';
// import Input from './Input';
// import Button from './Button';
// import Textarea from './Textarea';


// const App: React.FC = () => {
//   return (
//     // <div style={{ padding: '2rem' }}>
//     //   <h1>Usuários</h1>
//     //   <CardUsuario nome="Alice" tipoUsuario="admin" />
//     //   <CardUsuario nome="Bruno" tipoUsuario="visitante" />
//     //   <CardUsuario nome="Carla" tipoUsuario="editor" />

//     //   <h1>Comentários</h1>
//     //   <Comentario autor="Alice" revisado>
//     //     <p>Esse conteúdo está muito bem explicado. Parabéns!</p>
//     //   </Comentario>

//     //   <Comentario autor="Bruno" revisado={false}>
//     //     <p>Gostei do artigo, mas acho que faltou um exemplo prático.</p>
//     //   </Comentario>

//     //   <Comentario autor="Carla" revisado>
//     //     <p>Excelente abordagem sobre o tema. Me ajudou bastante!</p>
//     //   </Comentario>

      
//     //   <div style={{ padding: '1rem' }}>
//     //   <h1>Painéis</h1>
        
//     //   <Painel titulo="Boas vindas">
//     //     <p>Bem-vindo ao nosso site! Aqui você encontrará diversas informações úteis.</p>
//     //     <p>Este é um painel que contém informações importantes.</p>
//     //     <p>
//     //     </p>
//     //   </Painel>
      
//     //   <Painel titulo="Lista de tarefas">

//     //     <ul>
//     //       <li>Estudar React</li>
//     //       <li>Estudar JavaScript</li>
//     //       <li>Praticar TypeScript</li>
//     //       <li>Realizar alguns projetos</li>
//     //       <li>Contribuir com projetos open source</li>
//     //     </ul>
//     //   </Painel>

      
//     //   <h1>Produtos</h1>
//     //     <ListaProdutos produtos={[
//     //         { nome: 'Produto 1', preco: 29.99, emEstoque: true },
//     //         { nome: 'Produto 2', preco: 49.99, emEstoque: false },
//     //         { nome: 'Produto 3', preco: 19.99, emEstoque: true },
//     //       ]}
//     //     />  


      
//     //   </div>

//     // </div>

//     <div>
      


//       <Box>
//         <Steps 
//         steps={[
//           {nome: "Contato", ordem: 1 },
//           {nome: "Empresa", ordem: 2 },
//           {nome: "Projeto", ordem: 3 },
//         ]}
//         />

//         <Divider/>
        

// <form style={{ display: 'flex', flexDirection: 'column', gap: 20, marginTop: 24 }}>
//         <Input  />
//         <Input />
//         <Input />
        
// </form>
//       </Box>
      
//       </div>
//   );
// };

// export default App;

import Box from "./components/Box";
import Button from "./components/Button";
import Divider from "./components/Divider";
import Input from "./components/Input";
import Steps from "./components/Steps";
import Textarea from "./components/Textarea";

function App() {
  const [passoAtual, setPassoAtual] = useState(1);
  
  return (
    <div
      style={{
        display: "flex",
        alignItems: "center",
        justifyContent: "center",
        height: "100vh",
      }}
    >
      <Box>
        <Steps
          steps={[
            { nome: "Contato", ordem: 1 },
            { nome: "Empresa", ordem: 2 },
            { nome: "Projeto", ordem: 3 },
          ]}
        />

        <Divider />

        <form
          style={{
            display: "flex",
            flexDirection: "column",
            gap: 24,
            marginTop: 24,
          }}
        >

          {passoAtual === 1 && (
            <>
              <Input label="Nome" placeholder="Digite seu nome" />
              <Input label="Telefone" placeholder="Digite seu telefone" />
              <Input label="Email" placeholder="Email" />
            </>
          )}

          {passoAtual === 2 && (
            <>
              <Input
                label="Nome da Empresa"
                placeholder="Informe o nome da empresa"
              />
              <Input
                label="Nº de Funcionários"
                placeholder="Informe o número de funcionários"
              />
            </>
          )}

          {passoAtual === 3 && (
            <Textarea
              label="Sobre o negócio"
              placeholder="Fale um pouco sobre o negócio"
              ehExpandivel={false}
            />
          )}

          <Textarea
            label="Objetivo do Projeto"
            placeholder="Descreva quais são os objetivos do projeto"
            ehExpandivel={false}

          {/* Uncomment the following lines if you want to include the textarea for project objectives */}
          {/* <textarea 
            label ="Objetivo do Projeto" 
            placeholder="Descreva quais são os objetivo do projeto"
            ehExpandivel={false}
          {/*
          
          <Input label="Nome" placeholder="Digite seu nome" />
          <Input label="Telefone" placeholder="Digite seu telefone" />
          <Input label="Email" placeholder="Email" /> */}

          {/* <Input
            label="Nome da Empresa"
            placeholder="Informe o nome da empresa"
          />
          <Input
            label="Nº de Funcionários"
            placeholder="Informe o número de funcionários"
          />

          <Textarea
            label="Sobre o negócio"
            placeholder="Fale um pouco sobre o negócio"
            ehExpandivel={false}
          /> */}

        {/* <textarea 
        label ="Objetivo do Projeto" 
        placeholder="Descreva quais são os objetivo do projeto"
        ehExpandivel={false}
     /> */}

          <div
            style={{
              display: "flex",
              // justifyContent: "space-between",
              width: "100%",
            }}
          >
            {/* <Button textoBtn={"Voltar"} /> */}
            <div style={{ alignSelf: "flex-end" }}>
              <Button textoBtn={"Continuar"} onClick={() => console.log("entrou aqui")} />
            </div>
          </div>
        </form>
      </Box>
    </div>
  );
}

export default App;
