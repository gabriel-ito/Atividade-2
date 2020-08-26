import React,{useState} from 'react'
import {Text, View, TextInput, Button, StyleSheet, Alert} from 'react-native'


export default props => {
    const [valorA, setvalorA] = useState('')
    const [valorB, setvalorB] = useState('')
    const [resposta, setResposta] = useState('')


    function Somar(){
        setResposta(parseInt(valorA) + parseInt(valorB))
    }
    
    function Subtrair(){
        setResposta(parseInt(valorA) - parseInt(valorB))
    }
    
    function Multiplicar(){
        setResposta(parseInt(valorA) * parseInt(valorB))
    }
    
    function Dividir(){

        if (valorB == 0){
            setResposta("Impossivel dividir por zero")
        }
        else{
            setResposta(parseInt(valorA) / parseInt(valorB))
        }    
    }
    
    return (
        <View>
            <Text style={styles.text}> Informe os seguintes dados:</Text>
            
            
            <TextInput
                placeholder="Digite o valor 1"
                value={valorA}           
                onChangeText={valorA => setvalorA(valorA)}
            />
            <TextInput
                placeholder="Digite o valor 2"
                value={valorB}
                onChangeText={valorB => setvalorB(valorB)}
            />
            <Text> Resposta = {resposta} </Text>
            <Button title="Somar" onPress={(Somar)}/>
            <Button title="Subtrair" onPress={(Subtrair)}/>
            <Button title="Multiplicar" onPress={(Multiplicar)}/>
            <Button title="Dividir" onPress={(Dividir)}/>
        </View>
    );
}

const styles = StyleSheet.create({
    text:{
        fontSize:24,
        color:'blue',
        fontWeight:'bold'
    }
})
