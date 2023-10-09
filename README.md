# BDC Historic Fires Analysis

## Installation

Open a terminal, type: `R`
Once R is stared, typee: `install.packages(c('pivottabler'))` and choose `2` as mirror server.
The installation should proceed without errors, once done type `quit('yes')` and close the terminal.


## Data retrieval

Data can be retrieved from the BDC platform using the [WFS interoperability protocol](https://www.ogc.org/standard/wfs/) for geographic data.

Open a terminal and type:
```
curl -G 'https://bdcpoc.eresearch.unimelb.edu.au/geoserver/geonode/ows'\
    --data-urlencode 'service=WFS'\
    --data-urlencode 'version=1.1.0'\
    --data-urlencode 'request=GetFeature'\
    --data-urlencode 'typeName=geonode:historic_fires'\
    --data-urlencode 'outputFormat=csv'\
    --data-urlencode 'propertyName=gid,objectid,fire_id,fire_name,fire_type,ignition_c,capt_metho,area_ha,perim_km,state,agency,ignition_date,capture_date,extinguish_date,year,area_comp,perimeter_comp,thinness_ratio'\
    -o ./data/historic_fires/historic_fires.csv
    
curl -G 'https://bdcpoc.eresearch.unimelb.edu.au/geoserver/geonode/ows'\
    --data-urlencode 'service=WFS'\
    --data-urlencode 'version=1.1.0'\
    --data-urlencode 'request=GetFeature'\
    --data-urlencode 'typeName=geonode:s4_geo'\
    --data-urlencode 'outputFormat=csv'\
    --data-urlencode 'propertyName=sa4_code21,sa4_name21,sa4,week,resp_n_1920,resp_rate_1920,resp_n_1419,resp_rate_1419,asth_n_1920,asth_rate_1920,asth_n_1419,asth_rate_1419,copd_n_1920,copd_rate_1920,copd_n_1419,copd_rate_1419,bre_n_1920,bre_rate_1920,bre_n_1419,bre_rate_1419,hea_n_1920,hea_rate_1920,hea_n_1419,hea_rate_1419,heaa_n_1920,heaa_rate_1920,heaa_n_1419,heaa_rate_1419,cere_n_1920,cere_rate_1920,cere_n_1419,cere_rate_1419,ches_n_1920,ches_rate_1920,ches_n_1419,ches_rate_1419,men_n_1920,men_rate_1920,men_n_1419,men_rate_1419,burn_n_1920,burn_rate_1920,burn_n_1419,burn_rate_1419,deh_n_1920,deh_rate_1920,deh_n_1419,deh_rate_1419'\
    -o ./data/aihw/aihw.csv

curl -G 'https://bdcpoc.eresearch.unimelb.edu.au/geoserver/geonode/ows'\
    --data-urlencode 'service=WFS'\
    --data-urlencode 'version=1.1.0'\
    --data-urlencode 'request=GetFeature'\
    --data-urlencode 'typeName=geonode:census_2021_indigenous_state_sa1'\
    --data-urlencode 'outputFormat=csv'\
    --data-urlencode 'propertyName=sa1_code,tot_tot,tot_non_indig,tot_indig,impacted'\
    -o ./data/census/census_2021_indigenous_state_sa1.csv

curl -G 'https://naqd.eresearch.unimelb.edu.au/geoserver/geonode/ows'\
    --data-urlencode 'service=WFS'\
    --data-urlencode 'version=1.1.0'\
    --data-urlencode 'request=GetFeature'\
    --data-urlencode 'typeName=geonode:observations_062019_052020'\
    --data-urlencode 'outputFormat=csv'\
    --data-urlencode 'propertyName=site_id,site_name,state_name,time_stamp,longitude,latitude,pm2p5,pm10' \
    -o ./data/naqd/observations_062019_052020.csv
    
curl -G 'https://bdcpoc.eresearch.unimelb.edu.au/geoserver/geonode/ows'\
    --data-urlencode 'service=WFS'\
    --data-urlencode 'version=1.1.0'\
    --data-urlencode 'request=GetFeature'\
    --data-urlencode 'typeName=geonode:vba_fauna'\
    --data-urlencode 'outputFormat=csv'\
    --data-urlencode 'propertyName=id,site_id,comm_name,totalcount,start_year,vicadvdesc,affected' \
    -o ./data/vba/fauna.csv

curl -G 'https://bdcpoc.eresearch.unimelb.edu.au/geoserver/geonode/ows'\
    --data-urlencode 'service=WFS'\
    --data-urlencode 'version=1.1.0'\
    --data-urlencode 'request=GetFeature'\
    --data-urlencode 'typeName=geonode:vba_flora'\
    --data-urlencode 'outputFormat=csv'\
    --data-urlencode 'propertyName=id,site_id,comm_name,totalcount,coverabund,start_year,vicadvdesc,fire_resp,affected' \
    -o ./data/vba/flora.csv
```


## Analysis

### Historic fires

Open the `historic_fires.ipynb` Notebook, execute all cells, wait for the task to be compmeted, and collapse all code cells.


# Hospitalization Analysis

Open the `hospitalization.ipynb` Notebook, execute all cells, wait for the task to be compmeted, and collapse all code cells.


# Impact of Black Summer fires on indigenous population

Open the `indigenous.ipynb` Notebook, execute all cells, wait for the task to be compmeted, and collapse all code cells.


# Air Quality during Black Summer

Open the `airquality.ipynb` Notebook, execute all cells, wait for the task to be compmeted, and collapse all code cells.

