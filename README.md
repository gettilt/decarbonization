<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(f"# {config['name'].title()}")
]]]-->
# Decarbonization
<!--//[[[end]]]-->

## Mission

Tilt's mission is to map every theme to a basket of stocks for anyone to invest in. Mappings are AI generated and expert curated.
Expert improvements are accepted if they provide a better representation of a given theme.

## Theme Prompt
<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(config['prompt'])
]]]-->
Heavy industry decarbonization. 20-25% of global emissions comes from heavy industry (cement, fertilizer, refiners) and they need to reduce emissions. Green companies and companies that create economically viable ways to reduce emissions.
<!--[[[end]]]-->

## Theme Stocks

<!--[[[cog
import cog
import csv
import json

with open('context.json') as file:
  contexts = json.load(file)

def _get_context_str_for_ticker(ticker):
  try:
    context = contexts[ticker]
    context_str = context['chat_gpt'] or context['claude'] or ""
  except KeyError:
    context_str = ""

  return context_str

cog.outl("| Ticker  | Context | Source |")
cog.outl("| ------- | ---- | ---- |")

with open('theme.csv') as file:
  reader = csv.reader(file)
  next(reader) # skip the header
  for row in reader:
    context_str = _get_context_str_for_ticker(row[0])
    cog.outl(f"| {row[0]} | {context_str} | {row[1]} |")
]]]-->
| Ticker  | Context | Source |
| ------- | ---- | ---- |
| LIN | Linde is a global leader in industrial gases, including hydrogen, which is essential for decarbonizing heavy industries. | chat_gpt |
| BLDP | Ballard Power Systems develops fuel cell technology for heavy-duty applications, offering a zero-emission alternative for industrial processes. | chat_gpt,claude |
| ENPH | Enphase Energy provides advanced solar energy solutions, which can help heavy industries transition to renewable energy sources. | chat_gpt,claude |
| FSLR | First Solar manufactures solar panels, supporting the adoption of renewable energy in heavy industries. | chat_gpt,claude |
| BE | Bloom Energy offers solid oxide fuel cell technology, which can provide clean and efficient energy for industrial applications. | chat_gpt,claude |
| PLUG | Plug Power specializes in hydrogen fuel cell technology, which can be used to power heavy industrial processes with zero emissions. | chat_gpt,claude |
| CAT | Caterpillar is investing in sustainable technologies for heavy machinery, which can help reduce emissions in construction and mining industries. | chat_gpt |
| NEE | NextEra Energy is a major player in renewable energy, providing clean energy solutions that can help decarbonize heavy industries. | chat_gpt,claude |
| DAN | Dana Incorporated supplies power technologies for industrial applications, including electric and hybrid solutions that reduce emissions. | chat_gpt |
| FCEL | FuelCell Energy provides clean energy solutions through fuel cell technology, which can be used to reduce emissions in heavy industries. | chat_gpt,claude |
| TSLA | Tesla is a leader in electric vehicles and energy storage solutions, which are crucial for reducing emissions in heavy industries. | chat_gpt,google,claude |
| XOM | ExxonMobil is investing in carbon capture and storage technologies, which are crucial for reducing emissions in heavy industries. | chat_gpt,google |
| SEDG | SolarEdge Technologies provides solar inverters and other solutions that enhance the efficiency of solar energy systems, aiding in industrial decarbonization. | chat_gpt,claude |
| GE | General Electric is involved in renewable energy and grid solutions, which are essential for integrating clean energy into industrial processes. | chat_gpt |
| CRC |  | twitter |
| PHG |  | google |
| UL |  | google |
| ITRI | Itron provides smart metering and energy management solutions that can help heavy industry monitor and optimize energy consumption, leading to reduced emissions. | claude |
| ORA | Ormat Technologies is a geothermal and recovered energy power company that can provide clean, baseload power to help decarbonize heavy industry. | claude |
| SPWR | SunPower Corporation is a solar energy company that provides high-efficiency solar panels and energy storage solutions, which can help heavy industry reduce emissions by adopting renewable energy. | claude |
<!--[[[end]]]-->

## License

<p>
This project is licensed under <a href="./LICENSE">AGPLv3</a>.
</p>


## Contributors

Thank you for your improvements! We appreciate all the contributions from the community.

<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  repo = config['github_repo'].lower()
  cog.outl(f'<a href="https://github.com/gettilt/{repo}/graphs/contributors">')
  cog.outl(f'  <img src="https://contrib.rocks/image?repo=gettilt/{repo}" />')
  cog.outl('</a>')
]]]-->
<a href="https://github.com/gettilt/decarbonization/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=gettilt/decarbonization" />
</a>
<!--[[[end]]]-->

## Join Our Community

<a href="https://discord.gg/4vYMhRpaMY" target="_blank">
<img src="https://discord.com/api/guilds/1179775688421683220/widget.png?style=banner3" alt="">
</a>
