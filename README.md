<h1>Análises de Incidentes: Ataque DDoS com SYN Flood</h1>
<h2>Cenário</h2>
Como analista de segurança em uma agência de publicidade, identifiquei e respondi a um ataque de negação de serviço (DDoS) direcionado ao servidor da Web da empresa. Este documento detalha o incidente realizada, as medidas imediatas adotadas e os passos recomendados para prevenir ataques futuros.

<h2> Descrição do Problema</h2>
<h3>Situação Inicial</h3>
<ul>
  <li> Funcionários da empresa relataram indisponibilidade do site da empresa.</li>
  <li> Alerta gerado automaticamente pelo sistema de monitoramento indicando falhas no servidor.</li>
</ul>
<h3>Sintomas Observados</h3>
  <ul>
    <li>Mensagem de erro "Pausa na conexão" ao acessar o site.</li>
    <li>Alta taxa de pacotes de solicitação TCP SYN de um endereço IP desconhecido.</li>
    <li> Servidor sobrecarregado, incapaz de responder adequadamente ao tráfego legítimo.</li>
  </ul>

  <h2>Diagnóstico</h2>
  <h3>Causa Identificada</h3>
  <ul>
    <li> O servidor foi alvo de um ataque SYN Flood, caracterizado por um número elevado de solicitações TCP SYN enviadas ao servidor, que não eram concluídas, consumindo recursos e impedindo novas conexões.</li>
  </ul>
  <h3>Impacto ao Ataque</h3>
  <b>1. Servidor da Web</b>
  <ul>
    <li> Indisponibilidade temporária para funcionários e clientes.</li>
    <li> Sobrecarga de recursos devido ao tráfego anormal.</li>
  </ul>
  <b>2. Funcionários</b>
  <ul>
    <li> Impossibilidade de acessar a página de vendas para pesquisas.</li>
    <li> Interrupção das atividades relacionadas à promoção de pacotes de férias.</li>
  </ul>

  <h2>Ações Imediatas</h2>
  <b>1. Mitigação Inicial</b>
  <ul>
    <li>Coloquei o servidor temporariamente <b>off-libe</b> para interromper o ataque e permitir a recuperação do sistema.</li>
  </ul>
  <b>2. Análise do Tráfego de Rede</b>
  <ul>
    <li>Usei um <b>sniffer de pacotes</b> para capturar e examinar os dados em trânsito.</li>
    <li>Identifiquei um <b>endereço IP malicioso</b> comoo fonte de um alto volume de solicitações SYN.</li>
  </ul>
  <b>3. Configuração de Firewall</b>
  <ul>
    <li>Configurei o firewall para bloquear o endereço IP malicioso.
      </li>
  </ul>
  <h2>Limitações da Resposta Inicial</h2>
  Embora o bloqueio do IP tenha mitigado temporariamente o ataque, reconheço que:
  <ul>
    <li>O ataque pode usar <b>IP spoofing</b> para mascarar outros endereços IP.</li>
    <li>A solução imediata não resolve a vulnerabilidade subjacente.</li>
  </ul>

  <h2>Recomendações para Prevenção Futura</h2>
  <b>1. Implementar Medidas de Proteção Avançadas:</b>
  <ul>
    <li><b>Habilitar SYN Cookies</b> no servidor para verificar conexões legítimas.</li>
    <li>Configurar <b>limites da taxa de conexão</b> no firewall para evitar sobrecargas.</li>
  </ul>
  <b>2. Monitoramento Contínuo:</b>
  <ul>
    <li>Implantar sistemas de detecção e prevenção de intrusão (IDS/IPS).</li>
    <li>Monitorar regularmente padrões de tráfego para identificar anomalias.</li>
  </ul>
  <b>3. Uso de Serviços de Mitigação DDoS:</b>
  <ul>
    <li>Considerar soluções em nuvem especializadas em mitigação de ataques DDoS.</li>
  </ul>
  <b>4. Treinamento e Planejamento:</b>
  <ul>
    <li>Treinar a equipe de TI para responder rapidamente a ataques semelhantes.</li>
    <li>Criar um plano de resposta a incidentes documentado e testado regularmente.</li>
  </ul>

  <h2>Resumo Técnico</h2>
  <ul>
    <li><b>Tipo de ataque:</b>DDoS (SYN Flood)
    <b>Ferramentas usadas:</b>Sniffer de pacotes, Firewall
    </li>
  </ul>
